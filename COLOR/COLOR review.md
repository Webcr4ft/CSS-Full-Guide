
==================================================
CSS COLORS REVIEW
==================================================

# COLOR THEORY

## Color Theory Definition
Color theory is the study of how colors interact with each
other and how they affect our perception.

It covers:
- Color relationships
- Color harmony
- Psychological impact of color

## Primary Colors
Primary colors are the fundamental hues from which other
colors are derived.

- Yellow
- Blue
- Red

## Secondary Colors
Secondary colors result from mixing equal amounts of two
primary colors.

- Green
- Orange
- Purple

## Tertiary Colors
Tertiary colors result from combining a primary color with
a neighboring secondary color.

Examples:
- Yellow-Green
- Blue-Green
- Blue-Violet

## Warm Colors
Warm colors include:
- Red
- Orange
- Yellow

They can evoke feelings of comfort, warmth, and coziness.

## Cool Colors
Cool colors include:
- Blue
- Green
- Purple

They can evoke feelings of calmness, serenity, and
professionalism.

## Color Wheel
The color wheel is a circular diagram that shows how colors
relate to each other.

It is an essential tool for designers because it helps them
select effective color combinations.

## Analogous Color Schemes
Analogous colors are adjacent to each other on the color
wheel.

They create cohesive and soothing visual experiences.

## Complementary Color Schemes
Complementary colors are located on opposite ends of the
color wheel.

They create high contrast and strong visual impact.

## Triadic Color Scheme
A triadic color scheme uses three colors that are approximately
equidistant from each other on the color wheel.

When connected, the colors form an equilateral triangle.

Triadic schemes create vibrant color combinations.

## Monochromatic Color Scheme
A monochromatic color scheme uses colors derived from the
same base color.

Contrast is created by adjusting:
- Lightness
- Darkness
- Saturation

This creates unity and harmony while maintaining contrast.


==================================================
DIFFERENT WAYS TO WORK WITH COLORS IN CSS
==================================================

# NAMED COLORS

Named colors are predefined color names recognized by browsers.

Examples:
- blue
- darkred
- lightgreen

Example:

.example-named-color {
  color: blue;
}


==================================================
# RGB FUNCTION
==================================================

RGB stands for Red, Green, and Blue.

The rgb() function defines colors using the RGB color model.

Each value represents the intensity of:
- Red
- Green
- Blue

Example:

.rgb-color {
  color: rgb(255, 0, 0);
}


==================================================
# RGBA FUNCTION
==================================================

The rgba() function adds a fourth value called alpha.

The alpha value controls transparency.

An alpha value of:
- 1 = completely opaque
- 0 = completely transparent
- 0.5 = 50% transparent

Example:

.rgba-background {
  background-color: rgba(0, 0, 255, 0.5);
}


==================================================
# HSL FUNCTION
==================================================

HSL stands for:
- Hue
- Saturation
- Lightness

The hsl() function defines colors using these three
components.

Modern CSS syntax can also include an optional alpha value
using the / separator.

Example:

.hsl-color {
  color: hsl(120 100% 50%);
}

.hsl-alpha {
  color: hsl(120 100% 50% / 0.8);
}


==================================================
# HSLA FUNCTION
==================================================

The hsla() function is a legacy way of adding transparency
to HSL colors.

Modern CSS generally prefers hsl() with the / separator.

Example:

.hsla-background {
  background-color: hsla(0, 100%, 50%, 0.5);
}


==================================================
# HEXADECIMAL COLORS
==================================================

A hexadecimal color code represents a color using the RGB
color model.

Hexadecimal uses a base-16 numbering system containing:

0 1 2 3 4 5 6 7 8 9 A B C D E F

A full hexadecimal color normally contains six characters.

Example:

#F498A2

A three-character shorthand can also be used.

For example:

#2FB

is equivalent to:

#22FFBB

Example:

.hex-text {
  color: #FF5733;
}

.hex-background {
  background-color: #4CAF50;
}


==================================================
# THE BOX-SHADOW PROPERTY
==================================================

The box-shadow property applies one or more shadows around
an element.

Syntax:

box-shadow: offset-x offset-y blur-radius spread-radius color;

## Offset Values

The horizontal offset is called offset-x.

- Positive values move the shadow right.
- Negative values move the shadow left.

The vertical offset is called offset-y.

- Positive values move the shadow down.
- Negative values move the shadow up.

If the value is 0, a unit is not required.

## Blur Radius

The blur radius controls how blurry the shadow appears.

If omitted, it defaults to 0 and creates sharp edges.

Higher values create softer shadows.

## Spread Radius

The spread radius controls how much the shadow expands
or shrinks.

If omitted, it defaults to 0.

## Shadow Color

Shadow colors can use:

- Named colors
- Hexadecimal colors
- rgb()
- rgba()
- hsl()
- hsla()

## Inset Keyword

The inset keyword places the shadow inside the element
instead of outside.

Example:

.shadow-box {
  width: 200px;
  padding: 20px;
  background-color: lightblue;
  box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.5);
}


==================================================
# MULTIPLE BOX SHADOWS
==================================================

Multiple shadows can be applied by separating each shadow
with a comma.

Shadows are layered from front to back.

Example:

.multiple-shadows {
  box-shadow:
    5px 5px 10px rgba(0, 0, 0, 0.3),
    -5px -5px 10px rgba(255, 255, 255, 0.5);
}


==================================================
# LINEAR GRADIENTS
==================================================

Linear gradients create a gradual blend between colors
along a straight line.

The direction can be controlled using:

- to top
- to right
- to bottom
- to left
- to bottom right
- Angles such as 45deg

You can use any valid CSS color and as many color stops
as needed.

Example:

.linear-gradient {
  background: linear-gradient(
    45deg,
    red,
    #33FF11,
    rgba(100, 100, 255, 0.5)
  );

  height: 40vh;
}


==================================================
# RADIAL GRADIENTS
==================================================

Radial gradients create circular or elliptical gradients
that radiate from a central point.

Example:

.radial-gradient {
  background: radial-gradient(
    circle,
    red,
    blue
  );

  height: 40vh;
}
