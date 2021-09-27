##### C언어 구조체

--------------------------------------------------------------------------------

구조체 : 연관성이 있는 서로 다른 개별적인 자료형의 변수들을 하나의 단위로 묶은 새로운 자료형 이다.

만약 사람이라는 구조체를 만든다고 하면 아래와 같이 만들고 사용할 수 있다.

```c
#include <stdio.h>
#include <string.h>


struct person
{
	char name[12];
	int age;
	char gender[3];
};

int main(void) {

	struct person mine = { "홍혁기",25,"남" };  // 선언된 구조체는 자료형처럼 사용된다.
	struct person yours;

	int result = 0;
	int *ptrresult = &result;

	strcpy_s(yours.name, 12, "정창일");
	yours.age = 26;
	strcpy_s(yours.gender,3,"남");

	printf("%s %d %s \n", mine.name,mine.age,mine.gender);
	printf("%s %d %s \n", yours.name, yours.age, yours.gender);
	return 0;
}
```

1. person 이라고 선언된 구조체는 name,age,gender 가 변수로 선언되어 있다.
2. 선언된 구조체는 자료형으로 쓰인다 
3. 구조체 로 생성한 변수는 초기화 하면서 값을 넣어줄수 있다.
4. strcpy_s 를 통해 값을 넣어줄수도 있다.

이러한 구조체의 성질을 잘 활용한다면 코드 간결화에 도움이 될것 같다!

