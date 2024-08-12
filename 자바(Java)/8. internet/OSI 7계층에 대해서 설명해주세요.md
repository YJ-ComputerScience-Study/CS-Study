## OSI 7계층에 대해서 설명해주세요.

- OSI 7계층(Open Systems Interconnection Reference Model 7 Layers) : **국제 표준화 기구에서 네트워크 통신이 이뤄지는 과정을 7단계로 나눈 네트워크 표준 모델**

- 각 계층은 독립적이며 데이터를 송신할 때 각 계층에서 필요한 정보를 추가해 데이터를 가공함. 이때 제어 정보를 담은 **헤더(header)** 나 **트레일러(trailer)** 가 붙는데 이 과정을 **데이터 캡슐화**라고 함. 데이터 캡슐화하는 이유는 수신부의 같은 계층에서 데이터 호환성을 높이고 오류의 영향을 최소화하기 위해서임. **수신부**에서는 헤더와 트레일러 분석해 제거하는 **역캡슐화**를 진행하며 각 계층에 필요한 제어 정보를 얻음.

### OSI 7계층 전체 구조

![alt text](https://miro.medium.com/v2/resize:fit:640/format:webp/1*7yPBGx_K8GymgeGfzhfznA.gif)

> 이미지 출처 : [📢OSI Model — 7 Layers — Dataflow example 📧](https://medium.com/@sreekanth.thummala/osi-model-7-layers-dataflow-example-b711dbca5eff)

1. **물리 계층** : 데이터를 비트 단위의 0과 1로 변환한 후 장비를 사용해 전송하거나 전기 신호를 데이터로 복원함. 리피터, 허브 등이 물리 계층에 해당하는 장비임.

2. **데이터 링크 계층** : 데이터 흐름을 관리하며 데이터의 오류 검출 및 복구 등을 수행함. 브리지, 스위치, 이더넷이 데이터 링크 계층의 장비에 해당됨.
3. **네트워크 계층** : 데이터를 송신부에서 수신부까지 보내기 위한 최적 경로를 선택하는 라우팅을 수행함. 이때 선택한 최적 경로를 라우트라고 함. 네트워크 계층의 장비로는 라우터가 있음.
4. **전송 계층** : 신뢰성 있는 데이터를 전달하기 위한 계층으로 TCP, UDP 같은 전송 방식과 포트 번호 등을 결정함.
5. **세션 계층** : 세션의 유지 및 해제 등 응용 프로그램 간 통신 제어와 동기화를 함.
6. **표현 계층** : 데이터를 표준화된 형식으로 변경함.
7. **응용 계층** : HTTP, FTP 등의 프로토콜을 사용자가 직접적으로 접하는 응용 프로그램의 UI를 통해 제공함.

### 기존 네트워크 공부 내용 참고

[네트워크/1. 네트워크 레이어와 HTTP 프로토콜/OSI 7 layer란.md](https://github.com/YJ-ComputerScience-Study/CS-Study/blob/main/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC/1.%20%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%20%EB%A0%88%EC%9D%B4%EC%96%B4%EC%99%80%20HTTP%20%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C/OSI%207%20layer%EB%9E%80.md)
