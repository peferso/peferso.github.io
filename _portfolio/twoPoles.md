---
layout: single
title: "Calculation of particle masses and widths"
author_profile: true
tags: [Physics, Particle Physics, Theoretical Physics, resonances, amplitudes]
comments: false
classes: wide
toc: true
gallery1:
  - url: /assets/portfolio/twoPoles-figs/discovery-2317.png
    image_path: /assets/portfolio/twoPoles-figs/discovery-2317.png
    alt: "placeholder image 1"
    title: "Event distributions of Ds pi particle pairs as measured by BaBar Collaboraion."
gallery2:
  - url: /assets/portfolio/twoPoles-figs/fig-events-belle-fit1.png
    image_path: /assets/portfolio/twoPoles-figs/fig-events-belle-fit1.png
#alt: "placeholder image 1"
  - url: /assets/portfolio/twoPoles-figs/fig-imt-1rs.png
    image_path: /assets/portfolio/twoPoles-figs/fig-imt-1rs.png
#alt: "placeholder image 2"
  - url: /assets/portfolio/twoPoles-figs/fig-imt-2rs.png
    image_path: /assets/portfolio/twoPoles-figs/fig-imt-2rs.png
#alt: "placeholder image 3"
---

Several papers included in my PhD focus on the understanding of some special particles called **resonances**.

# Introduction
Resonances are unstable particles, that is, they don't live during much time.
In fact, most of them are very rare in nature, they are produced in extreme events which involve nuclear reactions.
They can be pictured as some weird combination of pieces of some toy, that can keep together at most during 
0.000000000000000000000001 seconds.
After this lapse of time, they split apart forming other particles, or _channels_.

Resonances, like almost all the particles, are so tiny that we do not even know what is their size for sure, but it should be of the order of
0.0000000000000001 meters.

This means that we do not observe them directly. Actually, when we "observe" something, we need to hit the object with light, which is a stream photons, and process the scattered photons. 

## Events distributions

In the case of resonances, we observe them in collisions of other particles, which are accelerated in experiments and crashed into each other. 
The colliding particles "split appart" and, sometimes, the subproducts recombine during very small times forming new particles, that is, resonances.
Here the word _sometimes_ is very important... Probability is at the heart of Quantum Mechanics! 
Collision experiments are done in experimental facilities called particle accelerators or colliders, such as the famous [Large Hadron Collider (LHC)](https://home.cern/science/accelerators/large-hadron-collider). 
In these experiments, particles are "crashed" many times, a lot of them accelerated together in great numbers forming what are called beams.
The results of all these collisions are measured and accumulated, allowing to estimate the probability of measuring certain products after the collisions. 
With this information, scientists obtain curves as the following one:

{% include gallery id="gallery1" caption="Events distributions of particle pairs" %}

The image above represents how a resonance manifests experimentally.
The plot is a  distribution of events, and it is proportional to the number of Ds pi pairs measured by [BABAR Collaboration](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.90.242001) in the discovery of the Ds(2317) resonance.
What this figure is telling us is that in the products generated in the collisions, the number of Ds pi pairs detected is different depending on the energy of the pair (which is the x axis).
The peak is an excess of Ds and pions pairs measured with energies around 2.3 GeV/c^2.
This could be interpreted as if these particles were produced after the decay of the resonance.
Recall that energy and mass are equivalent (E=m\*c^2), therefore, the mass of the resonance is well described by the position of the peak at 2.3 GeV/c^2, while the width of the peak is related with the resonance lifetime.

# Amplitudes

In my PhD I confronted some experimental results similar to the one described above with theoretical calculations. 
The curves as the one shown above can be also obtained theoretically.
Of course, there will be different theoretical models able to describe a single curve or data set, each one with different assumptions, "ingredients" and parameters.
The ultimate goal of a theory describing particle collisions is to provide the **scattering amplitude**.
In a few words, it is a mathematical function that depends on a set of kinematic variables, such as the energy and momentum of the particles involved.
It will also depend on other parameters or physical constants.
There is an infinite variety of mathematical combinations that could describe a given process or experimental curve, but the space of functions is highly reduced taking into account physical constraints coming from symmetries and other principles. Although we will not focus on these topics here.

## Resonances as singularities in the complex energy plane

From my point of view, one of the most beautiful aspects of particle physics and mathematics is the link that exists between particles and the theory of complex numbers.

{% include gallery id="gallery2" caption="Theoretical amplitudes and resonances as poles in the complex energy plane" %}

When scattering amplitudes are considered as functions of complex variables, they automatically can be analysed as surfaces in the complex plane.
The peaks representing resonances in the experiment, from a theoretical point of view, are associated to singularities of the scattering amplitudes in the complex energy plane (this means, with the energy variable having an imaginary component: E=Er+i\*Ei).
The caveats and subtleties associated to this interpretation are beyond the scope of this post, but let me just say that, in practice, the mass and width of a resonance can be computed from the location of these singularities the complex plane of the energy variable.
