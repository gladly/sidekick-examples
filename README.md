# Gladly Sidekick Examples
These are examples of different ways you can configure the Gladly Sidekick on the web. 

You can view the Sidekick developer documentation [here](https://developer.gladly.com/sidekick/).

To help with exploring the Sidekick functionality a small webserver is included and can be run, for this [Node](https://nodejs.org/) and [NPM](https://www.npmjs.com/) must be installed. 
To run the webserver do the following. 
```
$ npm install
$ npm start
```
visit [http://localhost:3000](http://localhost:3000) in your webbrowser. Don't forget to fill in your appId in the example HTML pages.


## Default Setup
If no customization is needed and you want to use the most straightfoward setup. 

[View Example](docs/default)

## Custom Minimized Button
Gladly allows you to customize the minimized chat button that is rendered on your site to better align with your brand. This is an example of how you can set that up.

[View Example](docs/custom-minimized-button)

## Working with Events
This is an example of how the events that Sidekick is emitting can be used. This can be useful if you want to track Sidekick interactions within an analytics platform such as [Google Analytics](https://developers.google.com/analytics/devguides/collection/analyticsjs/events). 

[View Example](docs/working-with-events)
