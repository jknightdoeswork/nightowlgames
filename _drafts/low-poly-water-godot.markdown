---
layout: post
title:  "Low Poly Water Shader in Godot"
date:   2019-12-05 11:10:13 -0600
categories: godot
---

_Note: this post is in development._

In this tutorial, I'm going to show you how to create this water effect in Godot.

We'll start with a quad. Add a MeshInstance to your scene and add a Quad Primitive to the Mesh Instance. Add a Shader Material to the quad, and add a Shader to the Shader material.

I like to save all of these resources to the file system as I create them, so my file structure looks like this:

	water/
	 WaterMaterial.tres
	 WaterShader.shader

There are three core components to our water shader: color by depth, shoreline foam and wave foam.

## Color By Depth
We use the `DEPTH_MAP` in order to find the color.

## Shoreline foam
We use a noise texture to add foam to the edge of the water.

## Wave Foam
We sample a noise texture to add foam to the middle of the water.

