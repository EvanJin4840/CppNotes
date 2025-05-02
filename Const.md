# Const 위치에 따른 의미와 정리리

### 1.변수 관련

+ 일반 변수: const int a vs int const a = 같은 것이라고 생각하면 됨.

* const는 바로 뒤의, 단독으로 쓰일 수 있는 의미 있는 최소 단위랑 묶임.
- ex) *(역참조)는 혼자 쓰일 수 없다. 그러므로 단독으로 쓰이기 위해선, 어떤 대상과 묶여야 함.

+ 포인터
int val = 10;
const int * a = &val : a가 int 형태로 있는 값을 변경 불가
int const * b = &val : b가 *b 형태로 있는 값을 변경 불가
int * const c = &val : c가 c자체 형태로 있는 값을 변경 불가가


참조 및 출처: https://m.blog.naver.com/oh-mms/222044543049