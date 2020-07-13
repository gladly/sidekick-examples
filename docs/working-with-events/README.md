# Working with Events
The following examples illustrate how to make use of the number of events that Sidekick emits. The full list of events that Sidekick emits can be found [here](https://developer.gladly.com/sidekick/Gladly.html#event:availability:change). 

To subscribe to events Sidekick must be first be initialized and be ready to use. To know when Sideick is initialized and ready to be used you should make use of the [manual initialization](https://developer.gladly.com/sidekick/) method. The Sidekick API uses Javascript Promises to signal that Sidekick has been initialized. More information about Promises can be found [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). This script MUST be inserted after the Sidekick load script above. A full setup example can be found [here](working-with-events/example.html)

**Simple Event Example**
```javascript 
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


