# Gladly Sidekick Examples
These are examples of different ways you can configure the Gladly Sidekick on web. 
You can view the Sidekick developer documentation [here](https://developer.gladly.com/sidekick/).

## Default setup
If no customization is needed and you want to the most straightfoward setup. 

[View Example](docs/default)

## Custom minimized button
This is an example of how you can customize the look of the minimized chat button. 

If Sidekick detects there is an element with ID = "custom-gladly-chat-button", the default minimized button will not be shown. Instead it's up to the owner of the website to define the minimized button experience with their own HTML. This example uses basic initialization. 

[View Example](docs/custom-minimized-button)

## Working with events
This is an example of how the events that Sidekick is emitting can be used. This can be useful if you want to track Sidekick interactions within an analytics platform such as [Google Analytics](https://developers.google.com/analytics/devguides/collection/analyticsjs/events). 

To subscribe to events Sidekick must be first be initialized and be ready to use. To know when Sideick is initialized and ready to be used, we make use of the manual initialization method.

[View Example](docs/working-with-events)
