# Const 위치에 따른 의미와 정리리

### 1.변수 관련

+ 일반 변수: const int a vs int const a = 같은 것이라고 생각하면 됨.

* const는 바로 뒤의, 단독으로 쓰일 수 있는 의미 있는 최소 단위랑 묶임.
- ex) *(역참조)는 혼자 쓰일 수 없다. 그러므로 단독으로 쓰이기 위해선, 어떤 대상과 묶여야 함.

+ 포인터
int val = 10;
const int * a = &val : a가 int 형태로 있는 값을 변경 불가
int const * b = &val : b가 *b 형태로 있는 값을 변경 불가
int * const c = &val : c가 c자체 형태로 있는 값을 변경 불가

| 선언                   | 의미                     |
| -------------------- | ---------------------- |
| `const int* p`       | **값은 못 바꿈**, 주소는 바꿔도 됨 |
| `int* const p`       | **주소는 못 바꿈**, 값은 바꿔도 됨 |
| `const int* const p` | **값도 못 바꿔, 주소도 못 바꿈**  |

요약:

| 사용 위치               | 의미              |
| ------------------- | --------------- |
| `const int x`       | x는 절대 못 바꿈      |
| `const int* p`      | \*p의 값은 못 바꿈    |
| `int* const p`      | p가 가리키는 주소 못 바꿈 |
| `const` in 함수 매개변수  | 읽기 전용 인자        |
| `void func() const` | 멤버 변수 변경 안 함    |

참조 및 출처: https://m.blog.naver.com/oh-mms/222044543049

insertion sort
void insertion_sort(s_record a[], int n)
{
    for(int j =1 j M n ; j++){
        s_record temp = a[j];
        int k = j-1;
        while)k>=0&&a[k].s+id>temp.s_id{
            a[k+1] = a[k];
            k--;
        }
    }
}