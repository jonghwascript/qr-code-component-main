# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)
- [Questions for the community](#questions-for-the-community)

## Overview

### Screenshot

![](./screenshot.jpg)

### Links

- Solution URL: [Add solution URL here](https://github.com/jonghwascript/qr-code-component-main.git)
- Live Site URL: [Add live site URL here](https://jonghwascript.github.io/qr-code-component-main)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Container Queries
- CSS `clamp()` function
- BEM naming convention

### What I learned

#### CSS Container Queries

I implemented a responsive layout that adapts based on the parent element's size using container queries.

```css
.container {
  container-type: inline-size;
  container-name: qr-container;
}
```

#### CSS clamp() for fluid sizing

I created a smoothly resizing layout without breakpoints using the `clamp()` function.

```css
.qr-stage {
  /* Automatically adjusts between 375px and 960px based on container size */
  width: clamp(var(--minWidth), 100%, 960px);
}
```

#### BEM naming convention

I applied the BEM methodology for class naming to clearly express the structure.

```html
<article class="qr-card">
  <img class="qr-card__image" />
  <div class="qr-card__content">
    <h1 class="qr-card__title">...</h1>
    <p class="qr-card__description">...</p>
  </div>
</article>
```

### Continued development

- I want to apply CSS Container Queries to more complex layouts.
- I want to deepen my understanding of semantic HTML tag selection.

### Useful resources

- [PerfectPixel Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi) - This helped me compare the design mockup with the actual implementation pixel by pixel, making it easier to determine exact sizes.
- [MDN - CSS Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_queries) - This helped me understand the concept and usage of container queries.
- [MDN - clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp) - I referenced this to understand how the clamp function works.

### AI Collaboration

- **Tool used**: Claude Code (Anthropic's CLI for Claude)
- **How I used it**:
  - Code review and accessibility checks
  - CSS class naming improvements (applying BEM methodology)
  - Identifying limitations of CSS variables in container query conditions
  - Optimizing responsive layout using the `clamp()` function
- **What worked well**: Through code review, I was able to quickly identify issues such as duplicate code, incorrect lang attribute, and missing style-guide colors.

## Author

- Frontend Mentor - [@jonghwascript](https://www.frontendmentor.io/profile/jonghwascript)

## Questions for the community

I would like feedback on the HTML structure.

- I'm currently using the `<img>` tag standalone. Would it be more appropriate to wrap it with `<figure>`?
- I'm curious if using `<figure>` and `<figcaption>` would be a more semantically correct approach for a QR code image.