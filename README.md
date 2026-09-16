# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Code review takeaways](#code-review-takeaways)
  - [Submission checklist](#submission-checklist)
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

- **Block:** An independent, reusable component, such as `.qr-card` or `.btn`.
- **Element:** A part that belongs to a block, joined with two underscores, such as `.qr-card__title` or `.btn__icon`.
- **Modifier:** A variation in appearance or state, joined with two hyphens, such as `.btn--primary` or `.btn--disabled`.

```html
<article class="qr-card">
  <img src="./images/image-qr-code.png" alt="QR code to visit the Frontend Mentor website" class="qr-card__image" />
  <div class="qr-card__content">
    <h1 class="qr-card__title">...</h1>
    <p class="qr-card__description">...</p>
  </div>
</article>
```

Three practical rules help keep BEM names consistent:

1. Keep element names flat instead of mirroring every level of HTML nesting: use `.card__price-current` instead of `.card__content__price-group__current-price`.
2. Add modifiers alongside the original class: use `<article class="card card--supervisor">` instead of `<article class="card--supervisor">`.
3. Join words within a name with a single hyphen, as in `.team-builder__title` or `.card__price-group`.

#### Alternative text for images

Meaningful images need alternative text that conveys their information or purpose to users who cannot see them. For example, a profile image can identify the person and their role:

```html
<img src="profile.jpg" alt="Sarah Chen, Senior Developer">
```

For purely decorative images, provide an empty `alt` attribute so screen readers can skip them:

```html
<img src="decorative-border.svg" alt="">
```

### Code review takeaways

The collected code review feedback provides the following guidelines for this component. These are review points to verify, rather than a record of completed fixes.

1. **Use `rem` for font sizes.** Relative font sizes respect the user's default browser font size. With a 16px root font size, 12px is `0.75rem`, 15px is `0.9375rem`, and 22px is `1.375rem`.
2. **Separate layout defaults from typography.** Apply `box-sizing: border-box` through the universal selector, and declare `font-family` and the base `font-size` on `body`.
3. **Remove development-only styles.** Remove the resizing demo's `resize: horizontal`, `overflow: hidden`, dashed debug border, and related comments before submission.
4. **Check dimensions against the reference design.** Aim for an approximately 288px square QR image at the reference size, verify card padding and border radius, and make the title visually distinct from the body text.
5. **Keep the image flexible.** Combine `width: 100%`, `max-width: 288px`, and `aspect-ratio: 1` so the QR image can shrink within its container while remaining square.
6. **Match the document language to the content.** Use `<html lang="en">` for the English page so screen readers use the appropriate pronunciation rules, and give the page a descriptive title such as `QR Code Component`.
7. **Provide a main landmark.** Wrap the primary content in `<main>` to support screen-reader landmark navigation.
8. **Describe the QR image's purpose in its alternative text.** Explain its destination, for example `alt="QR code to visit the Frontend Mentor website"`, instead of only saying `QR code`.
9. **Proofread the text.** Check spelling before submission, including using `front-end` instead of `font-end`.

### Submission checklist

Use this checklist for a final review; unchecked items do not indicate confirmed defects.

- [ ] Font sizes use `rem` units.
- [ ] Development-only styles and comments have been removed.
- [ ] The document's `lang` attribute matches the content language.
- [ ] The primary content has a `<main>` landmark.
- [ ] The image's `alt` text explains its purpose or destination.
- [ ] Dimensions match the reference design.
- [ ] Text has been checked for spelling mistakes.

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
