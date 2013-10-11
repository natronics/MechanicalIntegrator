---
layout: post_mathjax
title: Solar System Center of Mass
categories : [Science]
tags: [Science, space]
---

Right now scientists are searching for new planets. They have telescopes
pointed at distant stars carefully measuring how fast they move and looking for
tiny deviations—or wobble—in their speed. This wobble tells us that something
must be orbiting the star. When two objects are in orbit, they both orbit their
respective center or mass, called the barycenter.

In the case of solar systems the sun is so much more massive that the rest of
the planets that the barycenter is very nearly at the center of the sun. This is
also helped by the fact that on any given day the planets are likely scattered
randomly about and to some degree cancel each other out. Think of an evenly
matched tug-of-war. But what if all the planets were on one side of the sun?
Then how far off center would the barycenter be? I guessed it would be still
very near the middle of the sun, but it turns out it's about 800,000
kilometers outside the sun!

<!--more-->

Don't believe me? I didn't believe it when I first read it so I had to calculate
it myself. How does one go about calculating the center of mass of the solar
system?

First lets set up the situation. Like all great physics problems, this is a
vast simplification. We can safely make some favorable assumptions. Put the sun
at the center of a coordinate system, and everything is on the x-axis, and only
count the 8 most massive objects other than the sun.

![diagram](/resources/photos/solar-system-cm.png)

To find the center of mass $\boldsymbol{R}$ we just add up the masses
$m\_i$ times the distances $\boldsymbol{r\_i}$ for everything and divide by the
total mass.

$$\boldsymbol{R} = \frac{\displaystyle\sum\nolimits\_i m\_i \boldsymbol{r\_i}}{\displaystyle\sum\nolimits\_i m\_i}$$

Lets actually look at some numbers:

{: .table .table-hover}
   Body  | Distance from Sun<sup>1</sup> \[cm\] |  Mass<sup>2</sup> \[g\] | % Mass of the Solar System
 ------- | ------------------------------------ | ----------------------- | --------------------------
 Sun     | 0                                    | 1.99×10<sup>33</sup>    | 99.866
 Mercury | 5.78×10<sup>12</sup>                 | 3.3×10<sup>26</sup>     | 0.000017
 Venus   | 1.08×10<sup>13</sup>                 | 4.87×10<sup>27</sup>    | 0.00024
 Earth   | 1.50×10<sup>13</sup>                 | 5.98×10<sup>27</sup>    | 0.00030
 Mars    | 2.28×10<sup>13</sup>                 | 6.5×10<sup>26</sup>     | 0.000033
 Jupiter | 7.79×10<sup>13</sup>                 | 1.90×10<sup>30</sup>    | 0.095
 Saturn  | 1.43×10<sup>14</sup>                 | 5.70×10<sup>29</sup>    | 0.029
 Uranus  | 2.88×10<sup>14</sup>                 | 8.7×10<sup>28</sup>     | 0.0043
 Neptune | 4.50×10<sup>14</sup>                 | 1.00×10<sup>29</sup>    | 0.0050

Again you can really see just how massive the sun is. It accounts for
about 99.866% of the mass in the solar system! If we use the equation above and
plug in all the distances and masses and add it up we get:

$$\begin{align\*}
 \boldsymbol{R} &= \frac{2.9969\times 10^{44} \, \[\mathrm{cm} \cdot \mathrm{g}\]}{1.9917\times 10^{33} \, \[\mathrm{g}\]}  \\\
  &= 1.51\times 10^{11} \, \[\mathrm{cm}\]
\end{align\*}$$


Or in other words, the center of mass of the solar system, with all the
planets to one side, is about 1.5 million kilometers from the center of the
sun. The sun itself is about 0.7 million kilometers across, so that puts th
 center of mass about 800,000 kilometers off the surface of the sun.

Just something to think about. But don't forget, given the scale of the solar
system, 800,000 kilometers isn't very far. In fact it's about 70 times closer
to the sun than Mercury, the closest planet.

### References

 1. Universe today — _[How Far are the Planets from the Sun?](http://www.universetoday.com/guide-to-space/the-solar-system/how-far-are-the-planets-from-the-sun/)_
 2. Ask a Scientist — _[Planets and Their Mass](http://www.newton.dep.anl.gov/askasci/ast99/ast99227.htm)_
