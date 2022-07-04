Document Object model
- 화면을 구성하는 html code 원하는대로 변경할 수 있음
- 자바스크립트는 DOM을 활용하여, 화면을 구성하는 모든 것들에 접근할 수 있고 원하는 대로 다 바꿀수 있다.

document.getElementById('jasoseol');
- 특정 id를 가진 dom을 가져올 수 있다.
- document.getElementById('jasoseol').value; -> 값만 가져옴
- document.getElementById('jasoseol').innerHTML; -> 값만 가져옴

- .length : 배열, 문자열의 길이 


innerHTML div, span용 내용 실제 요소를 변경할 수 있습니다., value 는 입력용(GET 또는 POST된 값)

### ex4
JS 
함수 :
```js
function 함수이름() {
    명령어1;
    명령어2;
}
```

### ex5

글자를 쓸 때마다 자동으로 글자 수를 세려면 어떻게 할까?
- 키보드를 누를 때 마다 글자 수를 세어라

이를 event라고 함
- 마우스 클릭, 키보드 누름, 값 변화, 페이지 로딩 ..

이벤트 핸들링
- 이벤트가 발생하면 ~을 해라!

키보드를 누를 때 마다(이벤트) 글자 수를 세주어라(이벤트 핸들링) 

### ex5
글자 수 제한 --> 뒤에 글자 200자 넘으면 입력 안되게 만들거
if 조건문을 통해, 200글자만 남기고 나머지는 버리는 것으로도 구현 가능
