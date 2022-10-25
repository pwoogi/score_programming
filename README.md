## JAVA를 활용한 학점 산출 프로그램 만들기

* 초심으로 돌아가서 복습해보자

### 문제 정의

- Good School 학교가 있습니다. 이 학교에는 5명의 학생들이 수업을 듣습니다. 과목은 국어와 수학이 있고, 각 학생은 두 과목을 모두 수강합니다.

전공은 컴퓨터공학과 국어국문학 두 가지가 있습니다. 컴퓨터공학과 학생은 수학이 필수과목이고, 국어국문학과 학생은 국어가 필수 과목입니다.

각 학생별로 한 개의 전공을 선택합니다.

이번 학기 각 학생의 성적은 다음과 같습니다.

| 이름 | 학번 | 전공 | 필수 과목 | 국어 점수 | 수학 점수 |
| ------ | ------ | ------ | ------ | ------ | ------ |
| 강감찬 | 211213 | 국어국문학과 | 국어 | 95 | 56 |
| 김유신 | 212330 | 컴퓨터공학과 | 수학 | 95 | 98 |
| 신사임당 | 201518 | 국어국문학과 | 국어 | 100 | 88 |
| 이순신 | 202360 | 국어국문학과 | 국어 | 89 | 95 |
| 홍길동 | 201290 | 컴퓨터공학과 | 수학 | 83 | 56 |

- 학점을 부여하는 방벅은 여러 가지가 있습니다. 단순히 A,B,C,D,F를 부여하는 방법, A+, B-처럼 +/-를 사용하는 방법, Pass/Fail 만을 부여하는 방법등이 있습니다.

여기 각 학생에게 학점을 부여하는 데 사용하는 정책은 두 가지입니다. 일반 과목이라면 A ~ F로, 필수 과목이라면 S ~ F 로 분류합니다. 점수에 따른 학점 부여기준은

다음과 같습니다

- 필수 과목 학점 기준

| S | A | B | C | D | F |
| ------ | ------ | ------ | ------ | ------ | ------ |
| 95~100점 | 90~94점 | 80~89점 | 70~79점 | 60~69점 | 60점 미만 |

- 일반 과목 학점 기준

| A | B | C | D | F |
| ------ | ------ | ------ | ------ | ------ |
| 90~100점 | 80~89점 | 70~79점 | 55~69점 | 55점 미만 |

만약 똑같이 95점을 받은 경우, 필수 과목이라면 S를 받지만, 일반 과목은 A를 받습니다. 또한 56점을 받으면 필수 과목은 F이지만, 일반 과목은 D를 받습니다.

- 프로그램 구현 과제

위와 같이 주어진 성적과 각 과목에 대한 학점 정책에 따라 아래와 같이 학점 결과가 나올 수 있도록 구현합니다.

학점의 정책이 추가되는 경우와 과목이 추가되는 경우를 고려하여 객체를 설계하고 학점 정책에 대해서는 인터페이스를 선언하고 각 정책이 해당 인터페이스를 구현하도록 합니다.


### 클래스 정의 하고 관계도 그리기

<img src = "https://gitlab.com/easyspubjava/javacoursework/-/raw/master/Chapter7/img/student.png">


### 학점 평가 정책 설계하고 구현하기

인터페이스 정의하기

점수에 따른 학점의 정책은 여러가지가 있을 수 있습니다. 인터페이스를 먼저 선언하고, 각 정책 클래스가 이를 구현하도록 합니다

<img src= "https://gitlab.com/easyspubjava/javacoursework/-/raw/master/Chapter7/img/grade.png">


## 💭 회고
* 인터페이스 활용의 중요성을 다시 한 번 깨달았고 객체지향적인 설계의 공부가 심각하게 부족함을 느낌
* legacy한 기초 코드를 잘 다룰 수 있어야 조금 더 간결한 설계 또는 리팩토링 시 어떤 것을 수정해야하는지 깨달음.