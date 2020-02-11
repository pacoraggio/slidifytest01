---
title       : Melbourne House Prices Map Application
subtitle    : an Application to find House Prices in Melbourne, Australia
author      : Paolo Coraggio
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, ]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
logo        : MelbourneLogo.png
assets      : {assets: ../../assets}
---

<style>
.title-slide {
  background-color: #FF8A00; /* #EDE0CF; ; #CA9F9D*/
}
</style>

--- .class #id bg:black

## HPM App 

1. The application shows houses prices in Melbourne
2. Shows an interactive map
3. Allow you to search using customisable parameters

--- .class #id bg:black

## How to use it

> Go to the Map section of the application

> Insert the parameters of your search

> The resulting matches are shown on a Map with additional information

> Compare the price of the houses with the mean of Melbourne House Market

--- .class #id 

## How to push on Git?


a. I simply don't know..
b. RAAAAAAAA

--- .class #id 

## A Simple Plot


```r
require(ggplot2)
qplot(wt, mpg, data = mtcars)
```

<img src="assets/fig/simpleplot-1.png" title="plot of chunk simpleplot" alt="plot of chunk simpleplot" style="display: block; margin: auto;" />

--- .class #id bg:yellow

## Motion plot

<!-- MotionChart generated in R 3.6.2 by googleVis 0.6.4 package -->
<!-- Tue Feb 11 10:09:33 2020 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID2f5439497cc0 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
"Apples",
2008,
"West",
98,
78,
20,
"2008-12-31"
],
[
"Apples",
2009,
"West",
111,
79,
32,
"2009-12-31"
],
[
"Apples",
2010,
"West",
89,
76,
13,
"2010-12-31"
],
[
"Oranges",
2008,
"East",
96,
81,
15,
"2008-12-31"
],
[
"Bananas",
2008,
"East",
85,
76,
9,
"2008-12-31"
],
[
"Oranges",
2009,
"East",
93,
80,
13,
"2009-12-31"
],
[
"Bananas",
2009,
"East",
94,
78,
16,
"2009-12-31"
],
[
"Oranges",
2010,
"East",
98,
91,
7,
"2010-12-31"
],
[
"Bananas",
2010,
"East",
81,
71,
10,
"2010-12-31"
] 
];
data.addColumn('string','Fruit');
data.addColumn('number','Year');
data.addColumn('string','Location');
data.addColumn('number','Sales');
data.addColumn('number','Expenses');
data.addColumn('number','Profit');
data.addColumn('string','Date');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartID2f5439497cc0() {
var data = gvisDataMotionChartID2f5439497cc0();
var options = {};
options["width"] = 600;
options["height"] = 500;
options["state"] = "";

    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartID2f5439497cc0')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartID2f5439497cc0);
})();
function displayChartMotionChartID2f5439497cc0() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID2f5439497cc0"></script>
 
<!-- divChart -->
  
<div id="MotionChartID2f5439497cc0" 
  style="width: 600; height: 500;">
</div>


--- .class #id 

## Interactive Chart

require(rC)
