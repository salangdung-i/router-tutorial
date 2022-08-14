# REACT ROUTER 주요 개념

react router는 단순히 URL을 함수나 구성요소에 일치시키는 것이 아니다. URL에 매핑되는 전체 사용자의 인터페이스를 구축하는 것 이므로 익숙한 것보다 더 많은 개념이 포함될 수 있다. React Router의 3가지 주요한 작업.

## 주요 작업

1. 히스토리 스택 구조 및 조작
2. URL을 경로에 일치시키기
3. 경로 일치에서 중첩된 UI 랜더링

### 정의

- URL : 주소 표시줄의 URL. 많은 사람들이 URL과 경로라는 용어를 같은 의미로 사용하지만 이것은 React Router 경로가 아니라 URL이다.
- location : 내장 브라우저의 window.location 객체를 기반으로 하는 React Router 특정 객체이다. "사용자가 있는 위치"를 나타낸다.
- location status : URL에 인코딩되지 않는 location위에 함께 지속되는 값이다. 해시 또는 검색 매개 변수와 비슷하지만 브라우저 메모리에 보이지 않게 저장된다.
- history stack : 사용자가 탐색할 떄 브라우저는 스택의 각 위치를 추적한다. 브라우저에서 뒤로 버튼을 부로고 있으면 브라우저의 기록스택을 볼수 있다.
- CSR(Client Side Routing) : 일반 HTML 문서를 다른 문서에 링크 할 수 있으며 브라우저는 히스토리 스택 자체를 처리한다. 클라이언트 측 라우팅을 사용하면 개발자가 서버에 문서를 요청하지 않고로 브라우저 기록 스택을 조작할수 있다.
- History : React Router 가 URL의 변경사항을 구독할수 있게 하고 프로그래밍 방식으로 브라우저 기록 스택을 조작하기 위한 API 제공
- History Action : POP, PUSH, REPLACE... 사용자는 다음 세가지 이유 중 하나로 URL에 도달할수 있다. 새 항목이 히스토리 스택에 추가 될떄의 푸시, 교체는 새 항목을 푸시하는 대신 스택의 현재 항목을 교체한다는 점을 제외하고는 비슷하다. 마지막으로 사용자가 브라우저 크롬에서 뒤로 또는 앞으로 버튼을 클릭하면 POP이 발생한다.
- segment : 문자사이의 URL또는 경로 패턴 부붕니다. 예를들어 "/users/123"에는 두 개의 세그먼트가 있다.
- Path Patten : URL처럼 보이지만 동적 세그먼트 ("users/:userId") 또는 별 모양 세그먼트, URL이 아니라 ReactRouter가 일치시킬 패턴이다.
- Router : 다른 모든 구성 요소와 hook이 작동하도록 하는 상태 저장 최상위 구성요소이다.
- Route Config : 경로일치의 분기를 생성하기 위해 현재 위치에 대해 순위를 매기고 일치할 경로 개체의 트리이다.
- Route : 일반적으로 또는 모양이 있는 개체 또는 경로 요소이다. path, element... <Route path element> .path 경로 패턴이다. 경로 패턴이 현재 URL과 일치하면 요소가 랜더링된다.
- Route element Or <Route> : 이 요소의 props를 일으며? <Routes>에서 경로를 만들수 있지만, 그렇지 않으면 아무작업도 수행하지 않다.
- Nested Routes (중첩 경로) - 경로는 자식을 가질수도 있고 각 routed는 세그먼트를 통해 URL의 일부를 정의하기 떄문에 단일 URL은 트리의 중접 branch에 있는 여러 경로와 일치할수 있다. 이렇게 하면 outlet, realative link등을 통해 레이아웃 중첩이 가능하다.
- Relative links -
- Match
- Matches : 현재 위치와 일치하는 경로의 배열, 이 구조는 중첩 경로를 활성화 한다.
- Parent Route : 하위 경로가 있는 경로
- Outlet : 일치 항목 집합에서 다음 일치 항목을 랜더링하는 구성요소이다.
- Index Route : 경로가 없는 자식 경로는 부모의 URL에 있는 부모의 콘센트에서 랜더링된다.
- Layout Route : 경로가 없는 상위 경로로, 특정 레이아웃 내에서 하위 경로를 그룹화 하는대만 사용된다.
