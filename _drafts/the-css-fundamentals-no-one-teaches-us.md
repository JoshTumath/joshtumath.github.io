# The CSS fundamentals no one teaches us

[picture of someone scratching their head with a toolbox]

When learning to develop for the Web, do you ever feel like you're being taught about all the tools in a toolbox, but not how to actually use them? It's all well and good knowing how to drill a hole, but how do you go from that to using the drill, and the screwdriver, and the winch, and the hammer to make a kitchen?

That's how I felt when I was learning CSS ten years ago. It's empowering to know how to make the font size bigger, centre the text and float an image to the left, but how do you make boxes appear side-by-side (there was no flex box in those days)? And how do you stop `position: absolute` content from being positioned relative to the whole? And why is it that when I add a margin to a `div` element, it works, but when I add a margin to an `a` element, nothing happens?

Without a grasp of the fundamentals of how CSS works, most of the many 'tools' we have in CSS don't make any sense. It making CSS seem very complicated and difficult to master if you're new to Web development, whether you're new to programming in general or you come from an app development background.

These are three foundational things that I think make CSS much easier to understand once you're aware of them.

## 1. Everything is a box

[picture of DOM tree and boxes]

When crafting HTML, your user's Web browser parses this and creates the DOM, or Document Object Model. This is a tree of all the HTML elements on a page. The browser then takes all of these elements in the DOM, and turns them into boxes!

Unless an element is hidden, it will be rendered as a rectangular box. Whether it's a `table` element, a `div` element, a `p` (paragraph) element, an `li` (list item) element or even a little `em` (emphasised text) element, it will get turned into a box by the browser.

We can see this for ourselves by adding a border around every element.

```css
* {
  border: thin solid red;
}
```

## 2. Everything is part of 'the flow' by default

## 3. Every box follows the Box Model

## 4. Margins can overlap each other!
