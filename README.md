# 2025_Kwangwoon_DS_Project_2

반드시 제안서에 표기되어 있는 **구현 스펙 및 감점 조건**을 확인하고 구현할 것, 이를 확인하지 않고 이의 신청 시 점수 부여 불가능

제안서에 명시되어 있는 내용에 대한 질문은 답변 없이 Close할 예정입니다. 꼭 제안서를 꼼꼼히 살펴보시기를 바랍니다.



예시 command.txt 파일은 추후 업로드 예정, 그러나 모든 case를 다루는 것이 아니고 채점 용도로 예시 Command가 활용되는 것이 아님.

직접 command를 생성해서 여러 예외 case들을 확인해볼 것.

---

## Update Notes  

2025.10.13 (Version 2)
- 구현 조건 '메모리 누수 시 10% 감점' 삭제

2025.10.16 (Version 3)
- 각 명령어 구현 조건 일부 변경 (제안서 변경)
- Skeleton Code 오류 일부 수정
- command.txt, employee.txt 예시 파일 추가

2025.10.30 (Version 4)
- B+ Tree Delete 관련 내용 삭제 (제안서 오류 수정, 기존 구현 조건 변경 사항은 없음)
---

## How to Clone Repository  

```bash
sudo apt-get install git   #1차 프로젝트에서 다운받았다면 입력하지 않아도 무방
git clone https://github.com/evejaeyong/2025_Kwangwoon_DS_Project_2.git
```

---

## How to check memory leak 
- make 이후 생성된 run 파일 실행 전에 valgrind 명령어를 입력하면 메모리 누수를 확인 가능
- 반드시 run 파일이 있는 디렉토리 내에서 수행해야 함. cd(change directory)로 변경하기
```bash
sudo apt-get update
sudo apt-get install valgrind  #1차 프로젝트에서 다운받았다면 입력하지 않아도 무방
valgrind ./run
```
- "All heap blocks were freed -- no leaks are possible" 메세지가 출력되어야 누수가 발생하지 않은 것, "LEAK SUMMARY"가 나온다면 누수가 발생
- 2차 프로젝트에서는 메모리 누수를 따로 체크하지는 않을 예정
---

## 구현 고려사항

1. B+ Tree의 차수 변경이 가능하도록 구현해야 함. main.cpp 파일에서 Manager의 parameter로 받는 3을 조정하면, 하나의 Node에 들어가는 데이터의 갯수가 변경되도록 구현
2. Selection Tree는 포인터 형태로 구현, Heap은 배열 형태로 동적 할당을 통해 구현
3. 제안서 '표 2. 명령어 사용 예 및 기능 설명'에 명시되어 있지 않은 예외 case는 고려하지 않아도 무방함 (너무 애매하다고 생각하면 Github Issue를 통해 질문해주세요.)
4. 모든 명령어에 대해서, 너무 많은 인자 혹은 적은 인자를 받는 경우엔 각 명령어에 맞는 Error Code 출력
5. 주석은 필수로 작성. Line by line 수준으로 디테일할 필요는 없음. 그러나 너무 미흡하다면 감점 - 10% (반복문, 조건문이 어떤 역할을 하는지 정도만 입력해도 괜찮습니다.)
6. 출력은 반드시 log.txt 파일을 생성해 출력해야 함. 지키지 않을 시 **감점 - 10%**
7. log.txt, command.txt, employee.txt 파일 모두 코드와 같은 디렉토리 내에서 존재해야 함. 이를 지키지 않아서 코드 실행이 안될 경우 **점수 부여 불가**
8. log.txt 파일에서는 동작하지만, 실제 자료구조가 제대로 구현되어 있지 않은 경우 **감점 - 20점** (Ex. B+ Tree Search를 진행할 때, 가장 앞쪽 노드부터 Linked list를 검색하듯이 검색한다면 감점)
