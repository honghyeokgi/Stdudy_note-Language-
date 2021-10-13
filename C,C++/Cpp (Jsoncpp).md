##### Cpp (Jsoncpp)

--------------------------------------------------------------------------------

JsonCpp :  Cpp 에서 json 형식을 사용할수 있도록 해주는 외부 라이브러리 이다.

##### 설치

1. JsonCpp git hub 에 접속하여 사용하고자 하는 버전을 다운로드한다. (1.8.4 사용했습니다.)
2. amalgamate.py 를 실행 하여 dist 폴더에 헤더파일이 생긴것을 확인한다.
3. makefiles/msvc2010/jsoncpp.sln 파일을 실행시킨후 확인 버튼을 누른다
4. 3개의 패키지가 생기는데 모두 RuntimeLibrary 를 MDd 로 변경한다
5. 3개의 패키지를 빌드한다.
6. 사용하고자 하는 프로젝트에서 설치한 폴더의 include 경로와 debug 폴더를 추가한다.
7. dist에 있는 3개의 헤더파일을 패키지에 추가하여 같이 컴파일 하여 실행한다.

간단한 예제는 아래와 같다.

```c++
#pragma comment (lib,"lib_json.lib") // lib 파일등록을 한다면 굳이 추가하지 않아도 된다.
#include "json/json.h"
#pragma warning(disable: 4996) // 해당부분은 컴파일 및 빌드시 4996 에러가 발생한다면 추가하도록 한다.
#include <stdio.h>
#include <iostream>


std::string str;

int main()
{
	Json::Value test; // Json 배열의 이름
	test["id"] = "hhk";  
	test["age"] = 25;

	std::cout << test << std::endl;
	test["id"] = "resistor";
	
	std::cout << "id:" << test["id"] << std::endl; // 특정 원소만 추출할경우 다음과 같이 사용한다.
	
}
```

위 단계에서 6번과 7번에서 시간을 많이 소모했다..외부 라이브러리를 사용하는것은 처음이라 그런것 같다...

다른 외부 라이브러리를 사용한다면 더 빨라질것이라 생각한다.......



