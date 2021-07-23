### transition

- 어떤 상태에서 다른 상태로의 변화를 보내주는 애니매이션
- transition은 state가 없는 요소에 붙어야 한다(처음에 생긴 곳에)
- state에 transition을 준다면 변화를 준 행위를 그만할 경우 원래 상태로 바로 돌아간다
- transition 에 변화를 준 것들은 state에 들어있는 것들이 기준이 되어 바뀌는 것임, 바뀌는 것들에 한정하여 transition이 일어날 수 있음

---

- transition 은 상태에 따라 바뀌는 요소가 있을 때 사용함
- ease-in function: 브라우저에게 변화하는 방법을 알려주는 역할
- ease-in - 시작과 끝이 빠름
- ease-out - 시작과 끝이 느림
- ease-in-out - 시작이 빠르고 끝이 느림
- all - 변화 요소를 한번에 다룸
- cubic-bezier(0, 0, 0, 0) 을 통해 직접 설정 가능

### transformation

- 한 요소를 변형 시킬 수 있음
- transformationd은 box element를 변형시키지 않음, 즉 sibling들에게 영향 X
- margin, padding 적용 X, 일종의 3D transformation이기 때문
- transformationd은 페이지의 픽셀의 다른 부분에서 일어남
- box차원에서 일어나지 않음
- transformation 결합 가능

### Animation

```
@keyframes Animation Name{
  from{

  }
  to{

  }
}
img{
  animation: 애니메이션 이름 재생시간 옵션
  무한으로 반복 -> infinite
}
```

- from to 말고 1,2,3,4,5... 혹은 0% 25% 50% ... 와 같이 여러 단계를 나누어 애니매이션을 만들 수 있음
- 다른 proerty들도 애니매이션으로 만들 수 있음, 꼭 transform만 써야하는 건 아니지만, transform을 쓰는 걸 권함.

- Animation sample site
  https://animista.net/

### Media Queries

- screen and (min-width: npx) and (max-width:npx) and (orientation: landscape or portrait) => 스크린 사이즈에 따라서 property 조정 가능
  orientaiton은 가로 세로 감지

- media query는 and로 연ㄱ녈
- media ~ and ~ {
  element{
  ~
  }
  }
  }
- min-device-width는 모바일 전용
