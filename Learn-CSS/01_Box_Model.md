Learn CSS 01: Box Model ([https://web.dev/learn/css/box-model/](https://web.dev/learn/css/box-model/))

## 내용과 사이즈

css로 보여지는 부분은 다 박스다.

content에 따라서 박스 사이즈가 달라질 수 있는데 아래 얘네들로 조절할수있다.

**`intrinsic` layout: 브라우저가 콘텐츠 사이즈 기반으로 사이즈 결정하게함**

**`extrinsic` layout: 내가 직접 박스 사이즈 정해서 콘텐츠를 끼워넣음**

내가 외부박스 사이즈 정했는데 외부박스보다 내용 너비가 더 크면 오버플로우가 나타남

이럴때 해결방법은

- 외부 박스사이즈를 지정하지 않고 intrinsic으로 결정되게 하거나
- 외부박스사이즈를 min-content로 지정하는것이다.
  - 콘텐츠의 최소 intrinsic 너비만큼 세팅해줌

## 박스모델 영역

내용 박스 < 패딩 박스 < 보더 박스 < 마진 박스

패딩박스: 오버플로우 스크롤 지정시 이 영역을 차지함

마진박스: outline, box-shadow 속성이 여기 나타남

![image](https://user-images.githubusercontent.com/67747870/142224057-b99fe6bb-b532-4d69-b35f-947d24b884f3.png)

## 박스모델 컨트롤

모든 브라우저는 **user agent 스타일시트**를 HTML 문서에 적용한다.

- 콘텐츠를 읽기 쉽게 적절한 기본값 CSS를 브라우저마다 제공함
- CSS가 없을 때 엘리먼트가 어떻게 보여질지 정의함
- 엘리먼트 display 기본값
  - <div> : block
  - <li>: list-item
  - <span> : inline

inline 요소는 block margin을 갖는다. 다른 애들은 이게 없음.

이게 없는 애들은 inline-block값 사용하면 블록 마진 가질 수 있음

인라인, 인라인블록은 콘텐츠 크기만큼만 커질수있음

### box-sizing

박스 사이즈 어떻게 계산하는지 알려줌

기본적으로 모든 엘리먼트는 `box-sizing: content-box`를 따른다

너비랑 높이를 지정했을 경우 content box에 적용해준다.

그리고 패딩이랑 보더값 세팅하면 content box 사이즈에 더해서 적용된다.

- 너비 200인데 보더 10 패딩 20 줬으면 토탈 너비는?
  - ⇒ 200 + 왼 30 + 오 30 = 260

이걸 대체하는 방법은 `box-sizing: border-box` 이다.

위에처럼 내용박스 대신 보더 박스에서 적용해준단말임

그럼 결과적으로 너비는 200 유지됨

이게 좀더 예측가능한 방법임
