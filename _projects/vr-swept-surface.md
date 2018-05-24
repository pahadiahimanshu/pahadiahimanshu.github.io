---
layout: project
title: Interactive Swept Surface Modeling in Virtual Reality
meta: An interactive VR application that allows the user to sweep surfaces in virtual environment using both the motion-tracked contollers.
category: project
index: 1
image: ssm-cover.jpg
---

Virtual Reality is by far seen as a creative and artistic medium. Drawing and sculpting is hence of prime importance in the future of VR. Most of the papers and applications available take the concept of freehand sketching for mostly design purposes in VR. However freehand sketching is not usefull for making smooth surfaces for the purpose of modelling.

An implementation of the algorithm stated in ['Interactive swept surface modeling in virtual reality with motion-tracked controllers'](https://dl.acm.org/citation.cfm?id=3092908) by Tim McGraw, Esteban Garcia and Drew Summer (Purdue University) which was published in SBIM'17.

It is difficult to achieve smooth curves and surfaces while freehand sketching in air. Hence, the paper introduces Hermite spline curves as a modeling and control primitive. There are three options mentioned in the paper for the type of surface that can be modelled using these hermite curves- Swept Surfaces, Repeated cloned meshes, and Tubular structures. After the position is defined by the hermite splines, the orientation is ascertained by a rotation minimization frame. The frame and reparameterization is done to allow the user to orient and scale the surfaces and cloned meshes. 

**Development Environment** - Unity Engine, C# Scripting, HTC Vive System (with controllers and Lighthouse setup)

#### Features -  

{% include figure.html src='ssm-trackpad-feature.jpg' caption='User can switch between different options' %}

{% include figure.html src='ssm-trigger-feature.jpg' caption='Trigger usage' %}

#### Implementation - 

*   *Hermite splines* - The cubic Hermite curve has two endpoints p0 and p1. At the endpoints the curve is tangent to the given vectors m0 and m1. The parameteric equation of the curve is given by - 

<figure class="content__image " style="display: flex;align-items: center;flex-direction: column;">
    <img class="content__image__img"  src="https://latex.codecogs.com/gif.latex?\begin{center}&space;s(u)&space;=&space;p_{0}H_{0}(u)&space;&plus;&space;m_{0}H_{1}(u)&space;&plus;&space;m_{1}H_{2}(u)&space;&plus;&space;p_{1}H_{3}(u)\\&space;\shortintertext{&space;where\&space;u}&space;\in&space;\shortintertext{[0,1]&space;and\&space;basis\&space;functions\&space;are\&space;given\&space;by}&space;\\&space;H_{0}(u)&space;=&space;2u^3&space;-&space;3u^2&space;&plus;&space;1,\\&space;H_{1}(u)&space;=&space;u^3&space;-&space;2u^2&space;&plus;u,\\&space;H_{2}(u)&space;=&space;-2u^3&space;&plus;&space;3u^2,\\&space;H_{2}(u)&space;=&space;u^3&space;-&space;u^2&space;\end{center}" title="\begin{center} s(u) = p_{0}H_{0}(u) + m_{0}H_{1}(u) + m_{1}H_{2}(u) + p_{1}H_{3}(u)\\ \shortintertext{ where\ u} \in \shortintertext{[0,1] and\ basis\ functions\ are\ given\ by} \\ H_{0}(u) = 2u^3 - 3u^2 + 1,\\ H_{1}(u) = u^3 - 2u^2 +u,\\ H_{2}(u) = -2u^3 + 3u^2,\\ H_{2}(u) = u^3 - u^2 \end{center}" />
</figure>

*    *Line Renderer* - We use unity's own line renderer component to draw the splines and surfaces. The issue with using this feature is that it does not render one-pixel-wide lines. It renders billboard lines (polygons that always face the camera) that have a width in world units. Since, we move around the shapes we created, the shapes always face towards us, which makes them look unrealistic. This can be fixed though, if we create meshes instead of lines.
*    *Closed-surfaces* - Hermite splines are looped using a property of line renderer. Sweeping these closed splines can generate tubular surfaces which are hallow from inside.
*    *Freehand sketching* - Hermite splines are a great way of utilising both the controllers, but freehand sketching can make great shapes too.
*    *Swept Surfaces* - When the trigger on the right controller is pulled a swept surface is generated from the sequence of Hermite splines.


#### Gallery
{% include figure.html src='ssm-hermite-shape.jpg' caption='System constantly shows how the hermite will look with certain orientation' %}
{% include figure.html src='ssm-surfaces.jpg' caption='Sweept surfaces' %}
{% include figure.html src='ssm-closed-spline.jpg' caption='Closed Hermite spline' %}
{% include figure.html src='ssm-material.jpg' caption='Different material' %}
{% include figure.html src='ssm-art.jpg' caption='Let the imagination flow!' %}




