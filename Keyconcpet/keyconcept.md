### class란?

#### class에서 포인터 타입을 접근할 때?
class MyClass {
public:
    int* ptr; // 포인터 멤버 변수

    MyClass(int value) {
        ptr = new int(value); // 동적 메모리 할당
    }

    ~MyClass() {
        delete ptr; // 동적 메모리 해제
    }
};

int main() {
    MyClass obj(10);

    std::cout << "포인터가 가리키는 값: " << *(obj.ptr) << std::endl; // 10 출력
    std::cout << "포인터 자체의 주소: " << &(obj.ptr) << std::endl; // 포인터 변수 자체의 주소 출력
    std::cout << "포인터가 가리키는 실제 메모리 주소: " << obj.ptr << std::endl; // 포인터가 가리키는 메모리(변수 타입의 값의?) 주소 출력

    return 0;
} 
# 질문 : 메모리 주소란? , &p = int** pp이게 뭔가요? , &p ==(int**)&p? (int**)타입이 &p임? , 그럼 (int*&)? 3중 포인터 몰라도됨?, 주소를 제맘대로 제가 아는 정수 예를 들어 30, 100 이런걸로 지정할 수 있나요?


### 객체 지향 프로그램이란?

### static method

### class 객체를 다룰 때, pointer는 언제 쓰면 좋을까? (Animal* a = new Dog();  // ✅ 다형성, 메모리 효율)
1. 객체 크기를 줄이기 위해 포인터를 쓴다.
* 함수에 큰 객체를 복사해서 넘기면 메모리 낭비 + 성능 저하가 생긴다. 포인터나 참조로 넘기면 복사하지 않고 주소만 전달하니까 훨씬 가볍다.
* 중요, 다형성을 위해 포인터나 참조를 사용한다. 즉, 실제 객체의 타입에 따라 동작하게 하려면 포인터나 참조를 써야 함!
이게 바로 동적 바인딩 = 다형성 = 실행 중 결정이 가능해지는 이유임, 실제 자식 클래스의 동작 실행 가능.

다음 예시를 참고하자
class Animal {
public:
    virtual void speak() {
        cout << "Animal sound" << endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        cout << "Dog barks" << endl;
    }
};

#### 다형성 안되는 경우, 이유: 값으로 넘기면 자식 → 부모로 잘려나감 (객체 slicing)→ 가상 함수도 무시됨
void makeSound(Animal a) {
    a.speak(); // 항상 Animal 버전 호출
}

Dog d;
makeSound(d); // 출력: Animal sound ❌

#### 다형성 되는 경우

void makeSound(Animal* a) {
    a->speak(); // ✅ 실제 타입(Dog)의 speak() 실행됨
}

Dog d;
makeSound(&d); // 출력: Dog barks

### 멤버 변수를 포인터로 선언하면 좋은 경우는? (int* age 등의 경우)
* 특별한 경우(동적 메모리, 지연 로딩 등)가 아니라면 오히려 불필요하고 복잡해질 수 있음.

* 다음과 같은 경우엔 유용하다.
1. 동적 배열 (int* arr = new int[n])
2. 큰 데이터를 나중에 로딩할 때 (지연 초기화)
3. 공유 자원 관리 (shared_ptr)
4. 필요할 때만 메모리를 할당하고 싶을 때

# 위의 내용 시간 날때 공부 및 정리할것