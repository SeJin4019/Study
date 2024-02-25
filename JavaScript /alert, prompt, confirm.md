# alert
- 사용자가 '확인(ok)' 버튼을 누를 때까지 메시지를 보여주는 창이 계속 떠있게 됨
```javascript
alert("Hello");
```
메시지가 있는 작은 창을 모달창이라고 부름.   
'모달'이란 단어엔 페이지의 나머지 부분과 상호 작용이 불가능하다는 의미   
모달 창 바깥에 있는 버튼을 누르는 행동을 할 수 없음 확인 버튼을 누르기 전까지  

# prompt
- prompt 함수는 두개의 인수를 받습니다.
```javascript
result = prompt(title, [default]);
```
텍스트 메시지와 입력 필드, 확인, 취소 버튼이 있는 모달 창을 띄워줌
title :사용자에게 보여줄 문자열   
default : 입력 필드의 초깃값(선택값) (기본으로 셋팅 되어있는 값)   
*** 대괄호([])는 필수가 아닌 선택값이라는 것을 의미 ***   
prompt 함수는 사용자가 입력 필드에 기재한 문자열을 반환, 입력을 취소한 경우 null이 반환    
(즉 입력받은 문자열을 받아준다는 이야기)

# 컨펌 대화상자
```javascript
result = confirm(question);
```
confirm 함수는 매개변수로 받은 질문과 확인 및 취소 버튼이 있는 모달창을 보여줌
확인 버튼을 누르면 true, false를 반환
```javascript
let isBoss = confirm("당신이 주인인가요?");

alert( isBoss ); // 확인 버튼을 눌렀다면 true가 출력됩니다.
```
