# spreadsheet-backend
Uses Google Documents spreadsheet as a basic website CMS/back-end

## Purpose
Create dynamic web pages by editing a spreadsheet using only client-side code.

## Step-by-step

```loadSpreadsheet(url,complete,id,requestNumber) {

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
