### jQuery
document.getElementById('content').value;
-> $('#content').val();
-> $(선택자).행위;

jQuery 장점
- 간결한 문법
- 편리한 API
- 크로스 브라우징

### jQuery event(ex2)
```js
<button id="click" onclick="hello();">클릭</button>
```

↓

```js
<button id="click">클릭</button>
<script>
    function hello() {
        console.log('hello');
    }
    //.click()
    $('#click').click(hello);
</script>
```

### jQuery 익명함수 (ex3)
위에서는 함수를 정의하고 호출이 분리되어있음
익명함수는 간단한 이벤트 처리 한번만하고 반복되지 않는 함수일 때 사용
```js
<script>
    $('#click').click(function() {
        console.log('hello');
    });
</script>
```

### 미니 스타크래프트 2
.fadeIn([duration ] [, complete ])
- [대괄호는 선택 사항] 
- duration : A string or number determining how long the animation will run
- complete: A function to call oner the animation is complete, called once per matched element.


### 미니 스타크래프트 3
.animate(properties, [duration], [easing], [complete])
- properties : An object of CSS properties and values that the animation will move toward.
- easing: A string indicating which easing function to use for the transition.

### 미니 스타크래프트 4
.fadeOut([duration ] [, complete ])
-> 요소를 fadeOut 처리

드론에서 spit을 한 발 더 발사하려면 드론에서 시작하는 것이 아니라 벙커에서 발사하는데 이는 spit을 원래 원 위치로 옮겨야됨
```js
$('#spit').css({left: '150px'});
```

### 미니 스타크래프트 5(ex 5)
코드 순서상 벙커가 침에 맞고 HP가 감소해야되는데 맞기전에 HP가 감소하는 상황이 나타남 
```js
<script>
    var hp = 3;
    $('#drone').click(function(){
        $('#spit').fadeIn();
        $('#spit').animate({left: '+=250'});
        $('#spit').fadeOut();
        $('#spit').css({left: '150px'});
        hp -= 1;
        $('#hp').text('HP :' + hp);
        // hp id를 가진 text를 변경한다.
    });
</script>
```
이는 코드의 실행을 하고 종료되는지 확인하지 않고 순차적으로 코드를 실행하므로 맞기전에 HP가 감소하는 상황 발생한 것

> 즉 위의 시간이 오래걸리는 코드들은 동작하고 있는 동안 HP 변환은 빠르게 처리해서..

fadeOut(,complete) -> 이용한 spit이 사라질 때 hp가 감소하게 만들면 코드의 동기화(??)를 맞춰줄 수 있다.

```js
<script>
        var hp = 3;
        $('#drone').click(function(){
            $('#spit').fadeIn();
            $('#spit').animate({left: '+=250'});
            $('#spit').fadeOut(function(){
                hp = hp - 1;
                $('#hp').text('HP: ' + hp);
                if(hp == 0) {
                    $('#bunker').fadeOut()
                };
            });
            $('#spit').css({left: '150px'});
        });
    </script>
```