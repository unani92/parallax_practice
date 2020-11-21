# Parrlax Practice

실전에서 활용할 수 있는 패럻랙스 라이브러리들을 서칭하고 이를 실습해 봄으로써 실제 서비스에서 활용 가능하게 하는 것이 목표이다. 

1. rellax JS
패럴랙스 효과를 적용하고자 하는 DOM element에 rellax 객체를 적용해 줌으로써 간단하게 스크롤 다운 속도차에 의한 입체감을 줄 수 있다. 

```javascript
var rellax = new Rellax('.rellax')
```

```html
<img src="/image/guitar.svg" class="rellax guitar"  data-rellax-speed="3" alt="guitar-image">
<img src="/image/crowd.svg" class="rellax crowd" alt="crowd-image" >
```

2. scroll-out 
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