# Websheets: use a Google Documents spreadsheet as a basic website back-end/CMS

##What is a Websheet?
A Websheet is a fully customizable Website that you edit any time, anywhere by simply updating a Google Sheet. 

The Websheet is a cool, single page, multi-sectioned site. See demo: boulton.co

Edit your website from any device.

##Main features
-As simple as editing text in a spreadsheet
-Add and remove sections to customize your site
-Unlimited formatting: you may include custom Markdown or HTML in your content
-Fully customizable - edit the CSS and script files provided or use one of the two themes
-Get creative with dynamic data: if it's in your Sheet it can be on your site

## Step-by-step

## Getting started

1. The key ingredient to Websheets is the spreadsheet. This is your website's backend!
2. Download websheets.zip and upload the included files to a web server. Or you can work on things locally.

```javascript
loadSpreadsheet(url,complete,id,requestNumber) {

$('#statusBar').show();
setTimeout(function() {
$.getJSON('https://spreadsheets.google.com/feeds/list/'+url+'/1/public/values?alt=json&callback=?').done(function(data) {
complete(data,id,requestNumber);
if(requestNumber==dynamicArticles.length-1){
console.log('request number is '+requestNumber+' and number of dynamic articles minus 1 is, therefore complete\? '+dynamicArticles.length);
dataLoaded='true';
setTimeout(function(){dataLoadedFunctions()},1000);
}
});
},500);
}
```
