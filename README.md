# Redux_study

인프런 - 처음 만난 리덕스(Redux)

# 1강. Redux 소개

### Redux의 탄생

- SPA의 등장 -> 웹 사이트 규모 증가 -> 상태관리의 복잡도 증가
- 수많은 상태들을 어떻게 효과적으로 관리할 것인가?

### Flux 아키텍쳐

- 단방향 데이터 흐름을 활용한 리액트용 애플리케이션 아키텍처
- Redux는 Flex를 구현한 라이브러리

### Three Principles of Redux

1. Single source of truth : 단 하나의 진실의 원천
2. State is read-only : 상태 값은 읽기 전용
3. Changes are made with pure functions : 변화는 순수 함수들을 통해 이루어짐

### Redux Data Flow

- Action > Dispatcher > Reducer로 이어지는 단방향 데이터 흐름

# 2강. Redux 시작하기

### Redux 구성요소

- Store : Redux의 데이터들을 저장하기 위한 저장소
- State : Redux Store에 저장되어 있는 데이터
- Action : Redux Store에 저장된 데이터에 변화를 주기 위한 행동
- Action Creator : Action 객체를 생성하는 역할을 하는 함수
- Reducer : Redux State에 변화를 주는 역할

### Immutability (불변성)

- State is read-only + Changes are made with pure functions
- Redux Toolkit은 immutacbility를 지키기 위해 immer.js 라이브러리 사용

### 어떤 경우에 Redux를 사용해야 할까?

- 하나의 상태를 여러 컴포넌트에서 접근해야 할 경우
- 한 곳에서 상태들을 관리하고 싶을 경우

### Redux vs Context API

- redux-devtools
- Redux Store

# 3강. Store

### Store 저장하다

- State management : 상태를 관리하는 라이브러리
- 새로고침, 재부팅 시에 Redux Store의 데이터 초기화

### Dispatcher 발송하는 역할

- Action을 발송하는 역할
- store.dispatch(action)

### Store 관련 함수

- createStore(reducer, [preloadedState], [enhancer])

  - Redux Store 생성
  - 단 하나의 Store만 존재해야 함
  - reducer : Redux State에 변화를 주는 역할을 하는 Pure function
  - 모든 reducer들을 합친 rootReducer가 들어감
  - preloadedState : 초기 상태값
  - enhancer : Redux Store의 기능을 향상 시켜주는 역할 (middleware)

- applyMiddleware(...middleware)

  - 여러 개의 middleware를 하나로 합쳐주는 역할을 하는 함수
  - middleware : Redux에 원하는 기능을 추가할 수 있게 해주는 함수

- store.getState() : State를 가져오는 함수

- store.dispatch(action) : action을 발송하는 함수

### 4강. Action과 Action Creator

- Action : Redux State에 변화를 주기 위한 행동
    - JavaScript 객체 형태로 존재