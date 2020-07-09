# Default Example 
This example uses basic initialization and is the method that requires the least amount of setup. This uses the default minimized Sidekick button which can be setup as an icon or text and is configured within the Sidekick settings.

![Default Button Image](/default_button.png =1/5x)


```html

  
<!DOCTYPE html>
<html>
  <head>
    <meta charset='utf-8'>
    <title>Gladly Sidekick Default Example</title>

    <!-- 
      Sidekick can be initialized in two different way, this is the simplest way to initialize but does not
      offer granular control when Sidekick has been loaded. 
     -->
    <script type="text/javascript">
      window.gladlyConfig = {
          appId: '',  // This is a value you will be given by Gladly and is specific to each customer.
      };
    </script>

</head>
  <body>
    <h1>Gladly Sidekick Default Example</h1>
    <div><span>This page illustrates how Gladly Sidekick can be setup using the default behaviour.</span></div>

    <!-- 
      The Sidekick script is added in the HTML <body> section, this allows the rest of the page to display while Sidekick is loading.
    -->
    <script>
      !function(c,n,r,t){if(!c[r]){var i,d,p=[];d="PROD"!==t&&t?"STAGING"===t?"https://cdn.gladly.qa/gladly/chat-sdk/widget.js":t:"https://cdn.gladly.com/chat-sdk/widget.js",c[r]={init:function(){i=arguments;var e={then:function(t){return p.push({type:"t",next:t}),e},catch:function(t){return p.push({type:"c",next:t}),e}};return e}},c.__onHelpAppHostReady__=function(t){if(delete c.__onHelpAppHostReady__,(c[r]=t).loaderCdn=d,i)for(var e=t.init.apply(t,i),n=0;n<p.length;n++){var a=p[n];e="t"===a.type?e.then(a.next):e.catch(a.next)}},function(){try{var t=n.getElementsByTagName("script")[0],e=n.createElement("script");e.async=!0,e.src=d+"?q="+(new Date).getTime(),t.parentNode.insertBefore(e,t)}catch(t){}}()}}
      (window,document,'Gladly','PROD') // Note 'PROD' to the left indicate to use Production, if 'STAGING' is specified Gladly sandbox enviroment will be used.
    </script>
  </body>
</html>

```
