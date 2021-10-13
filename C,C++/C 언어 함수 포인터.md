##### C 언어 함수 포인터

--------------------------------------------------------------------------------

C언어 함수 포인터

함수 포인터는 함수의 주소값을 저장하는 포인터 변수이다(함수를 가르키는 포인터)!

```c
// 형식
// 반환자료형 (* 함수포인터 이름)(자료형1 매개변수이름,자료형2 매개변수 이름 ...)
```

위와 같은 형식으로 작성한다.

간단하게 3개의 인자를 받아 1번쨰 인자는 결과값을 저장할곳 2,3의 인자를 더하는 함수 포인터를 생성하면 아래와 같다.

```c
#include <stdio.h>

int add(int *z,int a, int b);

int main()
{
    int (*sum)(int *,int,int) = add;
    int result = 0;
    sum(&result,6,3);
    printf("%d",result);
    
}

int add(int *z,int a, int b)
{
    return *z = a + b;
}
```

다음과 같이 작성할수 있다.



이제 이 함수 포인터를 구조체 변수에 할당하는 방법은 아래와 같다.

```c
#include <stdio.h>

struct Calc
{
	float (*sum)(float, float);
	float (*minus)(float, float);
};

float add(float a, float b)
{
	float answer;
	answer = a + b;
	return answer;
}

float minuser(float a, float b) 
{
	float answer;
	answer = a - b;
	return answer;
}

int main()
{
	struct Calc cal;
	cal.sum = add;
	cal.minus = minuser;
	float result = 0;

	result = cal.sum(5, 5.3);
	printf("%.2f \n", result);

	result = cal.minus(5, 2.1);
	printf("%.2f", result);
    
    return 0 ;
}
```

구조체에 여러가지 함수 포인터를 정의하여 헤더파일에서 설정한다면 자신만의 내장함수로 사용할수 있을것 같으며 코드 활용도에 좋은 결과가 나타날것 같당!!!