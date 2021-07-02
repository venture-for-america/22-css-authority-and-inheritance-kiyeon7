#  CSS Authority and Inheritance

## Overview

In this lesson we will do a quick review of CSS authority and inheritance from the video lecture in the prior lesson.

## What's Covered in This Lesson 

1. Review CSS Authority
2. Review CSS Inheritance

### Authority

It is common when we are styling our HTML pages that we might accidentally write two selectors that are targeting the same element. Let's say for example you intend all `<h1>` level 1 headings to have light blue text, but you also gave some of the headings a class of intro `<h1 class="intro">` and these intro headings should have the text color of dark blue instead. What happens to the `<h1 class="intro">` elements? Will they have light blue or dark blue text? Fortunately CSS has rules that determine which selector wins. The strength of a selector to override another is known as authority. In CSS the more specific a selector, the more authority it carries.

```css
h1 {
  color: lightblue;
}

.intro {
  color: darkblue;
}
```

In the CSS code above, our first selector `h1` selects all level 1 headings whereas our second selector `.intro` selects elements that have the specific class of `intro` applied. In the case of the following html which will beat the other?

```html
<h1 class="intro">Welcome</h1>
```

In this case, a class is more specific as it is applied to only certain h1, whereas selecting all h1s is very general. Thus classes like `.intro` have more authority than a type selector such as `h1`. The end result is that the heading has dark blue text instead of light blue. The general rule is that descendent overrides id which overrides class which overrides type which overrides universal. 

If there are two selectors of equal authority the one that is written further down the page (closer to the bottom) will win. This is the last man rule.

See the link in the resources at the bottom of the lesson to explore CSS selector authority in more detail.

#### Inheritance

Certain CSS styles are inherited from a parent down to its child elements. One such example is most of the typography properties. We will discuss these in more detail below, but just to give you a quick example let's say we add the `font-family: Arial;` to a `ul` unordered list.

```css
ul {
    font-family: Arial;
}
```

```html
<ul>
    <li>Apples</li>
    <li>Oranges</li>
    <li>Bananas</li>
</ul>
```

In this case, all the `li` list items that are children of the `ul` will inherit the Arial font from their `ul` parent simply by being inside of it.

Certain properties like `font-family` can be inherited by a parent. However other properties by default are not directly inherited. See below, for example.

```css
ul {
  border: 1pc solid black;
}
```

A border will only affect the `ul` it is applied to and the `li` will not inherit the border by default. It is good to know which properties are inherited and which are not. There are also some CSS values that allow us to change the defualt behavior of inheritance.

## Summary

- The more specific a selector, the more authority it has.
- Some properties are inherited from a parent element and others are not.

## Resources

- [MDN - CSS Tutorials for Beginners](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started)
- [MDN - CSS Property Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [MDN - CSS Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance)
- [CSS Authority, Specificity](https://www.youtube.com/watch?v=In78mSOHmls&feature=youtu.be)
- [CSS Performance & Organization, Best Practices](http://learn.shayhowe.com/advanced-html-css/performance-organization/)
