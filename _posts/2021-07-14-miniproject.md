---
layout: single
title: "미니프로젝트 개발문서 모델"
---
### ■ 개발 소프트웨어 이름 : 영어단어 테스트기

### ◈요구사항
영어 단어를 외우면서 내가 얼마나 많이 외웠는지 시험을 보고 싶을 때가 있다. 
그러나 직접 단어를 써가며 시험지를 만드는 것은 오래 걸리고 번거롭기도 하다. 또한 채점 하는데에도 시간을 소요한다.
따라서 영어단어 테스트기 프로그램은 영어 단어를 외우고, 외운 단어를 스스로 테스트 하고 싶을 때 사용하기 위한 프로그램이다.
짧은 시간 안에도 영어 단어 테스트를 할 수 있고, 테스트를 마친 뒤 오답을 확인할 수 있는 기능을 통해 내가 어떤 단어를 모르는지, 어느 부분을 더 외워야하는지 알 수 있다.

[조건]
- 영어 단어와 뜻이 적혀있는 파일을 입력한다.
- 파일에 입력된 단어 중 테스트를 볼 단어의 개수를 정한다
- 사용자가 입력한 숫자 만큼 입력된 파일에서 랜덤으로 단어가 출력된다
- 사용자는 출력된 단어를 보고 뜻을 입력한다
- 단어 테스트가 종료되면, 맞은개수와 틀린개수를 알려주고, 오답을 확인할 것인지 물어본다
- 사용자가 오답확인을 원하면, 틀린단어에서 사용자가 입력한 단어와 정답을 같이 보여준다
- 오답확인이 끝나거나 사용자가 오답을 확인하지 않으면 프로그램을 마친다.

### ◈설계
1. 파일에서 단어를 읽어와 리스트에 저장한다
2. 단어를 뜻과 묶어 리스트에 저장한다
3. 사용자가 입력한 단어 개수만큼 랜덤으로 문제를 낸다
4. 정답과 오답의 개수를 센다
5. 테스트가 끝난 후에는 정답, 오답의 개수를 알려주고 오답리스트를 보여준다

### ◈코드
~~~python
import random
answer_o=0 #정답 개수
answer_x=0 #오답 개수
filelist=open('영단어 100개.txt','r').read().split() #파일에 있는 100개 단어 임시 저장
wordlist=[] #단어와 뜻을 같이 묶어서 저장
testlist=[] #문제에 나오는 단어를 저장
numlist=[] 
for x in range(int(len(filelist)/2)):
  wordlist.append([filelist[2*x],filelist[2*x+1]])
 
num=int(input(f'원하는 영어 단어 개수를 입력하세요\n(단, {len(wordlist)}의 개수보다 많을 시에는 {len(wordlist)}개의 단어가 나온다.) '))
if len(wordlist)<num: #wordlist의 길이보다 큰지 비교
  num=len(wordlist)
 
ran_num=random.randint(0,len(wordlist)) #ran_num에 0부터 단어장의 길이까지 랜덤으로 숫자를 넣음
for i in range(num): #숫자 num개 뽑기
  while ran_num in numlist: #뽑은 숫자들이 중복되지 않도록 numlist에 이미 있는 숫자인지 검토
    ran_num=random.randint(0, len(wordlist)) #중복되면 다시 뽑기
  numlist.append(ran_num) #numlist에 숫자 추가
 
for x in range(num): #사용자가 입력한 숫자(num)만큼 단어 출력(반복)
  testlist.append(wordlist[numlist[x]]) #testlist에 wordlist의 numlist[x]번째 단어를 저장
  word=input(f'{wordlist[numlist[x]][0]} : ') #사용자에게 단어 뜻을 입력받음
  if (word==wordlist[numlist[x]][1]): #만약 입력한 답안이 정답이라면 
    answer_o+=1 #정답 개수 증가
    testlist[x].append('T') #정답이면 True를 추가
  else:
    answer_x+=1 #오답 개수 증가
    testlist[x].append('F') #오답이면 False를 추가
    testlist[x].append(word)
else:
  print(f'\n결과 / 전체-{num} 정답-{answer_o} 오답-{answer_x}')
  if answer_x!=0: #오답이 없다면 바로 종료
    check=int(input('오답을 보시겠습니까?(1-확인, 0-종료) ')) #오답이 있으면 오답을 볼건지 질문
    if check:
      print('\n오답리스트')
      for x in testlist: 
        if x[2]=='F': #testlist의 저장된 값이 F인것만 출력
          print(f'문제-{x[0]} 내가 쓴 답-{x[3]} 정답-{x[1]}')
  print('\n영어단어 테스트를 종료합니다')
~~~

### ◈테스트
영단어 100개.txt  
servant 하인
hunger 배고픔
tomb 무덤
taste 맛
sign 신호
stair 계단
trip 여행
brain 뇌
trumpet 트럼펫
speech 연설
thumb 엄지손가락
horn 뿔
chief 주요한
trousers 바지
prince 왕자
force 힘
sight 시야
space 우주
wool 양모
expressway 고속도로
science 과학
examination 시험
jar 단지
salt 소금
death 죽음
saw 톱
swing 그네
wish 소원
grain 곡식
eraser 지우개
alphabet 알파벳
shoulder 어깨
nephew 조카
niece 조카딸
library 도서관
factory 공장
giraffe 기린
hawk 매
pigeon 비둘기
bowl 사발
scene 장면
life 생활
earth 지구
pill 알약
math 수학
ocean 대양
price 가격
row 줄
schedule 일정
machine 기계
route 길
ivy 담쟁이덩굴
gift 선물
candle 초
joke 농담
art 예술
corn 옥수수
pet 애완동물
robber 강도
cheek 뺨
clerk 점원
cookie 쿠키
army 군대
nurse 간호사
master 주인
lock 자물쇠
moment 순간
sheet 시트
monk 승려
teenager 십대
closet 벽장
handle 다루다
guide 안내하다
bar 막대기
ostrich 타조
knee 무릎
cricket 크리켓
deck 갑판
bit 조금
silk 비단
jean 진바지
cotton 솜
drum 북
sand 모래
shock 충격
march 행진
cage 새장
whole 전부
change 교환
department 부
office 사무실
ticket 표
energy 힘
idea 생각
hospital 병원
noise 소음
sample 샘플
example 예
lesson 교훈
plenty 풍부

[실행결과]  
원하는 영어 단어 개수를 입력하세요  
(단, 100의 개수보다 많을 시에는 100개의 단어가 나온다.) 10  
office : 사무실  
cookie : 쿠키  
march : 행진하다  
brain : 뇌  
cage : 새장  
change : 교환  
cheek : 뺨   
force : 힘  
corn : 옥수수  
art : 미술  

결과 / 전체-10 정답-8 오답-2  
오답을 보시겠습니까?(1-확인, 0-종료) 1  

오답리스트  
문제-march 내가 쓴 답-행진하다 정답-행진  
문제-art 내가 쓴 답-미술 정답-예술  

영어단어 테스트를 종료합니다  

### ◈프로젝트 후 소감
단순히 생각하기만 했던 것을 직접 만들어보는 게 즐거웠다. 어떻게 해야 할지 모르겠는 기술적인 문제에 시달릴 때 인터넷에 검색도 해보고,
이것저것 넣어서 실행해보기도 하면서 원하던 방향대로 흘러갈 때 뿌듯함을 느꼈다.
다 제작하고 나서 좀 더 완성된 프로그램을 위해 추가 기능들도 생각해 보았다.
같은 단어라도 뜻이 여러 개일 수도 있는데, 현재 프로그램에서는 저장된 한 개의 뜻으로만 사용자의 입력을 판단해야 한다는 점이 아쉬웠다.
따라서 한 단어에 뜻을 여러 개 저장할 수 있도록 해보고 싶고, 문제를 낼 때 품사도 같이 적어두고 품사에 맞는 뜻을 입력하는 것도 좋을 것 같다.
또한 테스트를 보고 난 뒤 결과를 메모장에 날짜-성적으로 저장하여 나중에도 테스트 성적을 한눈에 볼 수 있도록 하고 싶다.

