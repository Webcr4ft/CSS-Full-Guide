# What Are CSS Animations, and How Do They Work?

CSS animations allow you to create dynamic, visually engaging effects on web pages without the need for JavaScript or complex programming.

They provide a way to smoothly transition elements between different styles over a specified duration.

At its core, a CSS animation consists of two main components:

* The `@keyframes` rule
* The `animation` property

## The @keyframes Rule

The `@keyframes` rule defines the stages and styles of the animation.

It specifies what styles the element should have at various points during the animation.

Here's an example:

`@keyframes slide-in {
  0% {
    transform: translateX(-100%);
  }

  100% {
    transform: translateX(0);
  }
}`

This `@keyframes` rule, named `slide-in`, defines an animation that moves an element from left to right.

The percentages represent the progress of the animation:

* `0%` represents the start of the animation.
* `100%` represents the end of the animation.

The `translateX()` function in the `@keyframes` animation controls the horizontal position of an element as it animates into view.

## Applying an Animation

To apply this animation to an element, you use the `animation` property.

This example also repeats the animation infinitely so you can see it in action:

### HTML

`<link rel="stylesheet" href="styles.css">

<div class="sliding-element">Hello, I slide in!</div>`

### CSS

`@keyframes slide-in {
  0% {
    transform: translateX(-100%);
  }

  100% {
    transform: translateX(0);
  }
}

.sliding-element {
  animation: slide-in 2s ease-out infinite;
}`

This applies the `slide-in` animation to the element with a duration of `2` seconds and an `ease-out` timing function.

## The Animation Property

The `animation` property is actually a shorthand for several individual properties:

* `animation-name` specifies the `@keyframes` rule to use.

* `animation-duration` sets how long the animation should take to complete.

* `animation-timing-function` defines how the animation progresses over time, such as `ease`, `linear`, and `ease-in-out`.

* `animation-delay` specifies a delay before the animation starts.

* `animation-iteration-count` sets how many times the animation should repeat.

* `animation-direction` determines whether the animation should play forwards, backwards, or alternate.

* `animation-fill-mode` specifies how the element should be styled before and after the animation.

* `animation-play-state` allows you to pause and resume the animation.

## Using Animation Properties Individually

You can use these properties individually for more precise control:

### HTML

`<link rel="stylesheet" href="styles.css">

<div class="complex-animation">Watch my colors change!</div>`

### CSS

`.complex-animation {
  animation-name: color-change;
  animation-duration: 3s;
  animation-timing-function: linear;
  animation-delay: 1s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}

@keyframes color-change {
  0% {
    background-color: red;
  }

  50% {
    background-color: blue;
  }

  100% {
    background-color: green;
  }
}`

This creates an animation that continuously transitions an element's background color between red, blue, and green.

## CSS Animations and User Interaction

CSS animations can be triggered or controlled through various states and events, such as hovering over an element.

For example:

### HTML

`<link rel="stylesheet" href="styles.css">

<button class="button">Hover over me!</button>`

### CSS

`.button {
  background-color: blue;
  transition: background-color 0.3s;
}

.button:hover {
  background-color: red;
}`

While this example uses the `transition` property, which is simpler for basic effects, it demonstrates how CSS can create interactive, animated elements.

## CSS Animations vs. Transitions

CSS animations and transitions are related but serve different purposes.

* **CSS animations** use `@keyframes` to define multiple stages of an animation and can run automatically or repeat.
* **CSS transitions** smoothly animate a property when its value changes, such as when an element is hovered.

For simple effects, transitions are often enough. For more complex or repeated animations, `@keyframes` and CSS animations provide greater control.

## Accessibility and Performance

It's important to note that while CSS animations are powerful, they should be used in moderation.

Overuse of animations can:

* Lead to poor performance.
* Distract users.
* Create accessibility issues for users who are sensitive to motion.

Always consider providing options to reduce or disable animations for users who prefer less motion.

CSS provides the `prefers-reduced-motion` media feature to detect when a user has requested reduced motion:

`@media (prefers-reduced-motion: reduce) {
  .animated-element {
    animation: none;
  }
}`

## Conclusion

CSS animations offer a way to create engaging, interactive web experiences without relying on JavaScript.

By understanding the principles of `@keyframes` and the `animation` properties, you can bring your web designs to life in a performant and accessible manner.
