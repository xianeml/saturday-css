Learn CSS 02: Selectors [(https://web.dev/learn/css/selectors/)](https://web.dev/learn/css/selectors/)
아티클 엘리먼트 안에 있는 p태그 중에 첫번째 애한테만 스타일 주고싶을 때 어케 선택하냐!

- `article p:first-of-type { color: red; }`

- universal selector 전체선택자(\*) : 모든 요소에 적용
- type selector : html 태그 선택
- class selector
- id selector
- attribute selector 특성 선택자:

  - 특정 html 속성을 가진 요소를 선택함
  - 속성을 대괄호로 래핑해서 css 작성

  ```jsx
  <div data-type="primary"></div>

  [data-type='primary'] {
    color: red;
  }

  // 굳이 값으로 안찾고 이 속성 가진애들 모두 선택
  [data-type] {
    color: red;
  }

  // 속성값 소문자만 취급함
  [data-type='primary' s] {
    color: red;
  }

  // 속성값 대문자만 취급함
  [data-type='primary' i] {
    color: red;
  }

  // 문자열 걸러서 선택할수도 있음
  /* A href that contains "example.com" */
  [href*='example.com'] {
    color: red;
  }

  /* A href that starts with https */
  [href^='https'] {
    color: green;
  }

  /* A href that ends with .com */
  [href$='.com'] {
    color: blue;
  }
  ```

### 수도 클래스

- a:hover
- p:nth-child(even)

### 수도 엘리먼트

- :: 더블콜론

### 하위 선택자

- 하위 엘리먼트를 선택할때 p > strong 이라면 p strong 띄어쓰기로 선택
