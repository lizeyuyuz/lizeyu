---
layout: post
title: "Basic Simulation"
author: "Zoey Li"
categories: journal
tags: [simulation, statistics]
---

### The very basics of simulation (Gaussian distribution) 

Suppose that $$X$$ is a random variable with PDF $$\pi(x)$$. We are interested
in calculating $$\mathbb{E}_{\pi}(h(X))= \int h(x)\pi(x)\mathbb{dx}$$. This
might be an interval difficult to integrate and might not have a closed-form
solution, so we want to generate arbitrary points from the distribution
$$\pi(x)$$ to approximate this integral. There are cases where we only know $$\pi(x)$$ up to a multiplicative/normalizing constant. In these cases, importance sampling is used, which we will cover later. 

Here is a [PDF]({{ site.baseurl }}/assets/academic_notes/basic_simulation.pdf) with code and plots. 

