<link rel="stylesheet" href="styles.css" />
<button class="cta-button">Learn More</button>
.cta-button {
  background-color: orange;
  border: none;
  padding: 10px 30px;
  cursor: pointer;
  position: relative;
}

.cta-button::after {
  content: "➡️";
  position: absolute;
  right: 5px;
  bottom: 6px;
  font-size: 1.125rem;
  transition: transform 0.3s ease;
}

.cta-button:hover::after {
  transform: translateX(2px);
}
With transform: translateX(2px) in the hover state, the content gets pushed to the right by 2px any time the user hovers on the button. The transition property in the ::after itself ensures the process takes 0.3s.

That's what the transform property does – it allows you to rotate, skew, scale, or translate an element in a particular direction. You will learn more about that in future lessons.

In the next example, we will look at the ::first-letter pseudo-element. The ::first-letter pseudo-element targets the first letter of an element's content, allowing you to style it. Here's an example of some paragraph text. If we want to style the first letter, we can use the ::first-letter pseudo-element like this:

<link rel="stylesheet" href="styles.css" />
<p>freeCodeCamp lets you learn to code without having to pay.</p>
p::first-letter {
  font-size: 4rem;
}
In the last example, we will look at the ::marker pseudo-element, which lets you select the marker, bullet or numbering of list items for styling. The ::marker pseudo-element offers a way to enhance your website's brand identity by customizing list markers to match your color scheme.

Here's an example of an unordered list and an ordered list. To change the list item's marker color and size, you can use the ::marker pseudo-element like this:

<link rel="stylesheet" href="styles.css" />
<ul>
  <li>Unordered list item 1</li>
  <li>Unordered list item 2</li>
  <li>Unordered list item 3</li>
  <li>Unordered list item 4</li>
</ul>

<ol>
  <li>Ordered list item 1</li>
  <li>Ordered list item 2</li>
  <li>Ordered list item 3</li>
  <li>Ordered list item 4</li>
</ol>
li::marker {
  color: crimson;
  font-size: 1.5em;
  font-weight: bold;
}
In this lesson, we have covered only a few pseudo-elements. But there are many more like the ::placeholder, ::spelling-error and ::selection that I encourage you to explore on your own.
