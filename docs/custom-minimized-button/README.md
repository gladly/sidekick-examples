# Custom Minimized Button Example
You can customize the minimized chat button that is rendered on your site to better align with your brand. Instead of using the [default button](docs/default), you can code your own. 

![](/custom_1.png) ![](/custom_2.png)

There are a few simple steps to implement a custom minimized chat button.
1. Gladly requires that an HTML id of custom-gladly-chat-button be specified on the outermost HTML element
2. Gladly requires that an onclick handler be bound to the same outermost HTML element
3. The onclick handler will need to call the public Gladly API show

If the HTML custom-gladly-chat-button id is present, Gladly will do the following:
1. decorate that HTML element with a class of gladly-show, when the button should be visible
2. decorate that HTML element with a class of gladly-has-authenticated when a user has authenticated
3. decorate that HTML element with a class of gladly-unread when there are unread messages

It is up to you to utilize these classes and hooks properly to render and style your own custom button as you wish.

