# scene_graph_generation_in-the-battlefield

본 프로젝트는 ETRI에서 연구연수생으로서 참여한 프로젝트이며 비디오기반 프레임 단위별로 장면그래프를 생성하는 방법이 연구주제였습니다.

## 1. 규칙기반 관계 추론

모든 관계를 정의하기 어려워 객체를 특정 기준에 따라 분류한 뒤에 관계 정의를 진행했습니다. 프로젝트에서는 정적 객체와 동적 객체로 분류한 뒤에 관계 정의를 진행했습니다. 정적 객체는 비디오 상에서 움직이지 않는 객체이고 동적 객체는 비디오 상에서 움직이는 객체를 말합니다.
<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/7b0ea8f3-27e0-486b-95d0-586c69352ab9" />


이후 객체를 분류한 뒤에 각 객체분류마다 규칙 기반 관계추론을 진행한 뒤에 분류별 관계를 합치는 방식으로 장면에 대한 관계를 생성했습니다.
<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/7949ef06-a3b1-4b49-a8e3-3277f650cc83" />
 
<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/5b3e6747-ead8-4d30-946f-cbd3c1907c23" />

중간에 코사인 유사도만으로 exit와 move away를 구분하지 못하는 문제가 발생하여 객체 간의 거리를 제한함으로써 exit 추론 조건을 강화했습니다.

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/b3364dc3-01c2-42b5-94b4-9fd7bb0c010b" />

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/be93cfe1-1afe-4ec3-a231-089c2494bf42" />

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/899e90da-5936-408f-9220-f2a527a30c5b" />




## 2. VLM 기반 관계 추론

객체 탐지 및 추적 데이터를 프롬프트로 이용하고 현재 프레임과 바로 이전 프레임을 영상으로 정의한 뒤에 VLM에 INPUT으로 넣는 방식으로 장면에 대한 동적 관계를 추출했습니다.
프롬프트는 역할 부여, FEW-SHOT PROMPTING, 객체 및 관계 제한 등을 프롬프트로 구성하여 관계를 추출했습니다.

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/428f0efc-b640-465b-b3cd-a1676a5e481c" />

## 3. 발전방향
<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/56e8f0ff-bd43-45c3-8f91-716dd2716e39" />



