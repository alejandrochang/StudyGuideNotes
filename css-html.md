# CSS & HTML 

### What are the 3 main ways to apply CSS styles to a web page?
1. Using the style attribute on an element.
2. Using a <style> block in the <head> section of your HTML.
3. Loading an external CSS files using the link tag. 

Loading an external CSS files is the most commonly used and the best practice as it creates a separation for concerns.

### What are the different type of selectors?
The main different selectors include tags, classes and ID's.

```js
body { // tags
  width: 100%;
}

<div class="choose-me"></div> // classes
.choose-me {
}

<div id="no-choose-me"></div>

#no-choose-me {
}

```

