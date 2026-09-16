# Code Review Notes

QR Code Component 프로젝트에서 받은 코드 리뷰 피드백을 정리한 문서입니다.

---

## CSS

### 1. 폰트 크기는 rem 단위 사용

**문제:** `px`로 폰트 크기를 설정하면 사용자가 브라우저 기본 글꼴 크기를 변경해도 텍스트가 확대되지 않음

**해결:** `rem` 단위 사용 (1rem = 16px 기준)

```css
/* Bad */
font-size: 15px;

/* Good */
font-size: 0.9375rem; /* 15 / 16 */
```

| px | rem |
|----|-----|
| 12px | 0.75rem |
| 15px | 0.9375rem |
| 22px | 1.375rem |

---

### 2. 전역 선택자와 타이포그래피 분리

**문제:** `*` 선택자에 `font-family`와 `box-sizing`을 함께 선언하면 레이아웃과 타이포그래피의 책임이 혼합됨

**해결:** `box-sizing`은 `*`에, 폰트 관련 속성은 `body`에 선언

```css
/* Good */
* {
    box-sizing: border-box;
}

body {
    font-family: "Outfit", sans-serif;
    font-size: 0.9375rem;
}
```

---

### 3. 개발용 스타일 제거

**문제:** 개발 중 사용한 디버깅 스타일이 최종 제출물에 포함됨

**제거해야 할 속성:**
- `resize: horizontal;`
- `overflow: hidden;`
- `border: 2px dashed #bbb;`
- 관련 주석

---

### 4. 디자인 참조값과 일치시키기

**문제:** 임의의 크기값 사용으로 참조 디자인과 불일치

**확인 사항:**
- QR 이미지: 약 288px 정사각형
- 카드 padding, border-radius 등 디자인 스펙 확인
- 제목과 본문의 시각적 구분 (제목은 더 큰 폰트 크기 사용)

---

### 5. 유연한 이미지 크기

**문제:** 고정 크기 이미지는 다양한 뷰포트에서 문제 발생

**해결:** `width: 100%`와 `max-width`, `aspect-ratio` 조합 사용

```css
.image {
    width: 100%;
    max-width: 288px;
    aspect-ratio: 1;
}
```

---

## HTML

### 6. 문서 언어 설정

**문제:** `lang="ko"`로 설정했지만 콘텐츠가 영어 → 스크린 리더가 한국어 발음 규칙 적용

**해결:** 콘텐츠 언어와 `lang` 속성 일치시키기

```html
<!-- 영어 콘텐츠인 경우 -->
<html lang="en">
<title>QR Code Component</title>
```

---

### 7. Main 랜드마크 사용

**문제:** 주요 콘텐츠가 `div`로만 감싸져 있으면 스크린 리더 사용자가 랜드마크 탐색 불가

**해결:** 주요 콘텐츠를 `<main>` 요소로 감싸기

```html
<body>
    <div class="container">
        <main class="content-area">
            <article>...</article>
        </main>
    </div>
</body>
```

---

### 8. 목적 중심의 대체 텍스트

**문제:** "QR 코드"처럼 단순히 이미지를 설명하면 스크린 리더 사용자가 기능을 이해할 수 없음

**해결:** 이미지의 **목적**이나 **목적지**를 설명

```html
<!-- Bad -->
<img alt="QR code">

<!-- Good -->
<img alt="Frontend Mentor 웹사이트로 이동하는 QR 코드">
```

---

### 9. 오타 확인

제출 전 텍스트 콘텐츠의 맞춤법 검토

- `font-end` → `front-end`

---

## Checklist

프로젝트 제출 전 확인 사항:

- [ ] 폰트 크기가 `rem` 단위인가?
- [ ] 개발용 스타일이 제거되었는가?
- [ ] `lang` 속성이 콘텐츠 언어와 일치하는가?
- [ ] `<main>` 랜드마크가 있는가?
- [ ] 이미지 `alt` 텍스트가 목적을 설명하는가?
- [ ] 디자인 참조값과 크기가 일치하는가?
- [ ] 오타가 없는가?
