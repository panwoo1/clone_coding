### css with html

1. head tag 안에 style tag
2. CSS와 HTML 분리(대부분)
   - link tag를 이용해 styles.css와 연결하고 rel을 이용해 관계

- css가 하는 일은 HTML 태그를 가리키는 일(selector)
- CSS 작성에 띄어쓰기 X
- 속성 다음 콜론(:), 세미콜론(;) 으로 닫아줘야함

- \_ , / 도 사용 X
- css또한 어떤 값이든 쓸 수 있지만, 속성에 맞는 값을 써야 적용됨

- Cascading Style Sheets 에서 Cascading은 위에서 아래로 순서대로 브라우저가 css를 읽을 때 방식
- css를 html에 직접 적는 것을 inline CSS
- css를 포함시키는 것을 external CSS
- selector를 가리키는 CSS가 여러개이면, 가장 마지막 스타일이 적용

- div는 block으로 다른 요소 못옴
- 옆에 오는 것들이 더 적음 (span, link,img .etc)
- 옆에 올 수 있는걸 inline 라고 함.

### margin

- margin은 경계의 바깥 쪽
- 방향 설정 없이 margin 하나를 주면 사방에 적용
- 두 개를 줄 경우 상하, 좌우
- 네 개를 줄 경우 상 우 하 좌
- Collapsing margin 현상 (상 하 에서만 발생)
- body안에 div의 위 아래 마진이 body의 마진과 만나면 둘 중 큰 값의 마진으로 body에 적용

### padding

- padding은 margin의 반대 개념
- padding은 box의 경계로부터 안쪽에 있는 공간
- 값의 개수에 따라 적용되는 방향 margin과 동일
- 특정 id의 값을 지칭하려면 #id를 이용해 접근

### border

- box의 경계
- border: 굵기, 스타일, 색상 순

### classes

- span은 inline이기 때문에 높이와 너비를 가질 수 없으며, 위, 아래에 margin을 가질 수 없음
- padding은 가능
- .class
- id => #id class => .class
- class는 id와 다르게 여러 요소 작성 가능

### inline-block

- inline - width, height 무시돼서 무언가 추가하지 않는 이상 아무것도 안보임
- inlie-bock - 위 문제를 해결할 수 있어서 좋긴 한데, 반응형 디자인 지원되지 않음 -> 이 문제를 해결할 수 있는게 flex

### flex

- 자식 엘리먼트에는 어떤 것도 적지 말아야함.  
  자식 엘리먼트를 움직이게 하려면 부모 엘리먼트를 flex container로 만들어야 함.
- align-itmes - cross axis에서 작용(세로)
- justify-content - main axis에서 작용(가로)(디폴트)
- flex-container가 height를 가지고 있지 않으면 align-itmes를 사용하더라도 위치 바뀌지 않음.
- vh = viewpoint height (스크린에 따라 다름)

- justify-content나 align-items의 default를 변경하기 위해선, 'flex-direction'을 수정하면 된다.
- flex-direction에는 두 가지 속성, column과 row가 있다.
- display를 flex로 했을 때 default는 row이다. 따라서 flex-direction: column;을 주면 주축과 교차축이 반전된다.
- 원하는만큼 flex 부모-자식 엘리먼트를 만들어낼 수 있다.
- flex-wrap: nowrap;을 통해 wrapping이 일어나지 않게 할 수 있다.
- flexbox는 width값을 초기 사이즈로만 여기고, 모든 엘리먼트를 같은 줄에 있게 하기 위해 width를 바꾸기도 한다.
- flex-direction: column-reverse; 밑에서 시작해서 위로 올라가게 한다.(마찬가지로 row-reverse도 있다.)
- flex-wrap: wrap-reverse; 또한 있는데, 브라우저를 줄일 때, 엘리먼트가 겹쳐지는 위치가 역전된다rap일 경우 크기르 줄여서라도 한줄로

- https://flukeout.github.io/ css
- https://flexboxfroggy.com/#ko flex

### fixed

- position fixed를 이용하면 스크롤해도 항상 제자리
- 처음 만들어진 자리에 고정되어 있지만, top, left, right, bottom 중 하나만 수정해도 서로 다른 레이어에 위치하게 되어 원래 위치 무시됨

### position

- position: static (default)
- position: fixed - element가 처음 생성된 자리에 고정
- position: relative - element가 처음 생성된 위치를 기준점으로 top, bottom, left, right으로 위치를 조금씩 수정할 수 있음.
- position: absolute - 가장 가까운 relative 부모를 기준으로 이동  
  position: relative; 를 해주면 부모가 된다. 없으면 body

### pseudo selector

- 세부적으로 element를 선택해 주는 것
- ex) div:first-child...last-child...
- n번째 태그 수정 - nth-child(n) (even, odd, 3n +1 이런식으로...)

- ~를 사용해 바로 뒤에 오는 형제 관계가 아닌 tag에도 스타일 적용
- tag[attribute = "value"]을 통해 스타일 적용 가능
- tag[attribute ~= "value"]으로 value를 포함하는 모든 tag에 스타일 적용 가능
  = \*= is 'contains' , ~= = is 'exactly'
- ::placeholder - placeholder의 특성만 바꾸고 싶을 때 사용
- ::selection - 클릭해서 드래그할때 발생
- ::first-letter - 첫 글자에만 적용
- ::first-line - 첫 줄에만 적용

### Combinators

- div의 바로 밑 자식에서 span을 찾아서 그것만 효과를 주는 방법
  - div span{} 이렇게 하면 div 밑에 모든 span이 효과를 가짐
  - div > span 바로 밑을 찾게 되므로 바로 밑의 자식만
  - p + span{} 형제에게 영향을 끼침

### States

- active - 해당 요소를 마우스로 클릭했을 때 효과를 적용
- hover - 마우스가 해당 요소 위를 지나갈 때 효과를 적용
- focus - 키보드로 선택되었을 때 효과를 적용
- focus-within - 부오 요소에게 적용. 자신의 자식 요소 중 하나가 focused 되었을 때 효과를 적용
- visited - 방문한 사이트일 경우에 효과를 적용
- 조건을 나열해 여러 상황 설정 가능 ex) high-tag:hover ...

### color

- color system
  1. 16 진수 ex) #fcce00
  2. RGB ex) rgb(252, 206, 0), rgba(205, 23, 0, 0,5) (4번쨰 element는 투명도)
  3. color ex) tomato, teal ,...

### variable

- :root 라는 엘리먼트 추가 -> 모든 document의 뿌리
- --main-color 라고 하면 root 에 저장됨
