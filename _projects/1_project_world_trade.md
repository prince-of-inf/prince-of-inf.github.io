---
layout: page
title: Analysis of World Trade
description: in Python
img: assets/img/world_trade/world_trade.jpg
importance: 1
category: economics # show as category over project blocks
# related_publications: true # adds, section, to cite: {% cite einstein1950meaning %}
# giscus_comments: true # proste komentarze jak na githubie
# redirect: https://unsplash.com # redirect to another page on click
---

Check out the code on [Github](https://github.com/prince-of-inf/WorldTradeComplexNetworks)


Trade functions as the lifeblood of the global economy. Over the course of the 20th century, global trade evolved dramatically, shaped by various economic, political, and technological factors. In this project, we examine its evolution over time, with a focus on the period between 1948 and 2000. The data, sourced from the World Trade Organization (WTO), was thoroughly cleaned and preprocessed to ensure accuracy. Due to missing values in certain regions and years, the analysis was limited to the years 1948-2000. All values were adjusted to reflect the purchasing power of the U.S. dollar in 2021 to account for inflation and allow for meaningful comparisons over time.

## MAIN TRADING PARTNERS

By analyzing the maximum spanning tree, we identify the principal trading partners for each country. This method allows us to visualize how countries are interconnected through trade, revealing the key players in the global economy. 

Post-World War II Reconstruction (1945-1960s) saw the establishment of international institutions designed to promote trade liberalization and economic cooperation, such as the General Agreement on Tariffs and Trade (GATT) in 1947. During this period, many countries sought to rebuild their economies and restore pre-war trade levels. The U.S. emerged as a dominant player in global trade, both as a producer and consumer. In the year `1950`, the dominance of the United States and the United Kingdom in global trade is unmistakable. The U.S. was not only the world's largest economy but also a key player in rebuilding the global trade system through initiatives such as the Marshall Plan, which helped Europe recover from the devastation of World War II. Meanwhile, the UK maintained its influence through the Commonwealth, which established strong trading ties across its former colonies.

However, 25 years later, by the mid-1970s and 1980s, a shift in the global economic landscape began to take shape. In the year `1975` West Germany, France, and Japan re-emerged as significant trading partners. Germany, in particular, benefited from the post-war economic boom and became the biggest European conomy. German Wirtschaftswunder and french (Trente Glorieuses) were fueled by their integration into the global market and the success of the European Economic Community (EEC), which later evolved into the European Union (EU). Japan, with its rapid industrialization and export-driven growth, became a major economic force, particularly in electronics and automobiles.

By the year `2000`, we observe further evolution of the global trading system. The post-Cold War era marked a shift towards more complex and multipolar trade relationships. For instance, following the dissolution of the Soviet Bloc and the collapse of the USSR in 1991, many former Soviet satellite states saw unified Germany, rather than Russia, emerge as their primary trading partner. This shift was largely due to Germany's central role in the European Union and its proximity to these countries, which made it an attractive trading partner. Russia, struggling with economic instability and the challenges of transitioning from a planned economy to a market-oriented system, lagged behind in terms of establishing trade relationships with its former satellites.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/kr1950.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Year 1950
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/kr1975.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Year 1975
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/kr2000.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Year 2000
        </div>
    </div>
</div>
<div class="caption">
    Maximum spanning trees of global trade partners. Each country creates only one link to its major partner (country with the greatest trade exchange). Width of link scales with trade value.
</div>

## MAIN TRADERS THROUGH YEARS

In the last century, approximately half of all commercial exchanges were conducted by the top eight countries. These nations consistently represented the largest share of global trade, serving as the economic engines that drove the world economy. While there have been occasional instances of new trading leaders emerging temporarily, the upper ranks of the global trade hierarchy have predominantly been dominated by the world's major powers, especially in the post-World War II era.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/allexport5.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Top exporters
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/allimport5.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Top importers
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/alltrade5.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Top traders
        </div>
    </div>
</div>
<div class="caption">

</div>

## TRADE GROWTH

The distribution of summed trade flows among countries exhibits a "fat tail" characteristic, indicating that while many countries contribute only modestly to global trade, a few global powers dominate the trade landscape. This unequal distribution is a hallmark of the global economy, where the largest economies—such as the United States, Germany, and Japan account for a disproportionately large share of international trade. In fact, a small number of countries consistently account for more than half of all global trade. This phenomenon is often referred to as the Pareto principle, or the 80/20 rule, where a majority of trade volume is concentrated in the hands of a minority of nations.

Additionally, the assortativity in global trade is negative, signifying that countries with lower trade volumes are more likely to engage in trade with larger economies rather than with countries of a similar economic size. This means that smaller, less-developed nations tend to have more trading relationships with powerful economies, while the largest economies often trade with each other, but also engage with smaller nations to source raw materials, low-cost labor, or new markets for their goods. This phenomenon is well modelled by the `Gravity model of trade`.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/s1948.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
</div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/s2000.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">

</div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/world_trade/r_pearson.png" title="example image" class="img-fluid rounded z-depth-1"  zoomable=true %}
        <div class="caption">

</div>
    </div>
</div>
<div class="caption">
    CCDF stands for Complementary cumulative distribution function also known as tail distribution.
</div>