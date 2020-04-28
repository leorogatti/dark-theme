# Light and Dark theme.

A small project to demonstrate a light and dark theme with CSS and Javascript.

![](https://user-images.githubusercontent.com/57969961/80432204-e3361d80-88c9-11ea-8e44-b76e4b7ee5c1.gif)

## How it works?

Well, in CSS I declared the variables:

```CSS 
html {
  --bg: #FCFCFC;
  --bg-panel: #EBEBEB;
  --color-headings: #ff0000; 
  --color-text: #333333;  
}
```
and applied them in the website's light colors.



### First, in JavaScript i caught the documents:

```JavaScript 
const html = document.querySelector("html")
const checkbox = document.querySelector("input[name=theme]")
```



I get the ***Light theme*** with two variables,

```JavaScript
const getStyle = (element, style) =>
  window
    .getComputedStyle(element);
    .getPropertyValue(style);

const initialColors = {
  bg: getStyle(html, "--bg"),
  bgPanel: getStyle(html, "--bg-panel"),
  colorHeadings: getStyle(html, "--color-headings"),
  colorText: getStyle(html, "--color-text"),
}
```



**And to make the *dark theme* i changed the colors using the CSS variables in JavaScript** 

```JavaScript 
const darkMode = {
  bg: "#333333",
  bgPanel: "#434343",
  colorHeadings:"#ff3838",
  colorText: "#B5B5B5",
}
```



**To change the colors I used the variables:**

```JavaScript
const transformKey = key => "--" + key.replace(/([A-Z])/, "-$1").toLowerCase()


const changeColors = (colors) => {
   Object.keys(colors).map(key =>
      html.style.setProperty(transformKey(key), colors[key])
    )
}
```



### And finally to apply the dark colors i added an *Event Listener* in input:

```JavaScript
checkbox.addEventListener("change", ({target}) => {
  target.checked ? changeColors(darkMode) : changeColors(initialColors) 
})
```





## I learned how to do this with the [Rocketseat](https://www.youtube.com/watch?v=BvhYm0BOLvA) Dark Theme video
![](https://user-images.githubusercontent.com/57969961/80435678-9b1bf880-88d3-11ea-89c3-480ddeceab9c.png)

# -*Thanks for Read*
