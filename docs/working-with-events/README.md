# Working with events
This example illustrates how to make use of the number of events that Sidekick emits. The full list of events that Sidekick emits can be found [here](https://developer.gladly.com/sidekick/Gladly.html#event:availability:change). 

**Simple Event Example**

To subscribe to events Sidekick must be first be initialized and be ready to use. To know when Sideick is initialized and ready to be used we make use of the manual initialization method. 
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset='utf-8'>
    <title>Gladly Sidekick Working With Events Example</title>
</head>
  <body>
    <h1>Gladly Sidekick Working With Events Example</h1>
    <div><span>This page illustrates how Gladly Sidekick can be setup and consume events</span></div>

    <!-- 
      The Sidekick load script is added in the HTML <body> section, this allows the rest of the page to display while Sidekick is loading.
    -->
    <script>
      !function(c,n,r,t){if(!c[r]){var i,d,p=[];d="PROD"!==t&&t?"STAGING"===t?"https://cdn.gladly.qa/gladly/chat-sdk/widget.js":t:"https://cdn.gladly.com/chat-sdk/widget.js",c[r]={init:function(){i=arguments;var e={then:function(t){return p.push({type:"t",next:t}),e},catch:function(t){return p.push({type:"c",next:t}),e}};return e}},c.__onHelpAppHostReady__=function(t){if(delete c.__onHelpAppHostReady__,(c[r]=t).loaderCdn=d,i)for(var e=t.init.apply(t,i),n=0;n<p.length;n++){var a=p[n];e="t"===a.type?e.then(a.next):e.catch(a.next)}},function(){try{var t=n.getElementsByTagName("script")[0],e=n.createElement("script");e.async=!0,e.src=d+"?q="+(new Date).getTime(),t.parentNode.insertBefore(e,t)}catch(t){}}()}}
      (window,document,'Gladly','PROD') // Note 'PROD' to the left indicate to use Production, if 'STAGING' is specified Gladly sandbox enviroment will be used.
    </script>

    <!-- 
      In this example Sidekick is initialized with Sidekick API, it uses Javascript Promises to signal that Sidekick has been initialized. 
      More information about Promises can be found here: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise
      This script MUST be inserted after the Sidekick load script above.
    -->
    <script>
      Gladly.init({
        appId: '', // This is a value you will be given by Gladly and is specific to each customer.
      }).then(() => {
          /**
            The function inside 'then()' will be called once Sidekick is fully initialized and ready to be used.
            Events can only be subscribed to after Sidekick has been initialized and ready to be used.
          */
          Gladly.on('message:sent', (e) => {
            console.log(`User sent a message with type: ${e.type}`);
          });

      }).catch((error) => {

        console.log(error);

      });
    </script>
  </body>
</html>
```

**Sending Events to Google Analytics**

This is a simple example of how the events can be sent to Google Analytics. This document provides more details on how to work with custom events in Google Analytics.
```javascript
Gladly.init({
    appId: '', // This is a value you will be given by Gladly and is specific to each customer.
}).then(() => {
    /**
      The function inside 'then()' will be called once Sidekick is fully initialized and ready to be used.
      Events can only be subscribed to after Sidekick has been initialized and ready to be used.
    */
    Gladly.on('message:sent', (e) => {
        ga('send', 'event', {
            eventCategory: 'gladlySidekick',
            eventAction: 'message sent',
        });
    });

}).catch((error) => {

    console.log(error);

});
```


