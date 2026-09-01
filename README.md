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

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

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

컨테이너 쿼리를 사용하여 부모 요소의 크기에 따라 반응하는 레이아웃을 구현했습니다.

```css
.container {
  container-type: inline-size;
  container-name: qr-container;
}
```

#### CSS clamp() for fluid sizing

`clamp()` 함수를 사용하여 breakpoint 없이 부드럽게 크기가 조절되는 레이아웃을 만들었습니다.

```css
.qr-stage {
  /* 375px ~ 960px 사이에서 컨테이너 크기에 맞게 자동 조절 */
  width: clamp(var(--minWidth), 100%, 960px);
}
```

#### BEM naming convention

클래스 네이밍에 BEM 방식을 적용하여 구조를 명확하게 표현했습니다.

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

- CSS Container Queries를 더 복잡한 레이아웃에 적용해보고 싶습니다.
- 시맨틱 HTML 태그 선택에 대한 이해를 더 깊이 하고 싶습니다.

### Useful resources

- [PerfectPixel Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi) - 디자인 시안과 실제 구현을 픽셀 단위로 비교할 수 있어서 정확한 사이즈를 파악하는 데 도움이 되었습니다.
- [MDN - CSS Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_queries) - 컨테이너 쿼리의 개념과 사용법을 이해하는 데 도움이 되었습니다.
- [MDN - clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp) - clamp 함수의 동작 방식을 이해하는 데 참고했습니다.

### AI Collaboration

- **Tool used**: Claude Code (Anthropic's CLI for Claude)
- **How I used it**:
  - 코드 리뷰 및 접근성 점검
  - CSS 클래스 네이밍 개선 (BEM 방식 적용)
  - 컨테이너 쿼리에서 CSS 변수 사용 제한 사항 확인
  - `clamp()` 함수를 활용한 반응형 레이아웃 최적화
- **What worked well**: 코드 리뷰를 통해 중복 코드, 잘못된 lang 속성, style-guide 색상 미적용 등의 문제점을 빠르게 파악할 수 있었습니다.

## Author

- Frontend Mentor - [@jonghwascript](https://www.frontendmentor.io/profile/jonghwascript)

## Questions for the community

HTML 구조에 대해 피드백을 받고 싶습니다.

- 현재 `<img>` 태그를 단독으로 사용하고 있는데, `<figure>`로 감싸는 것이 더 적절할까요?
- QR 코드 이미지의 경우 `<figure>`와 `<figcaption>`을 사용하는 것이 시맨틱적으로 더 올바른 접근인지 궁금합니다.
