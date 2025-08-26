# scene_graph_generation_in-the-battlefield

### 본 프로젝트는 ETRI에서 연구연수생으로서 참여한 프로젝트이며 비디오기반 프레임 단위별로 장면그래프를 생성하는 방법이 연구주제였습니다.

## 1. 규칙기반 관계 추론

### 모든 관계를 정의하기 어려워 객체를 특정 기준에 따라 분류한 뒤에 관계 정의를 진행했습니다. 프로젝트에서는 정적 객체와 동적 객체로 분류한 뒤에 관계 정의를 진행했습니다. 정적 객체는 비디오 상에서 움직이지 않는 객체이고 동적 객체는 비디오 상에서 움직이는 객체를 말합니다.

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/76abf443-bf65-405d-92f7-9e278a1d0b3e" />



### 이후 객체를 분류한 뒤에 각 객체분류마다 규칙 기반 관계추론을 진행한 뒤에 분류별 관계를 합치는 방식으로 장면에 대한 관계를 생성했습니다.

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/e2a6828c-cbcb-45fd-86c3-31c0b74eab26" />

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/c7b28d62-4285-4c5a-a4bc-857e3f04d4a0" />

### 중간에 코사인 유사도만으로 exit와 move away를 구분하지 못하는 문제가 발생하여 객체 간의 거리를 제한함으로써 exit 추론 조건을 강화했습니다.

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/30764605-c6c4-4c85-9765-42104f5de93e" />

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/98d214b0-8ef7-4642-94fe-752beda9c63a" />

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/c3e121c2-77cc-4e63-b060-729fa9facedc" />




## 2. VLM 기반 관계 추론

### 객체 탐지 및 추적 데이터를 프롬프트로 이용하고 현재 프레임과 바로 이전 프레임을 영상으로 정의한 뒤에 VLM에 INPUT으로 넣는 방식으로 장면에 대한 동적 관계를 추출했습니다.
### 프롬프트는 역할 부여, FEW-SHOT PROMPTING, 객체 및 관계 제한 등을 프롬프트로 구성하여 관계를 추출했습니다.

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/c51d7a32-5b7c-4f35-b6b5-5c83ed6a0aa6" />


## 3. 발전방향
<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/c84e7fd4-f997-437a-80ce-d78740859b14" />




