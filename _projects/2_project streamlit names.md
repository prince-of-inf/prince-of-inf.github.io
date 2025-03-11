---
layout: page
title: Analysis of World Trade
description: in Python
img: assets/img/random_names/front.jpg
importance: 1
category: fun # show as category over project blocks
# related_publications: true # adds, section, to cite: {% cite einstein1950meaning %}
# giscus_comments: true # proste komentarze jak na githubie
# redirect: https://unsplash.com # redirect to another page on click
---

Generate some names on [site](https://rpg-random-names.streamlit.app/) (Waring: it could take up some seconds to wake up the app!)

## Random tables

I am a huge fan of tabletop role-playing games (TTRPGs). These games rely on conversations between several people who collaboratively create a story unfolding in their imagination. To support their efforts, TTRPGs often use random tables, which provide suggestions for what might happen next, such as who the players encounter in an abandoned factory or what characteristics the encountered dragon might have.

An important element that lends credibility to the worlds being created is names. Most game modules include at least one random table with names to help players generate appropriate and immersive character, place, or creature names.

Example of a random table:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/random_names/randomtable.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Example of random table of names (can you guess origin of them?)
        </div>
    </div>
</div>

<ul>
<li>But what if traditional names have become boring?</li>
<li>What if these traditional names don't fit into our fantasy world?</li>
<li>And what if, in our alternate version of history, the Vikings sailed all the way to China and we need names that blend these two cultures?</li>
</ul> 

## Generating names

To address this need, I created this name generator. It allows you to combine any combination of names from different origins to create completely new and unique names. The generator is based on Markov chains, a simple stochastic process that allows for combining randomness with determinism. By using order of letters in existing names, we can provide a base for the generator so that the resulting names don’t consist of unpronounceable clusters of consonants. However, a bit of randomness ensures that entirely new, unique names are generated.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/random_names/random_names.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Example of generated Swedish-Chinese names
        </div>
    </div>
</div>

`Have fun!`



