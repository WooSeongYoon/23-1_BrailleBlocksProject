# A Study on the Damage Detection of Braille Sidewalk Block Based on Deep Learning
딥러닝 기반 점자 보도블록 파손율 검출 연구를 진행한 프로그램
개발 인원: 우성윤, 김민석, 김수연, 박이산, 김민호
# 개발 배경
<img src="https://github.com/user-attachments/assets/23e8320f-560a-43fb-95fd-182ca46cd907" width="500" height="250"/> <img src="https://github.com/user-attachments/assets/ebcecb58-9610-402d-9537-f7970c7dac7d" width="500" height="250"/>   
교통약자가 증가하고 있으며, 관련 서비스가 증가하고 있습니다. 하지만, 아직 미약한 부분이 있으며 인공지능을 사용하여 효과적으로 개선할 수 있는 방안을 모색하였습니다.   
그중 교통약자를 위한 이동 보조 시설물 중 하나인 점자 보도블록을 인공지능으로 탐지 및 식별하는 방법을 구상하였습니다.   

# 설계 및 구현
## 프로그램 흐름도
![image](https://github.com/user-attachments/assets/daf00ebd-aa6f-4ce2-b26a-67b7899bb4d4)   
입력장치로 일반 스마트폰 카메라 등을 사용하며 이것으로 전방의 점자 보도블록을 인식합니다. 파손된 점자 보도블록을 식별하는 해당 이벤트 트리거 발생 시, 입력받은 영상 중 한 프레임을 YOLOv5x 모델과 CNN 모델에 입력하여 결과를 추론하는 모델을 설계하고 구현하였습니다.   
## CNN 모델 구성
![image](https://github.com/user-attachments/assets/8b968700-75dc-4479-b411-9b976a0ed61b)   
CNN 모델은 YOLOv5x 모델에 의해서 인식된 파손 영역의 사진을 입력받아 파손율을 추론하는 구조로 설계하였습니다. CNN 모델의 추론 클래스는 4개로 구성하였으며 각 25%, 50%, 75%의 파손율, 그리고 0%(파손되지 않음) 파손율로 설계하였습니다.   
## 정확도
- YOLOv5 정확도   
![image](https://github.com/user-attachments/assets/02aa3c4f-2164-4aa1-8604-916a44f3083a)
- CNN 정확도   
![image](https://github.com/user-attachments/assets/589c9456-2b5c-4ea5-a6cc-18c71395f25d)
## 데이터베이스
![image](https://github.com/user-attachments/assets/078e6f55-90f1-4771-b224-f571b1b7279b)   
위치 정보인 IP주소를 키값으로 지정하고 Count를 속성을 추가해 해당 주소에서 파손된 점자 보도블록을 얼마나 확인하였는지를 파악할 수 있게 하였습니다.   

# 프로그램 실행
![image](https://github.com/user-attachments/assets/94222893-ea1a-4de5-ae2f-07d11cfa609c)   
이미지를 촬영하여 Yolov5의 입력 데이터로 넣으면, 중간 이미지 처럼 "점자 보도블록이 식별됩니다. 이후에 CNN 모델을 통해 파손율을 분류합니다.   
파손율이 분류되면 마지막 이미지 처럼 사용자에게 경고의 말을 전하고 데이터베이스에 저장됩니다.

# 결론
교통약자의 안전을 위한 점자 보도블록 파손율을 인공지능 기술을 이용하여 높은 정확도로 검출하였습니다. 또한, 도로교통 분야에서 사람들의 안전한 이동환경을 만들고 보행자의 안전을 향상할 수 있는 기술이라는 것을 검증하였습니다.   
지자체와 민, 관 등이 점자 보도블록을 식별 및 분류하는 해당 모델을 채택하여 상용화하면, 보도 이용자에게 더 나은 환경과 경험을 제공할 수 있을 것이라 예상됩니다.

# 성과
 - 2023.05.20. | [대구대학교 공학교육혁신센터] 180만원 지원금 선정   
 - 2023.06.23. | [대구대학교 Linc3.0] 캡스톤 디자인 우수상   
 - 2023.11.08. | [대한임베디드공학회] 추계학술대회 출전   
 - 2024.01.29. | [대구대학교 Linc3.0] 우즈베키스탄 성과 발표회   
 - 2024.02.19. | [대구대학교 교육혁신원] Learning SIG+ 최우수상(총장상)   
