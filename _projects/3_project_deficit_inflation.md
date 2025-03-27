---
layout: page
title: Does debt and deficit cause inflation?
description: in Python and Dash
img: assets/img/deficit/front.jpg
importance: 1
category: economics # show as category over project blocks
# related_publications: true # adds, section, to cite: {% cite einstein1950meaning %}
# giscus_comments: true # proste komentarze jak na githubie
# redirect: https://unsplash.com # redirect to another page on click

# Check out the code on [Github](https://github.com/prince-of-inf/WorldTradeComplexNetworks)
---

A budget deficit, which occurs when a government's expenditures exceed its revenues, sparks considerable debate about its impact on the economy. One key issue is its potential connection to inflation. Intuitively, one might assume that to cover the resulting "budget gap," the government could resort to increasing the money supply, which in turn could lead to higher inflation. However, this mechanism is more complex, and the impact of the budget deficit on inflation can occur through various transmission channels, such as:

<ol>
    <li>Financing the deficit through money printing – If the government chooses to cover the deficit by issuing more currency, it risks devaluing the money already in circulation, thereby increasing inflationary pressures.</li>
    <li>Increase in public spending – Higher government expenditures can stimulate demand in the economy, potentially leading to rising prices if supply fails to keep up.</li>
    <li> Effect on confidence in the currency – Persistent deficits may undermine trust in the stability of the national currency, leading to depreciation and imported inflation.</li>
    <li>Tax increases and fiscal policy changes – Efforts to reduce the deficit through higher taxes or shifts in fiscal policy can influence inflation dynamics, either by dampening supply or by altering business costs.</li>
</ol>

In this project, I decided to examine this relationship using real-world data to gain a clearer understanding of its effects. 

To speed up exploatory analysis of data I built neat dynamic app in Dash/Plotly. Unfortunately you can't access it at the moment, but if you are curious, you can check out its code on [Github](https://github.com/prince-of-inf/DeficitDebtInflation)

## Data and Methodology

Data was sourced from the IMF and the World Bank for the period 1995–2024, averaged over five-year intervals.
Variables used:
<ol>
    <li> Inflation – measured by the annual growth rate of the Consumer Price Index (CPI).</li>
    <li> Net budget surplus – calculated as government revenues minus expenditures, expressed as a percentage of GDP.</li>
    <li> Gross debt – representing the accumulated fiscal deficit, also expressed as a percentage of GDP.</li>
</ol>

Countries were categorized into four income groups based on gross national income per capita: Low-income, Lower-middle-income, Upper-middle-income, High-income.

Cases where inflation exceeded 500% (3 instances) were excluded as outliers.

For each subset, the Spearman correlation coefficient (a measure of monotonic association) was calculated.

Additionally, data was fitted using two regression methods:
<ol>
   <li> Ordinary Least Squares (OLS) – standard estimator of linear relationships, as a santiy check. </li>

   <li> Huber regression – to reduce the influence of outliers by assigning lower weights to extreme values. </li>
</ol>


<div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/deficit/venezuela.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    <div class="caption">
    Example of extreme outlier - hiperinflation in Venezuela 2015-2019, CPI change has reached 17 thousand % (sic!) in 5 years average. This clearly shows why using OLS to fit linear model is not the best idea. Other excluded outliers (over 500 %) were Venezuela in 2020-2024 and Angola in 1995-1999.
    </div>

</div>

## Net Budget Deficit

In general, the existence of a budget surplus or deficit does not correlate with inflation increases.


<div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/deficit/netto.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    <div class="caption">
    Spearman Coefficient for correlation between budget surplus/deficit and CPI.
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig0_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
     <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig1_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>

</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig2_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
     <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig3_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>

</div>

<br> 
<br> 

But if we remove countries with surplus, we can observe statistically significant correlation between budget deficits and inflation growth but only in low-income countries.

<br> 

<div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/deficit/netto only deficit.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    <div class="caption">
    Spearman Coefficient for correlation between budget deficit and CPI.
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig0_deficit_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
     <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig1_deficit_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>

</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig2_deficit_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
     <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig3_deficit_net.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>

</div>

This suggests that these countries may resort to increasing the money supply to cover budget shortfalls. Lower-income countries may lack access to stable debt financing, forcing them to monetize their deficits (print money), which directly fuels inflation. They probably have weaker institutions and lower policy credibility can make it harder for governments to implement effective anti-inflationary policies, then bigger economies, where governments use a variety of fiscal and monetary tools to manage inflation independently of budget balances.

## Gross Debt

A statistically significant correlation was found between public debt and inflation growth in low-income and upper-middle-income countries, but with opposite trends:

<ul>
    <li>In upper-middle-income countries, higher debt is associated with slower inflation growth.</li>
    <li>In low-income countries, higher debt is linked to faster inflation growth.</li>
</ul>

<div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/deficit/debt.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    <div class="caption">
    Spearman Coefficient for correlation between gross debt and CPI.
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig0_debt.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
     <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig1_debt.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>

</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig2_debt.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
     <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/deficit/fig3_debt.png" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>

</div>

Findings about lower-income countries are consistent with results for budget deficit.

A possible explanation for upper-middle-income group is that countries with higher income, are structurally closer to high-income economies - their debts are nominally much higher than these of poorer countries and they can only incur them because of managing inflation under control. On the other hand poorer nations from this income group are less stable and thus the trend emerges.

## Conclusions

I found this project to be great oportunity to learn more about measures of debt and inflation, and also take a broader perspective on different nations. 

I hope that examples shown, helped you assess connection between inflation and deficit, which isn't always straightforward.
