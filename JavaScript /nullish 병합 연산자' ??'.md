# nullish 병합 연산자 '??'
a ?? b의 평과 결과는 다음과 같음    
a 가 null도 아니고 undefined도 아니면 a 그 외의 경우는 b
```javascript
let firstName = null;
let lastName = null;
let nickName = "바이올렛";

// null이나 undefined가 아닌 첫 번째 피연산자
alert(firstName ?? lastName ?? nickName ?? "익명의 사용자"); // 바이올렛
```
## '??'와 '||'의 차이 
```javascript
height = height ?? 100; // height에는 100이 할당 undefined이기 때문에

let height = 0;

alert(height || 100); // 100 0을 falsy한 값으로 취급 null, undefined를 할당한 것과 동일하게 처리 
alert(height ?? 100); // 0 여기서는 정확하게 null, undefined인 경우에만 100이 할당 
```
안정성 관련 이슈 때문에 ??는 &&나 ||와 함께 사용하지 못함
```javascript
let x = 1 && 2 ?? 3; // SyntaxError: Unexpected token '??'
```

