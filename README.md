# 22300649's assignment12
2026OSS-week12 assignment

Writer : 22300649 전경호

## Project Information
**Project**

- 위 프로젝트는, 4개의 Lab으로 구성되어 있으며, Lab1에는 자동으로 1초마다 증가하는 타이머가, 
Lab2에는 start,stop,resset 기능이 있는 타이머, Lab3에선 input에 focus하고 reset하는 기능, Lab4에서는 Lab2와 동일한 기능이 구현되어 있다.

- 위 프로젝트에선, React의 Hook 기능을 연습하고 확인해볼 수 있다.

- 원본 URL : https://github.com/2026-2-OSS/week12_starter_project

## Installation
**설치, 실행 방법**

- Sample Project: 강의에서 제공한 GitHub Repository
- GitHub Classroom Repository에서 작업
- npm install → npm run dev
- README.md, package.json, App.jsx, components/ 구조 확인
- 제공된 4개의 Lab 컴포넌트 및 TODO 부분 확인

**실행 화면**


## Source Code Exploration
**주요 파일**

- Lab1_EffectTimer.jsx
- Lab2_TimerControl.jsx
- Lab3_InputFocus.jsx
- Lab4_RefTimer.jsx

**useEffect 및 useRef 분석** 

- useEffect : 렌더링 결과를 반영한 뒤 실행되는 효과를 컴포넌트와 연결하는 Hook
- useRef : "current: 초기값" 을 반환하고, 렌더링이 일어나도 같은 내용이 유지되는 Hook

## Lab Implementatoin
**4개 Lab 구현 내용 및 실행 결과**
1. Lab 1: useEffect에 setInterval()과 cleanInterval() method를 사용, setCount로 타이머가 계속 증가하도록 구현. 화면 렌더부터 매 초마다 숫자가 계속해서 올라감.
2. Lab 2: running으로 관리되던 타이머에 따라, running이 true일 때 setInterval로 숫자 증가(setCount()). stop버튼으로 running을 false로 변경, reset은 stop()에 setCount(0). start버튼을 누르면 매 초마다 숫자 증가. stop 시 일시정지, reset 시 reset.
3. Lab 3: useRef를 사용해 화면의 input과 객체 연결. focus와 value=""를 사용해 포커스와 초기화 구현. focus 버튼을 누르면 input으로 커서 focus 작동. reset 시 내용 초기화.
4. Lab 4: Lab2와 기능은 동일하나, useRef를 사용해 current 관리를 진행.

## Lab Comparison
**STEP 3의 비교 분석 질문 4개에 대한 답변**

1. useEffect의 Dependency Array가 필요한 이유: 
    - Dependency Array는 effect를 언제 다시 실행할지 React에게 알려 주는 기준. 배열 안의 값이 이전 렌더와 달라졌을 때만 effect가 재실행된다. []이면 마운트 시 한 번만 실행, 배열을 생략하면 매 렌더 후 실행, [running]이면 running이 바뀔 때만 실행된다.

2. Cleanup을 사용하지 않으면 발생할 수 있는 문제
    - 타이머가 정리되지 않음. 계속해서 interval이 실행되기 때문에, 메모리를 낭비.

3. useState와 useRef의 가장 중요한 차이
    - useState는 set method를 호출하면 컴포넌트가 다시 렌더링되어 화면이 갱신된다. useRef는, .current를 바꿔도 리렌더가 일어나지 않는다.

4. LAB 2와 LAB 4의 Timer 관리 방식 차이
    - Lab2는, 타이머의 생성과 reset을 effect가 맡는다. 버튼은 running만 바꾸고, effect에서 running의 변화에 따라 interval을 만들고 정리한다. 
    - Lab4는, 버튼이 setInterval을 호출해 id를 timerRef.current에 저장하고, null로 초기화하며 cleanInterval한다. 

## Customizing
**수정한 데이터, 텍스트, 스타일 및 파일명**

1. App.jsx의 제목 뒤에 22300649를 붙임.
2. App.jsx의 footer에 "22300649 assignment 12" 텍스트 추가.
3. App.css의 .count의 font-size를 키움.


## Deployment
https://2026-oss-assign12-vert.vercel.app/

## Weekly Review
**새롭게 배운 내용 3가지**

- useEffect와 useRef의 주요 기능
- useEffect의 Dependancy array에 따른 렌더링 기준 변화
- setInterval, cleanInterval로 정리하는 것

**AI Usage** 
- 학습 자료를 전달하라고 요청 뒤 자료로 공부하며 해결
- 코드에는 관여하지 않음.

**느낀 점**
- 이번에는 지난 array와 다르게 좀 더 이해가 잘 된 거 같아 뿌듯했고, 코드 분석이 점점 더 빨라지는 거 같아 스스로의 성장함을 느꼈다.