## 회의록
#### 250714 (월)
- 홍수 및 침수 상황을 자동으로 감지하고 차단·알림하는 시스템 기획을 구체화했음.
- AI 활용을 위한 객체 탐지 + 예측 모델 조합에 대해 논의함.
- 배수로, 하수구 등 실제 사례 기반 대응 구조를 반영하기로 했음.
- 데이터 증강, 대피 경로 예측, 디지털 트윈 활용 등 부가 기능 아이디어도 도출됨.
- 다음 미팅 전까지 프로토타입 흐름 스케치 및 기술 타당성 조사를 진행할 예정.
--------------------
#### 250715 (화)
#### 회의 내용
- 기술 흐름, 아키텍처 구조화
- 모형 제작 방향 토의
- 1주차 할 일, 역할 구체화
- 피해 사례, 기술 스택 등 자료 조사 
##### 아키텍처 요약
- Jetson + 카메라: 실시간 홍수 상황 감지 (AI 추론 수행)
- 중앙 제어 서버 (서버 백엔드): 추론 결과 수신, 판단 로직을 통해 rpi5에 제어 명령 전송
- Raspberry Pi 5: 모터 제어(차수막 작동) 수행
- 웹 백엔드 (API 서버): 사용자 요청 처리, 경고 상태 API 제공
- 웹 프론트 (Vue 등): 실시간 영상 표시, 수동 제어 UI, 경고 알림
- Nginx: 프론트와 API 서버를 연결하는 리버스 프록시
