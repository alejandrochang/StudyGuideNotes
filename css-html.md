# CSS & HTML 

### Animations
The animation property can be used to animate CSS properties such as colors, background-color, height and width. Each animation needs to be defined with @keyframes at-rule. The @keyframes rule states what should happen at a specific moment durent the animation.

There are many subproperties that you can use with animations. If an animation has the same starting and ending properties it's useful to comma-separate e values inside @keyframes.

Browser support is quite good for animations, but there are a certain number of performance concerns with certain properties. The ones we that are safe are: trasnsform: translate(), trasnsform: scale(), trasnsform: rotate() and opacity.

```css
.element {
  animation: pulse 5s infinite;
}

@keyframes pulse {
  0% {
    background-color: #001F3F;
  }
  100% {
    background-color: #FF4136;
  }
}
```

### What are the 3 main ways to apply CSS styles to a web page?
1. Using the style attribute on an element.
2. Using a <style> block in the <head> section of your HTML.
3. Loading an external CSS files using the link tag. 

Loading an external CSS files is the most commonly used and the best practice as it creates a separation for concerns.

### What are the different type of selectors and how to target them?
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

### What are pseudo elements used for?

### Why would you want to use a pre-processor like SASS?
