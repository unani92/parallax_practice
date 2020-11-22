# Parrlax Practice

실전에서 활용할 수 있는 패럻랙스 라이브러리들을 서칭하고 이를 실습해 봄으로써 실제 서비스에서 활용 가능하게 하는 것이 목표이다. 

### 1. rellax JS
패럴랙스 효과를 적용하고자 하는 DOM element에 rellax 객체를 적용해 줌으로써 간단하게 스크롤 다운 속도차에 의한 입체감을 줄 수 있다. 

```javascript
var rellax = new Rellax('.rellax')
```

```html
<img src="/image/guitar.svg" class="rellax guitar"  data-rellax-speed="3" alt="guitar-image">
<img src="/image/crowd.svg" class="rellax crowd" alt="crowd-image" >
```

### 2. scroll-out 
효과를 적용하고자 하는 DOM element에 객체를 적용해주는 것 만으로 간단하게 스크롤 효과를 줄 수 있다. 

```javascript
ScrollOut ({
  // config 는 이 곳에 들어갑니다.
  threshold: .2
})
```

```css
[data-scroll] {
    transition: opacity 1s;
}
[data-scroll="in"] {
    opacity: 1;
}
[data-scroll="out"] {
    opacity: 0;
}
```

### 3. lax js
스크롤을 활용해 페이드 인/아웃, 회전, 가로/세로 트랜지션 등 다양한 애니메이션 효과를 줄 수 있다. 

```javascript
window.onload = function() {
    // lax 객체 생성
    lax.init()

    // scrollY 라는 이름의 드라이버를 추가
    lax.addDriver('scrollY', function () {
        return window.scrollY
      })

    // 특정 클래스와 드라이버에 맞는 애니메이션을 추가
    lax.addElements(
        '.box1',
        {
          // scrollY 드라이버의 값 변화에 따른 회전각 조절
          // 0일때 rotate = 0 , 10**9 일 때 rotate = 10**9
          scrollY: {
            rotate: [
              [0,1e9],
              [0,1e9]
            ]
          }
        }
      )
}
```

상기한 방식으로 선언한대로 해당 클래스에 맞는 애니메이션 효과들이 적용된다. 
다양한 효과들이 프리셋으로 이미 구현되어 있어 [이것](https://alexfox.dev/lax.js/preset-explorer)을 활용하면 더욱 간편하게 효과를 적용할 수 있다. 
```html
<div class="box1 lax"></div>
<div class="box2 lax lax_preset_fadeInOut-114-0"></div>
```