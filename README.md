안녕하세요.
이나리입니다.

vue.js를 사용하여 테스트 코드를 보기 좋게 수정 했습니다.
수정 내용은 아래와 같습니다.

1. 마크업

1) 부트스트랩 삭제
  - 부트스트랩 상의 설정된 스타일을 수정하기 위한 추가 스타일을 중복으로 잡아야 하는 점, 6개 그래프가 해상도에 따라 가로 사이즈가 통일되지 않는 점 때문에 삭제했습니다.

2)스타일 삭제
  - 마크업 상의 스타일이 과해서 구조를 한 눈에 알아보기 힘들기 때문에 시각적 효율을 위해 삭제 했습니다.

3) 데이터 값 삽입
  - 변동 가능성이 있는 모든 값은 데이터에서 제어할 수 있어야 하는데 기존 테스트 코드는 시간, 그래프 수치 등 마크업 상에서 픽스된 값들이 있어 데이터로 수정 가능하도록 수정 했습니다.


2. 스크립트
  - 변동 가능한 모든 수는 데이터로 입력 가능하도록 수정 했습니다.


3. 스타일
  - 디바이스 별 최적화된 그래프 사이징을 위해 미디어쿼리를 사용 했습니다.
