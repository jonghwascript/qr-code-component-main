# 배운점
## 대체 텍스트가 누락되었습니다
이미지를 볼 수 없는 사용자를 위해 이미지에 대한 대체 텍스트를 제공해야 합니다.

대신:
```
<img src="profile.jpg">
```
사용:
```
<img src="profile.jpg" alt="Sarah Chen, Senior Developer">
```
장식용 이미지의 경우, alt 속성을 비워 두세요.
```
<img src="decorative-border.svg" alt="">
```

## BEM 네이밍 규칙
1. Block (블록)
독립적으로 존재할 수 있고, 재사용 가능한 가장 큰 덩어리(컴포넌트)입니다.
ex) .card, .btn, .header, .navy

2. Element (엘리먼트 / 요소)
블록 안에서 특정 기능을 담당하는 종속된 부품입니다. 부모 블록을 벗어나면 의미를 잃습니다.
- **표기법:** 블록 이름 뒤에 언더바 두 개(`__`)를 붙입니다.
- `.card__title`, `.card__image`, `.btn__icon`

3. Modifier (모디파이어 / 수식어)
블록이나 엘리먼트의 **모양, 색상, 상태**를 약간 다르게 변경할 때 덧붙이는 옵션입니다
- 형태/색상 변경: `.card--supervisor` (슈퍼바이저 스타일의 띠지가 둘러진 카드), `.btn--primary` (메인 색상 버튼)
- 상태 변경: `.btn--disabled` (클릭을 막아둔 회색 버튼)


### 실무 BEM 핵심 규칙 (가장 많이 하는 실수 3가지)
**1. 하위 요소를 족보처럼 깊게 파고들지 않습니다 (손자 금지)**
- 나쁜 예: `.card__content__price-group__current-price` (수정하기 매우 힘들어짐)
- ✅ 좋은 예: `.card__price-current` (카드의 현재 가격이라는 것만 알면 충분함)

**2. Modifier는 반드시 원본 클래스와 함께 씁니다**
- ❌ 나쁜 예: `<article class="card--supervisor">`
- ✅ 좋은 예: `<article class="card card--supervisor">` (카드 뼈대를 잡고, 그 위에 슈퍼바이저 색상을 덧칠함)

**3. 단어와 단어 사이는 하이픈 한 개(`-`)로 연결합니다**
- ✅ 좋은 예: `.team-builder__title`, `.card__price-group`
