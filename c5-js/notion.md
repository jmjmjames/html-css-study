### 기념일 계산기 미리보기


### 객체(Object) 알아보기(ex2)
```js
var person = {
    name: 'jocoding', //key: value
    age: 20,
    sayHello: function() {
        console.log('hello')
    }
}
```
- 객체.key 를 사용하면 값을 얻을 수 있음
  - 예) person.name
- value가 함수일 때, 객체.함수()
  - 예) person.sayHello();


### Date 객체 알아보기 (ex3)
내장 객체
```js
<script>
    var now = new Date();    
    $('#click').click(function() {
        console.log('hello');
    });
</script>
```
