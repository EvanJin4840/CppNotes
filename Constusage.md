# Const 위치에 따른 의미와 정리

* const int a = 10;
* int const b = 10;

두 문장 모두 변경이 불가능하다. 첫번째 문장은 a의 int형식의 값 변경이 불가능하고, 두번째 문장은 a라는 놈의 자체 값 변경이 불가능하다는 의미이다.

출처: https://m.blog.naver.com/oh-mms/222044543049

## 오버로딩된 const/ 비 const함수 구분법?
* 예: const 객체와 non-const 객체에 따라 호출되는 함수가 달라지는 경우!