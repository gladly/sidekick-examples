# Custom Minimized Button Example
You can customize the minimized chat button that is rendered on your site to better align with your brand. Instead of using the [default button](docs/default), you can code your own. Below are two examples of custom minimized Sidekick buttons.

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

**SAMPLE HTML**
```html
<div id="custom-gladly-chat-button" onclick="Gladly.show()">
  <div id="gladly-not-authenticated">
    <span>LIVE CHAT</span>
  </div>
  <div id="gladly-authenticated">
    <svg width="18" height="18" fill="none" viewBox="0 0 18 18">
      <path fill="#000" />
    </svg>
    <span class="unread-dot"></span>
   </div>
</div>
```

**SAMPLE CSS**
```css
<style type="text/css">
    #custom-gladly-chat-button {
      visibility: hidden;
    }

    #custom-gladly-chat-button #gladly-not-authenticated {
        visibility: hidden;
    }

    #custom-gladly-chat-button #gladly-authenticated {
        visibility: hidden;
    }

    #custom-gladly-chat-button.gladly-show #gladly-not-authenticated {
        visibility: visible;
    }

    #custom-gladly-chat-button.gladly-show.gladly-has-authenticated #gladly-authenticated {
        visibility: visible;
    }

    #custom-gladly-chat-button.gladly-show.gladly-has-authenticated #gladly-not-authenticated {
        visibility: hidden;
    }

    #custom-gladly-chat-button .unread-dot {
        visibility: hidden;
    }

    #custom-gladly-chat-button.gladly-unread .unread-dot {
        background-color: green;
        border-radius: 50%;
        display: inline;
        height: 8px;
        position: absolute;
        right: 12px;
        top: 8px;
        visibility: visible;
        width: 8px;
    }
</style>
```
