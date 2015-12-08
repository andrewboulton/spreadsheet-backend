# Websheets: use a Google Documents spreadsheet as a basic website back-end/CMS

##What is a Websheet?
A Websheet is a fully customizable Website that you edit any time, anywhere by simply updating a Google Sheet. 

The Websheet is a cool, single page, multi-sectioned site. See demo: boulton.co

Edit your website from any device.

##Main features
*As simple as editing text in a spreadsheet
*Add and remove sections to customize your site
*Unlimited formatting: you may include custom Markdown or HTML in your content
*Fully customizable - edit the CSS and script files provided or use one of the two themes
*Get creative with dynamic data: if it's in your Sheet it can be on your site

##Coming soon
*Flickr image galleries

## Getting started

There are two requirements: 1. the spreadhseet and 2. the website files
### The spreadsheet
1. Upload the file *content.xslx* to Google Documents
2. Publish the file


## The website files
1. Extract the *websheets.zip* file and upload to a web server. (You may also work on your site locally.)

## Link the spreadhseet and website files
This is the only step that requires you to 

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
