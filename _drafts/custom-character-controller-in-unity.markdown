---
layout: post
title:  "Custom Character Controller in Unity"
date:   2020-04-11 11:11:11 -0600
categories: unity
---

I've written countless character controllers in unity and have iterated on the velocity and drag many times. The following is the most basic character controller there is. There's no max speed and it has a simplistic drag model.

# The basic algorithm of a kinematic character controller is this:

{% highlight csharp %}
Vector3 position;
float friction;
float acceleration;
void Update()
{
	velocity += GetInput()*acceleration * Time.deltaTime;
	position += velocity * Time.deltaTime;
	velocity -= friction * Time.deltaTime * velocity;
}
{% endhighlight %}

Implement that and you can start moving about the environment and play with the acceleration and friction. Max speed and acceleration curves are simple extensions. I dunno, something about a little cube running on top of another cube with the right friction and acceleration looks and feels so good to me.

The problem here, is that you'll run through walls without any knowledge of their presence.

Enter collision detection, or rather, collision resolution.

# A basic collision resolving algorithm looks like this:

{% highlight csharp %}
void FixedUpdate() {
	// check collisions
	int numOverlaps = Physics.OverlapBoxNonAlloc(m_transform.position, m_halfExtents, m_colliders, m_rigidBody.rotation, layerMask, QueryTriggerInteraction.UseGlobal);
	for (int i = 0; i < numOverlaps; i++) {
		Vector3 direction;
		float distance;
		if (Physics.ComputePenetration(m_boxCollider, m_transform.position, m_transform.rotation, m_colliders[i], m_colliders[i].transform.position, m_colliders[i].transform.rotation, out direction, out distance))
		{
			Vector3 penetrationVector = direction*distance;
			Vector3 velocityProjected = Vector3.Project(velocity, -direction);
			m_transform.position = m_transform.position + penetrationVector;
			velocity -= velocityProjected;
			Debug.Log("OnCollisionEnter with " + m_colliders[i].gameObject.name + " penetration vector: " + penetrationVector + " projected vector: " + velocityProjected);
		}
		else
		{
			Debug.Log("OnCollision Enter with " + m_colliders[i].gameObject.name + " no penetration");
		}
	}
}
{% endhighlight %}

The only really interesting element here is that you must set the velocity to zero along the collision vector. We do that by using Vector3.Project to find what component of velocity needs to be eliminated. This makes it so when you hit the ground, for example, the -y element of velocity is eliminated.
