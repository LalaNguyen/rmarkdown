---
title       : Slidify Demo
subtitle    : HTML5 slides from R Markdown
author      : Minh Nguyen
job         : R Hacker
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
ext_widgets: {rCharts: [libraries/nvd3]}

---

## Read-And-Delete

1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!

---
## Showing off what can be achieved without leaving RStudio

This is not serious analysis of Australian employment data. I just had jobs data lying around in  formats that were suited to show how `ggplot2`, `googleVis`, `Shiny` & `rCharts` could all be implemented into a `Slidify` presentation.

<div align="center">
<img src="http://24.media.tumblr.com/tumblr_lrq4pfRwh51r3uvuvo1_500.gif">
</div>

---
## Slide 2


```r
require(rCharts)
require(googleVis)
nodes_network <- read.csv("~/Development/env/citation_network/nodes_network.csv", 
    sep = ";")
dataSub <- subset(nodes_network, !(group == 1))
cdata <- aggregate(dataSub["id"], by = dataSub[c("country")], FUN = length)
names(cdata) <- c("Country", "No.Inventors")
Geo = gvisGeoChart(cdata, "Country", "No.Inventors", options = list(gvis.editor = "S&P", 
    projection = "kavrayskiy-vii", colorAxis = "{colors:['#91BFDB', '#FC8D59']}"))
```





---
## Map

<!-- GeoChart generated in R 3.1.1 by googleVis 0.5.6 package -->
<!-- Sat Dec  6 23:04:56 2014 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataGeoChartIDe903d631070 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 "AE",
3 
],
[
 "AR",
5 
],
[
 "AT",
57 
],
[
 "AU",
94 
],
[
 "BD",
1 
],
[
 "BE",
70 
],
[
 "BR",
21 
],
[
 "CA",
224 
],
[
 "CH",
114 
],
[
 "CL",
2 
],
[
 "CN",
273 
],
[
 "CO",
2 
],
[
 "CU",
13 
],
[
 "CZ",
16 
],
[
 "DE",
809 
],
[
 "DK",
40 
],
[
 "EE",
6 
],
[
 "EG",
1 
],
[
 "ES",
29 
],
[
 "FI",
33 
],
[
 "FR",
331 
],
[
 "GB",
272 
],
[
 "GT",
1 
],
[
 "HK",
16 
],
[
 "HU",
3 
],
[
 "IE",
31 
],
[
 "IL",
58 
],
[
 "IN",
91 
],
[
 "IS",
4 
],
[
 "IT",
95 
],
[
 "JO",
1 
],
[
 "JP",
2156 
],
[
 "KP",
2 
],
[
 "KR",
947 
],
[
 "KW",
7 
],
[
 "KY",
1 
],
[
 "LI",
1 
],
[
 "LT",
1 
],
[
 "LU",
3 
],
[
 "MC",
2 
],
[
 "MO",
1 
],
[
 "MX",
11 
],
[
 "MY",
8 
],
[
 "NL",
105 
],
[
 "NO",
24 
],
[
 "NZ",
25 
],
[
 "PE",
1 
],
[
 "PL",
2 
],
[
 "PT",
3 
],
[
 "RU",
9 
],
[
 "SA",
13 
],
[
 "SE",
75 
],
[
 "SG",
59 
],
[
 "SI",
3 
],
[
 "SK",
3 
],
[
 "TH",
3 
],
[
 "TR",
4 
],
[
 "TT",
1 
],
[
 "TV",
1 
],
[
 "TW",
582 
],
[
 "UA",
2 
],
[
 "US",
5494 
],
[
 "VE",
1 
],
[
 "VN",
1 
],
[
 "ZA",
4 
] 
];
data.addColumn('string','Country');
data.addColumn('number','No.Inventors');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartGeoChartIDe903d631070() {
var data = gvisDataGeoChartIDe903d631070();
var options = {};
options["width"] =    556;
options["height"] =    347;
options["projection"] = "kavrayskiy-vii";
options["colorAxis"] = {colors:['#91BFDB', '#FC8D59']};

    chartGeoChartIDe903d631070 = new google.visualization.ChartWrapper({
    dataTable: data,       
    chartType: 'GeoChart',
    containerId: 'GeoChartIDe903d631070',
    options: options
    });
    chartGeoChartIDe903d631070.draw();
    

}

  function openEditorGeoChartIDe903d631070() {
  var editor = new google.visualization.ChartEditor();
  google.visualization.events.addListener(editor, 'ok',
  function() { 
  chartGeoChartIDe903d631070 = editor.getChartWrapper();  
  chartGeoChartIDe903d631070.draw(document.getElementById('GeoChartIDe903d631070')); 
  }); 
  editor.openDialog(chartGeoChartIDe903d631070);
  }
    
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "charteditor";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartGeoChartIDe903d631070);
})();
function displayChartGeoChartIDe903d631070() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartGeoChartIDe903d631070"></script>
 
<!-- divChart -->
<input type='button' onclick='openEditorGeoChartIDe903d631070()' value='S&P'/>  
<div id="GeoChartIDe903d631070" 
  style="width: 556; height: 347;">
</div>

---




