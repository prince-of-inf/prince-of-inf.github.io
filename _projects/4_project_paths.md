---
layout: page
title: Modelling pathways on the campus
description: in NetLogo
img: assets/img/paths/front.jpg
importance: 1
category: fun # show as category over project blocks
# related_publications: true # adds, section, to cite: {% cite einstein1950meaning %}
# giscus_comments: true # proste komentarze jak na githubie
# redirect: https://unsplash.com # redirect to another page on click
---

One fascinating branch of econophysics is the study of collective phenomena. This field is based on the assumption that individual units follow simple rules of behavior, but when these units are grouped together, complex behavior can be observed. This phenomenon is known as emergence, which refers to the appearance of something completely new (and often unexpected) when the collective becomes more than the sum of the actions of individual units. Emergent phenomena are often unpredictable based on observations of the behavior of individual agents. In such cases, simulation models are a useful tool for understanding and analyzing these complex behaviors.

In the following project, I aimed to explore whether the paths on the campus of my university were designed in a rational way, by conducting simulation of collective path beating in NetLogo

## Preparation

The figure below shows a Google Maps image of the central courtyard of the Warsaw University of Technology (WUT) campus. On the left is the Physics building, and on the right is the Chemistry building. The road leading north goes to the Mathematics building, the eastern path leads to the main building, and the southern one leads to the Aeronautics and Environmental Engineering building. To cross the triangular square, one can also use one of three paths leading to the central fountain. 

As you can imagine, students running around the campus to make it to their classes held in different buildings was very common in our program.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/paths/mapaPW_google.jpg" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Map of WUT campus
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/paths/paths1.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Map in NetLogo
        </div>
    </div>
    
</div>


In our simulation students should walk along the designated paths and avoid walking on the grass. However, if a designated path is too long, they may be tempted to walk on the grass, which will eventually lead to the creation of a new path, that has the same preference as the paved road (since the grass has already been trampled, the perceived public cost of continuing to walk on it seems smaller).

## Results

If you'd like to see the simulation in action, `you can watch the video` on [YouTube](https://www.youtube.com/watch?v=ootxVMwd2p4) 

After some time, it became apparent that a path was consistently being trampled in the southwest part of the courtyard. Interestingly, I remembered that this area actually has a sidewalk (which can be seen on a more detailed map from OpenStreetMap).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/paths/paths2.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Simulation frame
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/paths/mapaPW.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        OpenStreetMap
        </div>
    </div>
    
</div>

Additionally, it is easy to notice the inconvenience of walking the eastern path from the center. In the simulation, students eagerly shorten their route by walking on the grass...

Unfortunately, my proposal to the dean to consider adding an additional shortcut received no response...
