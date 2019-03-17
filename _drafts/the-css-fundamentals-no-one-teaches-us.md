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

## 2. Every box is laid out in 'the flow' by default

[picture of rows of boxes]

There are different types of boxes in our toolbox. Inline boxes, block boxes, flex boxes, grid boxes, table boxes, list-item boxes, inline-block boxes, inline-grid boxes, inline-flex boxes....

There's quite a lot! But these can be drilled down into two categories:

* Block boxes
* Inline boxes

**Block boxes** are boxes that appear one after the other. This blog post starts with a block containing the heading, a block containing an image, a block containing a paragraph, a block containing a sample of code and so on.

[picture of rows of boxes]

**Inline boxes** are boxes that appear - as their name would suggest - within lines of text. If some text is _emphasised_, that means it is in a inline box with the CSS property `font-style: italic` set on it.

[picture of rows of text]

The CSS `display` property is what's used to set which type of box a box will be.

```css
.poster-image {
  display: block
}
```

So what about all those other types of boxes like `grid`, `flex` and `table`? This is where it gets a bit confusing, because they aren't actually the types of boxes; they set how the boxes inside that box are laid out! Recently, the way the `display` property works got updated to better reflect this. You can now specify a _display-outer_ and _display-inner_.

For example, `display: block` is the same as writing `display: block flow`. `block` is the _display-outer_ (the type of block) and `flow` is the _display-inner_ (the way that the boxes inside are laid out). The `flow` value is the default layout method that we're used to, where all blocks appear one after the other. But we could change it to `grid`, enabling things to be laid out very differently! You can read up on different layout methods on [MDN](https://developer.mozilla.org/).

## 3. Every box follows the Box Model

## 4. Margins can overlap each other!

This one throws everyone off guard! 

## 5. The browser has a default HTML stylesheet
