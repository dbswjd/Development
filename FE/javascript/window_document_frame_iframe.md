# window, document, frame, iframe 알아보기 

## window
+ 브라우저 객체 모델의 최상위 객체
+ 브라우저 객체 모델(BOM : Browser Object Model) 은 웹브라우저의 탭 혹은 창의 모델을 나타내는데, 이러한 웹브라우저 객체 모델의 최상위 객체가 window 객체
+ window 객체는 현재 웹브라우저의 창이나 탭을 표현

## document
+ 문서 객체 모델의 최상위 객체
+ 문서 객체 모델(DOM : Document Object Model) 은 현재 웹페이지의 모델을 생성하며, 이러한 문서 객체 모델의 최상위 객체가 document 객체
+ document 객체는 전체 페이지를 표현

### window vs document 
window는 웹브라우저 창, document는 웹브라우저 창 안에 보이는 문서 
실제로 document 객체는 window 객체의 속성

## frame

## iframe
https://kamang-it.tistory.com/entry/Webhttp%ED%86%B5%EC%8B%A0%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%96%91%EB%B0%A9%ED%96%A5-%ED%86%B5%EC%8B%A0%EA%B8%B0%EB%B2%95-hidden-iframe-streaming

### iframe 통신
#### postMessage
window.postMessage
``` javascript
otherWindow.postMessage(message, targetOrigin, [transfer]);
```
otherWindow : postMessage를 보낼 대상
message : 대상에게 전송할 내용, string 타입 
targetOrigin : 메세지르 전송받을 대상의 도메인을 설정하는 부분


``` javascript
window.onload = function () {
  window.parent.postMessage("This is message", '*');
}
```

수신 측
``` javascript
window.addEventListener('message', function (e){
  console.log(e.data); //This is message
});
```


출처 : http://june0313.github.io/2019/02/16/windows-document/#:~:text=document%20%EA%B0%9D%EC%B2%B4%EB%8A%94%20%EC%A0%84%EC%B2%B4%20%ED%8E%98%EC%9D%B4%EC%A7%80,%EB%AC%B8%EC%84%9C%EB%9D%BC%EA%B3%A0%20%EC%83%9D%EA%B0%81%ED%95%98%EB%A9%B4%20%EB%90%9C%EB%8B%A4.
https://ohgyun.com/531 
