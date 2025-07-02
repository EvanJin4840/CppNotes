## makefile 사용법 정리

- make -d 하면 어떤 규칙이 작동 안 했는지 로그로 확인 가능

### 예제


* 최종적으로 만들 실행 파일 이름
all: main
main.c
util.c
util.h

* 실행 파일(main)을 만들기 위해 필요한 오브젝트 파일 나열
main: main.o util.o
	$(CC) -o main main.o util.o

* .c 파일을 .o 파일로 컴파일
main.o: main.c util.h
	$(CC) -c main.c

util.o: util.c util.h
	$(CC) -c util.c

* 임시 파일 지우는 규칙
clean:
	rm -f *.o main
