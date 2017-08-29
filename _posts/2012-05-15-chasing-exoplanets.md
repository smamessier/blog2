---
layout: post
title: Chasing exoplanets from your backyard
date: '2012-05-15 20:16:00'
tags:
- projects-edu
---

The full original report is available [here](http://seb.mamessier.com/docs/supaero/pir1A/PIR_rapport_final.pdf) in french. This post gives a short english summary of our adventure, it is still in progress. 

#### Introduction
I often refer to this amazing underrated movie - The Truman Show - that I discovered thanks to my highschool English teacher a couple of years back: even if there seems to be a consensus among a community, it doesn't hurt to experience the truth yourself. It is actually a very important step in research: one should always try to reproduce previous findings as no one is fully immune to honest mistakes.

#### A simple "Initiation to research" undergrad project.
In 2010, Romain Pennec and I had to find a topic for our Supaero (French aerospace school) 1st year research project. It had to be related to our common passion for astronomy. It also had to be mind-blowing. It had come to our ears that a very skillfull pseudo-professional french astronomer - Christian Buil - had managed to confirm the existence of an extrasolar planet from his backyard - using a spectrometer -. Although we only had a couple of years of experience with telescopes, we had the math, the energy and motivation on our side so we decided to commit to such an adventure.

#### The transit method
We quickly came to the conclusion that the only affordable method would be the transit method - which, similarly to an eclipse, consists in observing the drop of brightness of a remote star when its hypothetical planet transits between its host star and our point of view (earth) - also, our time horizon for this project forbid any long term observation and therefore we had to give up on discovering a new exoplanet and rather focus on confirming a previous finding.
<p style="text-align:center !important"><img src="/content/images/2016/04/transit.png" width="200px"/></p>

#### The target: HD189733b
By the end of 2009, only 72 extrasolar planets had been discovered using the transit method. We used the excellent resource [http://var2.astro.cz](http://var2.astro.cz/ETD/predict_detail.php?STARNAME=HD189733&PLANET=b&delka=1.475501&sirka=43.566169) to find the most promising target with respect to our time frame and available instruments. It turned out `HD189733 b` was to transit in front of its host star `HD189733` three times during our project, and two occurrences were potentially observable from South of France. Other parameters were to be considered such as the `altitude` of the star - how high it is in the sky, the higher the thiner of an atmospheric layer the light has to go through - the `azimuth` of the star from your observation point - this matters most in suburban areas with light pollution being more important in the direction of big cities, if you have a car and a mobile setup then this should not be as important.  , the `apparent magnitude` - the brightness of a star given in a logarithmic scale - and the predicted `depth` of the drop of brightness provoked by the transit were factors that lead us pick `HD189733 b` as our target.
`HD189733` (to not mix up with its hypothetical exoplanet `HD189733 b`) is a quite close (63 light years away) orange dwarf star you can observe in the Vulpecula - little fox - constellation. Its average apparent magnitude is `7.33`, which means it is `610` times darker than Vega, one of the brightest stars of the northern hemisphere. It is also slightly darker than the darkest star the human eye could capture in perfect conditions which means that the first challenge of our experiment will be to find `HD189733` in the night sky !!
The first observation night takes place on campus in Toulouse, with a terrible light pollution. We aligned our telescope with respect to the polar star, and used the 3-star alignment method of our motorized mount to be able to photograph the wished area. (With such a poor sky, it is virtually impossible to try to find such a star manually). It is still hard to know whether we are looking at the right place as we can't see the nearby nebulae through the ocular lens as we thought we would. Indeed, the Dumbbell nebulae (M27) is not far as you will see in the following pictures. We took a couple of shots and after some basic image processing, we found out we were almost at the right place!
<p style="text-align:center !important"><img src="/content/images/2016/04/overlay.png" width="100%"/></p>
The blue image represents the area we shot and the dark overlay was taken from a sky map to get an understanding of where we should have been looking at. Ok we missed `HD189733` for a couple of pixels but we knew we could at least somewhat trust our alignment and pointing method.

#### Measuring our instrumental accuracy
We had read a couple of stories and felt confident our equipment was theoretically good enough to capture the drop of photons caused by the transit of `HD189733b`. However many sources of disturbances can decrease our signal-noise ratio and therefore we had to check how accurate our measurement pipeline could be. We drove an hour away from Toulouse to get a better sky and simply did dozens of 30s shots of `HD189733`'s area. 
<p style="text-align:center !important"><img src="/content/images/2016/04/photometry.png" width="400px"/></p>
Thanks to our previous experience, find the star was much easier and using the technique of differential photometry with three neighbor stars, we were able to find our measurement precision. After a thorough image processing pipleine (using darks, flats, ..), we obtained a standard deviation of `7 mmag` which was great news as the depth of the transit was supposed to be around `30 mmag`.
<p style="text-align:center !important"><img src="/content/images/2016/04/precision.png" width="80%"/></p>

#### Shoot it
Coming soon ;)

#### Analyze the data
Coming soon ;)

Sources:
* http://www.astrosurf.com/~buil/extrasolar/obs.htm