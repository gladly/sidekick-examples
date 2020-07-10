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

A new element with ID "custom-gladly-chat-button" is added to the body, CSS will be used to place it where we want on the page. Sidekick will add different classes to the element to tell the button what state Sidekick is in, CSS can then be used to change the apperance of the button to match expectation.
```html
    <button id="custom-gladly-chat-button" onclick="Gladly.show()">
      <div id="with-no-active-chat">
        <span>START NEW CHAT</span>
      </div>
      <div id="with-active-chat">
        <span>CONTINUE EXISTING CHAT</span>
        <div id="with-unread-message">
          <span> (unread message)</span>
        </div>
      </div>
    </button>
```

**SAMPLE CSS**

Position buttom in the lower right corner
```css
#custom-gladly-chat-button {
position: fixed;
padding: 10px;
right: 20px;
bottom: 10px;
}
```
By default we hide the button. 
```css
#custom-gladly-chat-button {
display: none;
}
#custom-gladly-chat-button #with-active-chat {
display: none;
}
#custom-gladly-chat-button #with-unread-message {
display: none;
}
```
If "gladly-show" is there we show the button 
```
#custom-gladly-chat-button.gladly-show {
display: block;
}
```
If user has gone through onboarding the "gladly-has-authenticated" class will be added, we hide the element with the text "START NEW CHAT" and show the element with the text "CONTINUE EXISTING CHAT"
```css
#custom-gladly-chat-button.gladly-has-authenticated #with-no-active-chat {
display: none;
}
#custom-gladly-chat-button.gladly-has-authenticated #with-active-chat {
display: block;
}
#custom-gladly-chat-button.gladly-unread #with-unread-message {
display: block;
}
```
