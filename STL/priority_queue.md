### priority_queue의 템플릿 인자 3개 의미
- 첫 번째 인자: 저장할 데이터의 타입 (예: int, string, 사용자 정의 타입 등)
- 두 번째 인자: 내부에서 사용할 컨테이너 타입 (기본값은 vector<T>, deque<T>도 가능)
- 세 번째 인자: 정렬 기준(비교 함수 객체) (기본값은 less<T> = 최대 힙, 직접 지정하면 최소 힙 등 가능)
예시 ``priority_queue<int, vector<int>, greater<int>> pq;``

* 기본값
priority_queue<int>는 내부적으로 priority_queue<int, vector<int>, less<int>>와 같습니다.
즉, 비교 함수와 컨테이너를 지정하지 않으면 자동으로 최대 힙이 됩니다

비교 함수만 바꾸고 싶으면
priority_queue<int, vector<int>, greater<int>>처럼 세 번째 인자만 바꿔주면 최소 힙이 됩니다. (greater를 사용하면 min_heap이 됨.)
