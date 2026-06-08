# Unity Robotics Hub 기반 로봇 시뮬레이션 커리큘럼

> **과정명**: Unity Robotics Hub를 활용한 로봇 시뮬레이션 및 제어
> **학습 기간**: 1학기 (15주, 주 3시간 수업 + 실습)
> **난이도**: 초급 ~ 중고급
> **사전 준비물**: Unity 2021.3 LTS 이상, ROS (Noetic 또는 ROS 2 Humble), Python 3, Git

---

## 📋 목차

1. [과정 개요](#1-과정-개요)
2. [주별 커리큘럼](#2-주별-커리큘럼)
   - [1주차: 오리엔테이션 및 환경 설정](#1주차-오리엔테이션-및-환경-설정)
   - [2주차: Unity 기초 - 씬 구성 및 물리](#2주차-unity-기초---씬-구성-및-물리)
   - [3주차: ROS 기초 및 개념](#3주차-ros-기초-및-개념)
   - [4주차: Unity-ROS 연결 (TCP 커넥터)](#4주차-unity-ros-연결-tcp-커넥터)
   - [5주차: URDF 임포트 및 로봇 모델링](#5주차-urdf-임포트-및-로봇-모델링)
   - [6주차: 센서 시뮬레이션](#6주차-센서-시뮬레이션)
   - [7주차: ArticulationBody와 로봇 제어 기초](#7주차-articulationbody와-로봇-제어-기초)
   - [8주차: 중간 프로젝트](#8주차-중간-프로젝트)
   - [9주차: MoveIt 기반 모션 플래닝](#9주차-moveit-기반-모션-플래닝)
   - [10주차: Pick and Place 구현](#10주차-pick-and-place-구현)
   - [11주차: 합성 데이터 생성](#11주차-합성-데이터-생성)
   - [12주차: 디지털 트윈 기초](#12주차-디지털-트윈-기초)
   - [13주차: 고급 주제 - 멀티 로봇, RL, HRI](#13주차-고급-주제)
   - [14주차: 기말 프로젝트](#14주차-기말-프로젝트)
   - [15주차: 기말 발표 및 총평](#15주차-기말-발표-및-총평)
3. [평가 기준](#3-평가-기준)
4. [참고 자료](#4-참고-자료)

---

# 1. 과정 개요

## 1.1 과정 설명

* 본 과정은 **Unity Robotics Hub**를 활용하여 로봇 시뮬레이션의 전반을 학습합니다.
* Unity의 강력한 3D 렌더링 엔진과 ROS (Robot Operating System)의 로봇 제어 프레임워크를 결합하여 <br>
  로봇 모델링, 시뮬레이션, 센서 데이터 생성, 모션 플래닝, 디지털 트윈까지를 실습 위주로 학습합니다.

## 1.2 학습 목표

이 과정을 수료하면 다음 역량을 갖추게 됩니다:

| 역량 | 설명 |
|---|---|
| **Unity 시뮬레이션 환경 구축** | Unity 에디터에서 3D 씬을 구성하고 물리 엔진을 활용할 수 있다 |
| **ROS 이해 및 활용** | ROS의 기본 개념(토픽, 서비스, 액션)을 이해하고 명령어를 다룰 수 있다 |
| **Unity-ROS 통합** | TCP 커넥터를 통해 Unity와 ROS 간 양방향 통신을 구성할 수 있다 |
| **로봇 모델 임포트** | URDF 포맷의 로봇 모델을 Unity로 가져와 시뮬레이션할 수 있다 |
| **센서 시뮬레이션** | LiDAR, RGB-D 카메라, IMU 등 가상 센서를 구성하고 데이터를 수집할 수 있다 |
| **로봇 제어** | ArticulationBody를 이용한 로봇 팔/모바일 로봇 제어를 구현할 수 있다 |
| **모션 플래닝** | MoveIt과 통합하여 충돌 회피 경로 계획을 수립할 수 있다 |
| **합성 데이터 생성** | 시뮬레이션 환경에서 AI 학습용 합성 데이터를 생성할 수 있다 |
| **디지털 트윈** | 실제 로봇 시스템의 디지털 트윈을 구축할 수 있다 |

## 1.3 사전 요구사항

| 구분 | 내용 |
|---|---|
| **프로그래밍** | C# 기초 문법 (변수, 함수, 클래스), Python 기초 |
| **운영체제** | Windows 10/11 또는 Ubuntu 20.04/22.04 |
| **하드웨어** | GPU 권장 (NVIDIA GTX 1060 이상), RAM 16GB 이상 |
| **선수 지식** | 3D 공간 좌표계 이해 (추천), 선형대수 기초 (추천) |

## 1.4 필요 소프트웨어 스택

| 소프트웨어 | 버전 | 용도 |
|---|---|---|
| Unity Hub + Unity Editor | 2021.3 LTS 이상 | 시뮬레이션 엔진 |
| ROS (선택) | Noetic (Ubuntu 20.04) 또는 ROS 2 Humble (Ubuntu 22.04) | 로봇 미들웨어 |
| Python | 3.8+ | ROS 스크립트 |
| Git | 최신 버전 | 버전 관리 |
| Docker (선택) | 최신 버전 | ROS 환경 컨테이너 |

### ROS 미설치 환경에서의 대체 방법

ROS가 설치되지 않은 Windows 환경에서는 다음 방법을 사용할 수 있습니다:

- **방법 1**: WSL2 (Windows Subsystem for Linux)에 ROS 설치
- **방법 2**: Docker 컨테이너로 ROS 실행
- **방법 3**: ROS 대신 Unity TCP 커넥터만 사용하여 시뮬레이션 로직은 C#으로 직접 구현

## 1.5 Unity Robotics Hub 패키지 목록

| 패키지 | 설명 |
|---|---|
| `com.unity.robotics.urdf-importer` | URDF 파일을 Unity 씬으로 임포트 |
| `com.unity.robotics.ros-tcp-connector` | Unity ↔ ROS TCP 통신 |
| `com.unity.simulation.sensors` | LiDAR, 카메라, IMU 등 센서 패키지 |
| `com.unity.simulation.foundation` | 시뮬레이션 기반 프레임워크 |

---

# 2. 주별 커리큘럼

---

## 1주차: 오리엔테이션 및 환경 설정

### 학습 목표
- 과정 전반의 흐름 이해
- Unity Robotics Hub 개발 환경 구축
- 첫 번째 Unity-ROS 연결 테스트

### 세부 내용

#### 1.1 강의 개요 (1시간)
- 로봇 시뮬레이션의 필요성과 활용 분야
- 주요 시뮬레이터 비교 (Gazebo, Isaac Sim, Unity, MuJoCo)
  - **Unity 장점**: 고품질 렌더링, Asset Store, C# 스크립팅, VR/AR 연동
  - **Unity 단점**: 로봇 전용 기능은 add-on, 물리 튜닝 필요
  - **Isaac Sim과의 차이점**: RL 대규모 병렬 학습은 불가, 대신 HMI/시각화에 강점
- Unity Robotics Hub의 구조와 생태계

#### 1.2 실습: 개발 환경 설치 (1.5시간)

**Step 1: Unity Hub 및 Unity Editor 설치**
```bash
# Unity Hub 다운로드
# https://unity.com/download
# Unity 2021.3 LTS 설치 (Windows: C:\Program Files\Unity\Hub\Editor\2021.3.x)
```

**Step 2: ROS 환경 준비 (Windows WSL2 예시)**
```powershell
# PowerShell (관리자)
wsl --install -d Ubuntu-22.04
```

```bash
# WSL2 Ubuntu 내
sudo apt update && sudo apt upgrade -y
sudo apt install -y ros-humble-ros-base python3-colcon-common-extensions
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

**Step 3: Unity Robotics Hub 클론**
```bash
git clone https://github.com/Unity-Technologies/Unity-Robotics-Hub.git
```

**Step 4: ROS TCP 엔드포인트 설치**
```bash
# WSL2 또는 Ubuntu 내
mkdir -p ~/ros_ws/src
cd ~/ros_ws/src
git clone -b main https://github.com/Unity-Technologies/ROS-TCP-Endpoint.git
cd ~/ros_ws
colcon build
source install/setup.bash
```

#### 1.3 과제
1. Unity Hub + Editor 설치 완료
2. WSL2 / Docker에 ROS 환경 구성
3. Unity-Robotics-Hub 레포지토리 클론 및 디렉토리 구조 파악 (README.md 읽고 요약)
4. ROS-TCP-Endpoint 빌드 성공

> **참고**: ROS 설치에 어려움이 있는 경우 Docker 이미지(`osrf/ros:humble-desktop`)를 사용하거나, 4주차까지 Unity 단독으로 작업 가능합니다.

---

## 2주차: Unity 기초 - 씬 구성 및 물리

### 학습 목표
- Unity 에디터 인터페이스에 익숙해지기
- 3D 오브젝트 배치 및 Transform 다루기
- Unity 물리 엔진(PhysX) 기본 이해
- C# 스크립팅 기초

### 세부 내용

#### 2.1 Unity 에디터 둘러보기 (1시간)
- **핵심 창**: Scene, Game, Hierarchy, Project, Inspector
- **게임 오브젝트와 컴포넌트** 관계
- **좌표계**: World 좌표 vs Local 좌표, 왼손 좌표계 (Unity 표준)
- **프리팹(Prefab)** 개념과 활용

#### 2.2 실습: 간단한 환경 구성 (1시간)

```c#
// 1. 오브젝트 회전 스크립트
using UnityEngine;

public class RotateObject : MonoBehaviour
{
    public float speed = 30f;
    public Vector3 axis = Vector3.up;

    void Update()
    {
        transform.Rotate(axis, speed * Time.deltaTime);
    }
}
```

```c#
// 2. 키보드로 오브젝트 이동
using UnityEngine;

public class SimpleMovement : MonoBehaviour
{
    public float moveSpeed = 2f;

    void Update()
    {
        float h = Input.GetAxis("Horizontal");
        float v = Input.GetAxis("Vertical");
        Vector3 move = new Vector3(h, 0, v) * moveSpeed * Time.deltaTime;
        transform.Translate(move, Space.World);
    }
}
```

#### 2.3 물리 엔진 기초 (0.5시간)

| 컴포넌트 | 설명 |
|---|---|
| `Rigidbody` | 물리 영향 받는 오브젝트 (중력, 충돌, 힘) |
| `Collider` (Box, Sphere, Mesh) | 충돌 감지 영역 |
| `Physic Material` | 마찰력, 바운스 계수 |
| `FixedUpdate()` | 물리 연산 타이밍에 동기화되는 메서드 |

```c#
// Rigidbody에 힘 가하기
using UnityEngine;

public class ApplyForce : MonoBehaviour
{
    private Rigidbody rb;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void FixedUpdate()
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            rb.AddForce(Vector3.up * 5f, ForceMode.Impulse);
        }
    }
}
```

#### 2.4 실습: 물리 테스트 월드 만들기 (0.5시간)
- 평면(Plane) 바닥 생성, 큐브/구체 배치
- 각 오브젝트에 Rigidbody + 다양한 Collider 할당
- Physic Material 생성 (마찰 0.8, 바운스 0.5)
- 큐브가 경사면을 굴러 내려가는 시뮬레이션

| 항목 | 값 |
|---|---|
| 바닥 Plane 크기 | 20 x 20 |
| 구체 Radius | 0.5 |
| 큐브 크기 | 1 x 1 x 1 |
| 중력 | -9.81 m/s² (기본값) |

#### 2.5 과제
1. Unity Roll-a-Ball 튜토리얼 완료 (공 굴리기 게임)
2. 큐브 5개를 계단 형태로 쌓고 Rigidbody로 물리 붕괴 시뮬레이션
3. 다음 개념을 각각 한 문장으로 설명: `Transform`, `Collider`, `Prefab`, `FixedUpdate`

---

## 3주차: ROS 기초 및 개념

### 학습 목표
- ROS 철학과 아키텍처 이해
- ROS 통신 방식 (Topic, Service, Action) 이해
- 기본 ROS 명령어 숙달
- ROS 패키지 구조 이해

### 세부 내용

#### 3.1 ROS 개요 (1시간)
- **ROS란?**: 분산 프로세스 간 통신을 위한 미들웨어
- **핵심 개념**:

| 개념 | 설명 | 비유 |
|---|---|---|
| **Node** | 최소 실행 단위 프로세스 | 프로그램 하나 |
| **Master (ROS 1)** | 노드 간 이름 관리 서비스 | 전화 교환국 |
| **Topic** | 비동기 단방향 메시지 스트림 | 출판-구독 |
| **Service** | 동기 양방향 요청-응답 | 함수 호출 |
| **Action** | 장기 실행 태스크 (피드백 포함) | 진행률 있는 작업 |
| **Message** | 데이터 구조체 (통신 형식) | JSON 스키마 |
| **Bag** | 메시지 기록/재생 도구 | 블랙박스 |

- **ROS 1 vs ROS 2 주요 차이**:

| 항목 | ROS 1 (Noetic) | ROS 2 (Humble) |
|---|---|---|
| 통신 미들웨어 | TCPROS/UDPROS | DDS (Data Distribution Service) |
| 마스터 | roscore 필요 | 분산형 (디스커버리 자동) |
| 실시간 지원 | 제한적 | 지원 |
| 멀티 플랫폼 | Linux 중심 | Windows, macOS, Linux |
| 보안 | 없음 | SROS2 지원 |

#### 3.2 실습: ROS 기본 명령어 (1시간)

```bash
# ROS Master 실행 (ROS 1)
roscore

# 노드 실행
rosrun turtlesim turtlesim_node
rosrun turtlesim turtle_teleop_key

# Topic 리스트 확인
rostopic list -v

# Topic 메시지 보기
rostopic echo /turtle1/cmd_vel

# Topic publish 해보기
rostopic pub /turtle1/cmd_vel geometry_msgs/Twist \
  "linear: {x: 2.0, y: 0.0, z: 0.0}
   angular: {x: 0.0, y: 0.0, z: 1.8}"

# rqt_graph로 노드 관계 시각화
rqt_graph
```

#### 3.3 ROS 패키지 구조 (0.5시간)
```
my_robot_pkg/
├── CMakeLists.txt       # 빌드 설정
├── package.xml          # 패키지 메타데이터
├── launch/              # 런치 파일
│   └── my_robot.launch
├── urdf/                # 로봇 모델
│   └── my_robot.urdf
├── msg/                 # 커스텀 메시지
│   └── MyMessage.msg
├── srv/                 # 서비스 정의
│   └── MyService.srv
├── src/                 # C++ 소스 (ROS 1)
├── scripts/             # Python 스크립트
└── config/              # 설정 파일
```

#### 3.4 실습: 간단한 발행자-구독자 만들기 (0.5시간)

```python
# talker.py (Python 발행자)
#!/usr/bin/env python3
import rospy
from std_msgs.msg import String

def talker():
    rospy.init_node('talker', anonymous=True)
    pub = rospy.Publisher('chatter', String, queue_size=10)
    rate = rospy.Rate(1)  # 1 Hz

    while not rospy.is_shutdown():
        msg = f"Hello from Unity Robotics! {rospy.get_time()}"
        rospy.loginfo(msg)
        pub.publish(msg)
        rate.sleep()

if __name__ == '__main__':
    try:
        talker()
    except rospy.ROSInterruptException:
        pass
```

```python
# listener.py (Python 구독자)
#!/usr/bin/env python3
import rospy
from std_msgs.msg import String

def callback(msg):
    rospy.loginfo(f"Received: {msg.data}")

def listener():
    rospy.init_node('listener', anonymous=True)
    rospy.Subscriber('chatter', String, callback)
    rospy.spin()

if __name__ == '__main__':
    listener()
```

#### 3.5 과제
1. turtlesim에서 거북이를 사각형으로 움직이도록 `rostopic pub` 명령어 시퀀스 작성
2. talker/listener 예제 직접 작성 및 실행 (ROS 노드 간 통신 확인)
3. ROS Topic과 Service의 차이점을 200자 이내로 설명
4. `rosbag` 명령어로 turtlesim 데이터 30초 녹화 후 재생

---

## 4주차: Unity-ROS 연결 (TCP 커넥터)

### 학습 목표
- ROS-TCP-Connector 아키텍처 이해
- Unity ↔ ROS 간 메시지 송수신
- ROS 메시지 타입과 Unity C# 클래스 매핑
- 양방향 통신 구현

### 세부 내용

#### 4.1 ROS-TCP-Connector 아키텍처 (1시간)

```
┌──────────────────┐         TCP Socket         ┌──────────────────┐
│    Unity Editor   │ ◄──────────────────────►   │  ROS Endpoint    │
│                   │     (포트 10000)            │   (Python Node)  │
│  RosTcpConnector  │                            │                  │
│  ┌──────────────┐│                            │ros_tcp_endpoint │
│  │ Publisher    ││                            │  ┌────────────┐ │
│  │ Subscriber   ││                            │  │ Subscriber │ │
│  │ Service      ││                            │  │ Publisher  │ │
│  └──────────────┘│                            │  └────────────┘ │
└──────────────────┘                            └──────────────────┘
```

**통신 흐름**:
1. Unity의 `RosTcpConnector`가 ROS Endpoint에 TCP 연결
2. Unity Publisher → ROS Subscriber: Unity에서 ROS로 메시지 전송
3. ROS Publisher → Unity Subscriber: ROS에서 Unity로 메시지 전송
4. Service: 양방향 요청-응답

#### 4.2 실습: Unity 프로젝트에 ROS-TCP-Connector 추가 (1시간)

**Step 1: 패키지 설치**
```
Window > Package Manager > + (Add package from git URL)
git URL 입력:
  https://github.com/Unity-Technologies/ROS-TCP-Connector.git?path=/com.unity.robotics.ros-tcp-connector
  https://github.com/Unity-Technologies/URDF-Importer.git?path=/com.unity.robotics.urdf-importer
```

**Step 2: ROS 설정**
```
GameObject > ROS > ROS Connection
  - ROS IP Address: (WSL2 IP 또는 로컬 IP)
  - ROS Port: 10000
```

**Step 3: Unity → ROS 메시지 발행**
```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Std;

public class UnityToRosPublisher : MonoBehaviour
{
    private ROSConnection ros;
    public string topicName = "/unity_chatter";

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.RegisterPublisher<StringMsg>(topicName);
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            StringMsg msg = new StringMsg($"Hello from Unity at {Time.time:F2}s");
            ros.Publish(topicName, msg);
            Debug.Log($"Published: {msg.data}");
        }
    }
}
```

**Step 4: ROS에서 수신 확인**
```bash
# WSL2 또는 Ubuntu 터미널
ros2 topic echo /unity_chatter  # ROS 2
# 또는
rostopic echo /unity_chatter    # ROS 1
```

**Step 5: ROS → Unity 메시지 구독**
```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Std;

public class RosToUnitySubscriber : MonoBehaviour
{
    void Start()
    {
        ROSConnection ros = ROSConnection.GetOrCreateInstance();
        ros.Subscribe<StringMsg>("/ros_chatter", Callback);
    }

    void Callback(StringMsg msg)
    {
        Debug.Log($"Received from ROS: {msg.data}");
    }
}
```

```bash
# ROS에서 발행
rostopic pub /ros_chatter std_msgs/String "data: 'Hello from ROS!'"
```

#### 4.3 실습: 양방향 통신 테스트 (0.5시간)

Unity 씬에서 큐브를 키보드로 움직이면 ROS에 위치(Twist) 발행, ROS에서 명령을 받아 큐브 색상 변경:

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Geometry;

public class CubeController : MonoBehaviour
{
    private ROSConnection ros;
    public string twistTopic = "/cube_cmd_vel";
    private Renderer cubeRenderer;
    private Vector3 targetColor = Color.white;

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.RegisterPublisher<TwistMsg>(twistTopic);
        ros.Subscribe<ColorMsg>("/cube_color", UpdateColor);
        cubeRenderer = GetComponent<Renderer>();
    }

    void UpdateColor(ColorMsg msg)
    {
        targetColor = new Color(msg.r, msg.g, msg.b, 1f);
    }

    void FixedUpdate()
    {
        // 큐브를 ROS로 제어
        float h = Input.GetAxis("Horizontal");
        float v = Input.GetAxis("Vertical");

        if (Mathf.Abs(h) > 0.1f || Mathf.Abs(v) > 0.1f)
        {
            TwistMsg twist = new TwistMsg(
                new Vector3Msg(v * 0.5f, 0, 0),
                new Vector3Msg(0, h * 0.5f, 0)
            );
            ros.Publish(twistTopic, twist);
        }

        // 큐브 색상 부드럽게 전환
        cubeRenderer.material.color = Vector4.Lerp(
            cubeRenderer.material.color, targetColor, Time.deltaTime * 2f
        );
    }
}
```

#### 4.4 ROS 메시지 타입과 Unity 매핑

| ROS 메시지 타입 | Unity C# 클래스 | 용도 |
|---|---|---|
| `std_msgs/String` | `StringMsg` | 문자열 데이터 |
| `geometry_msgs/Twist` | `TwistMsg` | 선속도/각속도 |
| `geometry_msgs/Pose` | `PoseMsg` | 위치/방향 |
| `sensor_msgs/Image` | `ImageMsg` | 이미지 데이터 |
| `sensor_msgs/LaserScan` | `LaserScanMsg` | 2D LiDAR 스캔 |
| `sensor_msgs/PointCloud2` | `PointCloud2Msg` | 3D 포인트 클라우드 |
| `nav_msgs/Odometry` | `OdometryMsg` | 주행 거리 측정 |

#### 4.5 과제
1. Unity에서 ROS로 `Int32Msg`를 발행하는 카운터 스크립트 작성 (1초에 1씩 증가)
2. ROS에서 `std_msgs/ColorRGBA`를 받아 Unity 오브젝트 색상을 변경하는 시스템 구현
3. mesh geometry_msgs/Twist를 Unity 오브젝트의 Rigidbody에 적용하는 브리지 스크립트 작성
4. **심화**: Unity ↔ ROS 왕복 지연 시간(RTT) 측정 스크립트 작성

---

## 5주차: URDF 임포트 및 로봇 모델링

### 학습 목표
- URDF 포맷 이해
- URDF Importer를 사용한 로봇 모델 임포트
- ArticulationBody 체인 이해
- 로봇 모델 시각화 및 기본 조작

### 세부 내용

#### 5.1 URDF (Unified Robot Description Format) (1시간)

URDF는 로봇을 XML로 기술하는 포맷입니다:

```xml
<?xml version="1.0"?>
<robot name="simple_arm">

  <!-- 링크: 로봇의 강체 부위 -->
  <link name="base_link">
    <visual>
      <geometry>
        <box size="0.2 0.2 0.1"/>
      </geometry>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <material name="blue">
        <color rgba="0 0 0.8 1"/>
      </material>
    </visual>
    <collision>
      <geometry>
        <box size="0.2 0.2 0.1"/>
      </geometry>
    </collision>
    <inertial>
      <mass value="1.0"/>
      <inertia ixx="0.01" ixy="0" ixz="0"
               iyy="0.01" iyz="0" izz="0.01"/>
    </inertial>
  </link>

  <!-- 조인트: 링크 간 연결 관계와 운동 자유도 -->
  <joint name="joint1" type="revolute">
    <parent link="base_link"/>
    <child link="arm_link"/>
    <origin xyz="0 0 0.05" rpy="0 0 0"/>
    <axis xyz="0 0 1"/>
    <limit lower="-3.14" upper="3.14" effort="1.0" velocity="1.0"/>
  </joint>

  <link name="arm_link">
    <visual>
      <geometry>
        <box size="0.05 0.05 0.3"/>
      </geometry>
      <origin xyz="0 0 0.15" rpy="0 0 0"/>
      <material name="red">
        <color rgba="0.8 0 0 1"/>
      </material>
    </visual>
    <collision>
      <geometry>
        <box size="0.05 0.05 0.3"/>
      </geometry>
    </collision>
    <inertial>
      <mass value="0.5"/>
      <inertia ixx="0.005" ixy="0" ixz="0"
               iyy="0.005" iyz="0" izz="0.001"/>
    </inertial>
  </link>

</robot>
```

**핵심 요소**:

| 요소 | 설명 |
|---|---|
| `<link>` | 로봇의 각 파트 (질량, 관성, 시각/충돌 형상) |
| `<joint>` | 링크 간 연결 (타입: revolute, prismatic, fixed, continuous 등) |
| `<visual>` | 렌더링용 3D 형상 |
| `<collision>` | 충돌 감지용 형상 (단순화 권장) |
| `<inertial>` | 물리 시뮬레이션용 질량/관성 텐서 |

**조인트 타입**:

| 타입 | 자유도 | 설명 |
|---|---|---|
| `fixed` | 0 | 고정 |
| `revolute` | 1 (회전) | 제한된 회전 (힌지) |
| `continuous` | 1 (회전) | 무제한 회전 (바퀴) |
| `prismatic` | 1 (직선) | 직선 운동 (슬라이더) |
| `planar` | 2 (평면) | 평면 운동 |
| `floating` | 6 | 완전 자유 (6-DOF) |

#### 5.2 실습: URDF Importer로 로봇 가져오기 (1시간)

**Step 1: URDF 파일 준비**
```bash
# Niryo One URDF 다운로드 (Unity Robotics Hub 샘플)
cp -r Unity-Robotics-Hub/tutorials/pick_and_place/ROS/src/niryo_one_urdf ~/ros_ws/src/
```

**Step 2: Unity에서 URDF 임포트**
1. `Robot > Import Robot from URDF` 메뉴 클릭
2. URDF 파일 선택
3. 임포트 설정:
   - **Axis Type**: Standard (Y-up) 또는 ROS(Gravity)
   - **Convex Decomposition**: ✅ (충돌 메시 자동 최적화)
   - **Import Inertia**: ✅ (URDF 관성 데이터 사용)

**Step 3: 임포트 결과 확인**
- Hierarchy에 로봇 게임오브젝트 트리 구조 확인
- 각 링크에 `ArticulationBody` 컴포넌트 자동 할당
- 조인트 제한, 드라이브 파라미터 자동 설정

#### 5.3 ArticulationBody 이해 (0.5시간)

`ArticulationBody`는 Unity에서 로봇 체인을 구현하는 핵심 컴포넌트입니다.

| 속성 | 설명 | 로봇 예시 |
|---|---|---|
| `Immutable` | 체인 내 고정 | 로봇 베이스 |
| `Revolute` | 1축 회전 | 팔 관절 |
| `Prismatic` | 1축 직선 | 그리퍼 |
| `Spherical` | 3축 회전 | 볼 조인트 |
| `Stiffness` | 위치 제어 강성 | 관절 위치 유지 |
| `Damping` | 속도 저항 | 진동 억제 |
| `ForceLimit` | 최대 토크 | 안전 제한 |
| `Target` | 목표 위치 | 모션 플래닝 결과 |

```c#
// ArticulationBody에 직접 명령 내리기
using UnityEngine;

public class JointController : MonoBehaviour
{
    private ArticulationBody[] joints;

    void Start()
    {
        joints = GetComponentsInChildren<ArticulationBody>();
    }

    public void SetJointPosition(int jointIndex, float targetPosition)
    {
        if (jointIndex < 0 || jointIndex >= joints.Length) return;

        var joint = joints[jointIndex];
        var drive = joint.xDrive;
        drive.target = targetPosition;
        joint.xDrive = drive;
    }

    public float GetJointPosition(int jointIndex)
    {
        if (jointIndex < 0 || jointIndex >= joints.Length) return 0f;
        return joints[jointIndex].jointPosition[0];
    }
}
```

#### 5.4 실습: 임포트한 로봇 팔 움직여보기 (0.5시간)

```c#
using UnityEngine;

public class SimpleArmController : MonoBehaviour
{
    public float speed = 30f;
    private ArticulationBody[] joints;
    private float[] targetPositions;

    void Start()
    {
        joints = GetComponentsInChildren<ArticulationBody>();
        targetPositions = new float[joints.Length];
    }

    void Update()
    {
        // 키보드로 각 관절 제어
        // 1번 관절: Q/E
        if (joints.Length > 0) UpdateJoint(0, KeyCode.Q, KeyCode.E);
        // 2번 관절: A/D
        if (joints.Length > 1) UpdateJoint(1, KeyCode.A, KeyCode.D);
        // 3번 관절: Z/X
        if (joints.Length > 2) UpdateJoint(2, KeyCode.Z, KeyCode.X);
    }

    void UpdateJoint(int index, KeyCode negative, KeyCode positive)
    {
        var joint = joints[index];
        var drive = joint.xDrive;

        if (Input.GetKey(negative))
            targetPositions[index] -= speed * Time.deltaTime;
        if (Input.GetKey(positive))
            targetPositions[index] += speed * Time.deltaTime;

        // 조인트 제한 적용
        targetPositions[index] = Mathf.Clamp(
            targetPositions[index],
            (float)joint.twistLock.lowerLimit,
            (float)joint.twistLock.upperLimit
        );

        drive.target = targetPositions[index];
        joint.xDrive = drive;
    }
}
```

#### 5.5 과제
1. URDF로 2-DOF 로봇 팔 직접 설계하고 Unity에 임포트
2. Niryo One 또는 TurtleBot3 URDF를 Unity에 임포트하고 각 관절 움직임 확인
3. 임포트한 로봇의 관절 각도를 ROS `/joint_states` 토픽으로 발행하는 스크립트 작성
4. **심화**: URDF에 포함된 `<transmission>` 태그의 역할 조사 및 리포트

---

## 6주차: 센서 시뮬레이션

### 학습 목표
- Unity Simulation Sensors 패키지 이해
- RGB-D 카메라, LiDAR, IMU 센서 구성
- 센서 데이터를 ROS로 스트리밍
- 센서 노이즈 모델링

### 세부 내용

#### 6.1 센서 시뮬레이션 개요 (0.5시간)
- 시뮬레이션에서 센서의 역할
- 실제 센서와 가상 센서의 차이
- Unity 센서 패키지 아키텍처

```
Unity Sensor Architecture:

Sensor Prefab
  ├── Sensor Component (데이터 수집 로직)
  ├── Visualization (데이터 시각화)
  └── Publisher Node (ROS 메시지 발행)
```

**지원 센서 목록**:

| 센서 | 출력 데이터 | ROS 메시지 타입 |
|---|---|---|
| RGB Camera | Color Image | `sensor_msgs/Image` |
| Depth Camera | Depth Map | `sensor_msgs/Image` |
| Stereo Depth | Stereo Image Pair | `sensor_msgs/Image[]` |
| Fisheye Camera | Wide-angle Image | `sensor_msgs/Image` |
| LiDAR (RayTraced) | Point Cloud | `sensor_msgs/PointCloud2` |
| LiDAR (Physics) | LaserScan / PointCloud | `sensor_msgs/LaserScan` |
| LiDAR (Raster) | Point Cloud | `sensor_msgs/PointCloud2` |
| IMU | Accel + Gyro + Orientation | `sensor_msgs/Imu` |
| Joint State | 관절 위치/속도/토크 | `sensor_msgs/JointState` |
| Time-of-Flight | 거리 Point Cloud | `sensor_msgs/PointCloud2` |

#### 6.2 실습: RGB-D 카메라 설치 (1시간)

**Step 1: 센서 패키지 설치**
```
Window > Package Manager > + (Add package from git URL)
https://github.com/Unity-Technologies/ROS-TCP-Connector.git?path=/com.unity.robotics.ros-tcp-connector
// 센서는 com.unity.simulation.sensors (Unity 2021.3+ Package Manager에서 검색)
```

**Step 2: 카메라 센서 설정**

카메라 센서 프리팹을 씬에 배치하고 속성 설정:

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Sensor;
using Unity.Simulation.Sensors;

public class CameraSensorBridge : MonoBehaviour
{
    private ROSConnection ros;
    public string imageTopic = "/unity/camera/rgb";
    public string depthTopic = "/unity/camera/depth";

    // 실제로는 Sensor 컴포넌트가 자동으로 ROS 메시지를 publish
    // 여기서는 수동 브리지 예시

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.RegisterPublisher<ImageMsg>(imageTopic);
    }

    // 센서 데이터는 Sensor 컴포넌트 설정에서 ROS 연결로 직접 publish 가능
}
```

**센서 설정 파라미터**:

| 파라미터 | 권장값 | 설명 |
|---|---|---|
| Resolution | 640x480 | 해상도 (높을수록 정확 but 느림) |
| FOV | 60°-90° | 시야각 |
| Update Rate | 10-30 Hz | 업데이트 주파수 |
| Noise | Gaussian(mean=0, std=0.01) | 센서 노이즈 |
| Depth Range | 0.3 - 10.0m | 측정 가능 거리 |

#### 6.3 실습: LiDAR 센서 구성 (1시간)

**RayTraced LiDAR 설정**:

```c#
// LiDAR 파라미터를 C#에서 동적 설정
using UnityEngine;
using Unity.Simulation.Sensors;

public class LidarConfig : MonoBehaviour
{
    public Sensor lidarSensor;

    void Start()
    {
        // LiDAR 속성 설정 (컴포넌트에 따라 실제 API는 다를 수 있음)
        // 실제로는 Inspector에서 직접 설정하거나,
        // URDF SDF 태그로 자동 설정됨
        Debug.Log($"LiDAR sensor initialized on {gameObject.name}");
    }

    void OnDrawGizmos()
    {
        // LiDAR 시야각 시각화
        Gizmos.color = Color.green;
        Gizmos.DrawWireSphere(transform.position, 1f);
    }
}
```

**LiDAR 파라미터 테이블**:

| 파라미터 | RayTraced | Physics | Raster |
|---|---|---|---|
| 정확도 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| 성능 | 중간 | 빠름 | 빠름 |
| 범위 | 무제한 | 물리 Ray 제한 | 렌더링 기반 |
| ROS 타입 | PointCloud2 | LaserScan/PointCloud2 | PointCloud2 |

#### 6.4 실습: IMU 센서 및 데이터 시각화 (0.5시간)

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Sensor;

public class ImuPublisher : MonoBehaviour
{
    private ROSConnection ros;
    public string imuTopic = "/imu/data";
    public float updateRate = 100f; // Hz
    private float lastPublishTime;

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.RegisterPublisher<ImuMsg>(imuTopic);
    }

    void FixedUpdate()
    {
        if (Time.time - lastPublishTime < 1f / updateRate) return;
        lastPublishTime = Time.time;

        // Rigidbody로부터 실제 물리 데이터 읽기
        Rigidbody rb = GetComponent<Rigidbody>();
        if (rb == null) return;

        ImuMsg imuMsg = new ImuMsg
        {
            header = new RosMessageTypes.Std.HeaderMsg
            {
                frame_id = "imu_link",
                stamp = RosMessageTypes.BuiltinInterfaces.TimeMsg.Now()
            },
            orientation = new RosMessageTypes.Geometry.QuaternionMsg(
                transform.rotation.x,
                transform.rotation.y,
                transform.rotation.z,
                transform.rotation.w
            ),
            angular_velocity = new RosMessageTypes.Geometry.Vector3Msg(
                rb.angularVelocity.x,
                rb.angularVelocity.y,
                rb.angularVelocity.z
            ),
            linear_acceleration = new RosMessageTypes.Geometry.Vector3Msg(
                rb.acceleration.x,
                rb.acceleration.y,
                rb.acceleration.z
            )
        };

        ros.Publish(imuTopic, imuMsg);
    }
}
```

#### 6.5 센서 노이즈 모델링 (0.5시간)

실제 센서 동작을 모방하기 위한 노이즈 파라미터:

```c#
[System.Serializable]
public class NoiseParameters
{
    public float mean = 0f;
    public float stdDev = 0.01f;

    public float Apply()
    {
        return GaussianRandom(mean, stdDev);
    }

    private static float GaussianRandom(float mean, float stdDev)
    {
        float u1 = Random.value;
        float u2 = Random.value;
        float normal = Mathf.Sqrt(-2f * Mathf.Log(u1)) * Mathf.Cos(2f * Mathf.PI * u2);
        return mean + stdDev * normal;
    }
}

// 노이즈가 적용된 센서 데이터 예시
public class NoisyLidarPoint
{
    public NoiseParameters rangeNoise = new NoiseParameters { mean = 0, stdDev = 0.02f };
    public NoiseParameters angleNoise = new NoiseParameters { mean = 0, stdDev = 0.005f };
    public float dropOutRate = 0.01f; // 1% dropout

    public Vector3 ApplyNoise(Vector3 hitPoint, Vector3 origin)
    {
        // 드롭아웃 (물체가 감지되지 않음)
        if (Random.value < dropOutRate) return Vector3.positiveInfinity;

        Vector3 direction = (hitPoint - origin).normalized;
        float range = Vector3.Distance(origin, hitPoint);

        // 거리 노이즈
        range += rangeNoise.Apply();

        // 각도 노이즈 (빔 방향에 작은 섭동)
        Quaternion angleNoiseRot = Quaternion.Euler(
            angleNoise.Apply() * Mathf.Rad2Deg,
            angleNoise.Apply() * Mathf.Rad2Deg,
            0
        );
        direction = angleNoiseRot * direction;

        return origin + direction * range;
    }
}
```

#### 6.6 과제
1. RGB 카메라를 로봇 팔 엔드 이펙터에 부착하고, ROS에서 이미지 토픽 구독 확인
2. Physics LiDAR를 로봇 베이스에 장착하고 2D LaserScan 발행
3. 다양한 조명 조건에서 카메라 이미지 차이 비교 (Directional Light 각도 변경)
4. **심화**: 멀티 센서 퓨전 시뮬레이션 - 카메라 + LiDAR + IMU 데이터를 동시에 ROS로 스트리밍

---

## 7주차: ArticulationBody와 로봇 제어 기초

### 학습 목표
- ArticulationBody 드라이브 속성 이해
- 위치 제어(Position Control)와 속도 제어(Velocity Control)
- PID 제어 개념
- ROS로부터 조인트 명령 수신 및 실행

### 세부 내용

#### 7.1 ArticulationDrive 상세 (1시간)

**드라이브 모드**:

| 모드 | stiffness | damping | 사용 예 |
|---|---|---|---|
| **Position Control** | > 0 | = 0 | 정확한 위치 유지 |
| **Velocity Control** | = 0 | > 0 | 일정 속도 회전 |
| **Impedance Control** | > 0 | > 0 | 힘 제어 (순응 운동) |

```c#
// 각 모드별 설정 예시
using UnityEngine;

public class DriveModes : MonoBehaviour
{
    private ArticulationBody joint;

    void Start()
    {
        joint = GetComponent<ArticulationBody>();
    }

    // 위치 제어: 목표 각도로 이동하여 유지
    public void SetPositionMode(float targetAngle)
    {
        var drive = joint.xDrive;
        drive.stiffness = 1000f;    // 높은 강성
        drive.damping = 0f;         // 댐핑 없음
        drive.target = targetAngle;
        drive.forceLimit = 100f;
        joint.xDrive = drive;
    }

    // 속도 제어: 일정 속도로 계속 회전
    public void SetVelocityMode(float targetVelocity)
    {
        var drive = joint.xDrive;
        drive.stiffness = 0f;       // 강성 없음
        drive.damping = 10f;        // 속도 추종
        drive.targetVelocity = targetVelocity;
        drive.forceLimit = 50f;
        joint.xDrive = drive;
    }

    // 임피던스 제어: 목표 위치 + 속도 저항
    public void SetImpedanceMode(float targetAngle)
    {
        var drive = joint.xDrive;
        drive.stiffness = 500f;     // 중간 강성
        drive.damping = 50f;        // 속도 저항 (진동 억제)
        drive.target = targetAngle;
        joint.xDrive = drive;
    }
}
```

#### 7.2 PID 제어 기초 (1시간)

```c#
using UnityEngine;

[System.Serializable]
public class PIDController
{
    public float Kp = 10f;    // 비례 gain
    public float Ki = 0.1f;    // 적분 gain
    public float Kd = 1f;      // 미분 gain

    private float integral = 0f;
    private float lastError = 0f;

    public float Compute(float target, float current, float dt)
    {
        float error = target - current;

        // 적분항 (windup 방지)
        integral += error * dt;
        integral = Mathf.Clamp(integral, -100f, 100f);

        // 미분항
        float derivative = (error - lastError) / Mathf.Max(dt, 0.001f);
        lastError = error;

        // PID 출력
        return Kp * error + Ki * integral + Kd * derivative;
    }

    public void Reset()
    {
        integral = 0f;
        lastError = 0f;
    }
}
```

#### 7.3 실습: ROS → Unity 조인트 명령 (0.5시간)

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Sensor;

public class JointStateSubscriber : MonoBehaviour
{
    private ROSConnection ros;
    public string jointCommandTopic = "/joint_group_command";
    private ArticulationBody[] joints;

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        joints = GetComponentsInChildren<ArticulationBody>();

        ros.Subscribe<JointStateMsg>(jointCommandTopic, OnJointCommand);
    }

    void OnJointCommand(JointStateMsg msg)
    {
        if (msg.position.Length != joints.Length)
        {
            Debug.LogWarning($"Joint count mismatch: ROS={msg.position.Length}, Unity={joints.Length}");
            return;
        }

        for (int i = 0; i < joints.Length; i++)
        {
            var drive = joints[i].xDrive;
            drive.target = (float)(msg.position[i] * Mathf.Rad2Deg);
            joints[i].xDrive = drive;
        }
    }
}
```

ROS 측 발행 코드:
```python
#!/usr/bin/env python3
import rospy
from sensor_msgs.msg import JointState
from std_msgs.msg import Header
import math

def send_joint_commands():
    pub = rospy.Publisher('/joint_group_command', JointState, queue_size=10)
    rospy.init_node('joint_command_sender')
    rate = rospy.Rate(10)  # 10 Hz

    t = 0.0
    while not rospy.is_shutdown():
        msg = JointState()
        msg.header = Header()
        msg.header.stamp = rospy.Time.now()
        msg.name = ['joint1', 'joint2', 'joint3']
        msg.position = [
            0.5 * math.sin(t),
            0.3 * math.cos(t * 0.7),
            0.2 * math.sin(t * 1.3)
        ]
        pub.publish(msg)
        t += 0.1
        rate.sleep()

if __name__ == '__main__':
    try:
        send_joint_commands()
    except rospy.ROSInterruptException:
        pass
```

#### 7.4 실습: 모바일 로봇 베이스 제어 (0.5시간)

```c#
// TurtleBot3 스타일 모바일 베이스
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Geometry;

public class MobileBaseController : MonoBehaviour
{
    private ROSConnection ros;
    public string cmdVelTopic = "/cmd_vel";
    public float maxLinearSpeed = 0.5f;
    public float maxAngularSpeed = 1.0f;
    public float acceleration = 2.0f;

    private Vector3 targetVelocity = Vector3.zero;
    private Rigidbody rb;

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.Subscribe<TwistMsg>(cmdVelTopic, OnCmdVel);
        rb = GetComponent<Rigidbody>();
    }

    void OnCmdVel(TwistMsg msg)
    {
        targetVelocity = new Vector3(
            (float)msg.linear.x,
            0,
            (float)msg.linear.y  // ROS 좌표계 → Unity 변환
        );
        // 각속도는 Y축 회전으로 매핑
    }

    void FixedUpdate()
    {
        // 가속도 제한 적용
        Vector3 currentVel = rb.velocity;
        Vector3 desiredVel = transform.forward * targetVelocity.z * maxLinearSpeed;
        rb.velocity = Vector3.MoveTowards(currentVel, desiredVel, acceleration * Time.fixedDeltaTime);
    }
}
```

#### 7.5 과제
1. PID 파라미터(Kp, Ki, Kd)를 바꿔가며 관절 응답 특성 관찰 및 리포트 작성
2. ROS `/cmd_vel`을 받아 Unity TurtleBot3가 움직이는 시스템 완성
3. ROS `/joint_states`를 Unity에서 발행하여 RViz에서 실시간 시각화
4. **심화**: 조인트 위치 제어 시 overshoot 최소화를 위한 feedforward 항 구현

---

## 8주차: 중간 프로젝트

### 프로젝트 설명
지금까지 배운 내용을 종합하여 **"ROS로 제어되는 로봇 팔 시뮬레이터"** 구현

### 요구사항

| 항목 | 세부 내용 | 점수 |
|---|---|---|
| **Unity 씬** | 로봇 팔 + 작업 테이블 + 조작 대상 물체 | 15% |
| **URDF 임포트** | 최소 4-DOF 로봇 팔 (Niryo One, UR5, 또는 직접 제작) | 15% |
| **ROS 연결** | ROS ↔ Unity TCP 통신 (양방향) | 15% |
| **조인트 제어** | ROS 메시지로 각 관절 위치 명령 | 15% |
| **엔드 이펙터** | 그리퍼 열고 닫힘 구현 | 10% |
| **카메라 센서** | 엔드 이펙터 부착 RGB 카메라 → ROS 이미지 스트리밍 | 10% |
| **문서화** | README (설치법, 실행법, 아키텍처) | 10% |
| **발표** | 5분 시연 + 3분 Q&A | 10% |

### 제출 형식

```
team_XX_midterm/
├── UnityProject/
│   └── (Unity 프로젝트 파일)
├── ROS/
│   └── (ROS 패키지)
├── README.md
├── architecture.png (선택)
└── demo_video.mp4 (선택)
```

### 평가 기준

| 평가 항목 | 배점 |
|---|---|
| 기능 완성도 (모든 요구사항 충족) | 40% |
| 코드 품질 (주석, 네이밍, 구조화) | 20% |
| ROS 통신 안정성 (지연/끊김 없음) | 15% |
| 시각적 완성도 (조명, 재질, 환경) | 10% |
| 발표 및 시연 | 15% |

### 일정
- **7주차**: 프로젝트 설명 및 팀 구성 (2-3인)
- **8주차 전반**: 구현 및 테스트
- **8주차 후반**: 발표 및 제출

---

## 9주차: MoveIt 기반 모션 플래닝

### 학습 목표
- MoveIt 아키텍처 이해
- MoveIt Setup Assistant로 로봇 설정
- ROS → Unity 모션 플래닝 파이프라인
- 충돌 회피 경로 생성

### 세부 내용

#### 9.1 MoveIt 개요 (1시간)

**MoveIt 주요 컴포넌트**:

```
                    ┌─────────────────┐
                    │   MoveIt!       │
                    │  ┌───────────┐  │
  /joint_states ──► │  │ Planning  │  │ ──► /trajectory
                    │  │ Scene     │  │
  /tf ────────────► │  │ Kinematics│  │
                    │  │ Collision │  │
                    │  └───────────┘  │
                    └─────────────────┘
```

| 컴포넌트 | 역할 |
|---|---|
| **Planning Scene** | 환경/장애물 정보 관리 |
| **MoveGroup** | 로봇 그룹(팔, 그리퍼) 인터페이스 |
| **Kinematics** | 순기구학/역기구학 해석 (KDL, IKFast, TRAC-IK) |
| **Collision Checking** | 충돌 검사 (FCL, PBD) |
| **Planner** | 경로 계획 알고리즘 (OMPL, CHOMP, STOMP) |

#### 9.2 실습: MoveIt 설정 (1시간)

**Step 1: MoveIt 패키지 생성**
```bash
cd ~/ros_ws/src
ros2 pkg create --build-type ament_cmake my_robot_moveit_config

# MoveIt Setup Assistant 실행
ros2 launch moveit2_setup_assistant setup_assistant.launch.py
```

**Step 2: URDF 로드 및 설정**
1. Setup Assistant에서 URDF 로드
2. Self-Collision 매트릭스 자동 생성
3. Planning Group 정의 (arm, gripper 등)
4. Robot Pose 설정 (home, vertical 등)
5. End Effector 지정
6. ROS 2 Controllers 설정
7. 설정 파일 생성 (SRDF, config)

**Step 3: 생성된 설정 파일 구조**
```
my_robot_moveit_config/
├── config/
│   ├── ompl_planning.yaml       # OMPL 플래너 설정
│   ├── kinematics.yaml          # IK 솔버 설정
│   ├── joint_limits.yaml        # 조인트 제한
│   ├── moveit_controllers.yaml  # 컨트롤러 설정
│   └── srdf/
│       └── my_robot.srdf        # 로봇 의미론적 설명
└── launch/
    ├── move_group.launch.py
    └── demo.launch.py
```

#### 9.3 실습: 모션 플래닝 요청 및 Unity로 전송 (1시간)

**Python으로 모션 플래닝**:
```python
#!/usr/bin/env python3
import rospy
import sys
import moveit_commander
import geometry_msgs.msg
from trajectory_msgs.msg import JointTrajectory, JointTrajectoryPoint

def plan_to_pose():
    moveit_commander.roscpp_initialize(sys.argv)
    rospy.init_node('moveit_planner', anonymous=True)

    # MoveGroup 초기화
    robot = moveit_commander.RobotCommander()
    scene = moveit_commander.PlanningSceneInterface()
    group = moveit_commander.MoveGroupCommander("arm")
    group.set_planning_time(5.0)

    # 목표 Pose 설정
    target_pose = geometry_msgs.msg.Pose()
    target_pose.position.x = 0.3
    target_pose.position.y = 0.0
    target_pose.position.z = 0.2
    target_pose.orientation.w = 1.0
    group.set_pose_target(target_pose)

    # 모션 플래닝 실행
    plan = group.plan()

    if plan:
        rospy.loginfo("Plan found! Publishing trajectory...")
        pub = rospy.Publisher('/planned_trajectory', JointTrajectory, queue_size=10)

        # Unity가 구독할 수 있도록 trajectory 발행
        trajectory_msg = plan.joint_trajectory  # 실제 API에 따라 조정
        pub.publish(trajectory_msg)
    else:
        rospy.logwarn("No plan found!")

    moveit_commander.roscpp_shutdown()

if __name__ == '__main__':
    plan_to_pose()
```

**Unity에서 Trajectory 수신 및 실행**:
```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Trajectory;
using Unity.Robotics.UrdfImporter.Control;

public class TrajectoryExecutor : MonoBehaviour
{
    private ROSConnection ros;
    public string trajectoryTopic = "/planned_trajectory";
    private ArticulationBody[] joints;

    private JointTrajectoryMsg currentTrajectory;
    private int currentPointIndex = 0;
    private float timer = 0f;

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        joints = GetComponentsInChildren<ArticulationBody>();
        ros.Subscribe<JointTrajectoryMsg>(trajectoryTopic, OnTrajectory);
    }

    void OnTrajectory(JointTrajectoryMsg msg)
    {
        currentTrajectory = msg;
        currentPointIndex = 0;
        timer = 0f;
        Debug.Log($"Received trajectory with {msg.points.Length} waypoints");
    }

    void FixedUpdate()
    {
        if (currentTrajectory == null || currentPointIndex >= currentTrajectory.points.Length)
            return;

        var point = currentTrajectory.points[currentPointIndex];

        // 각 조인트 위치 설정
        for (int i = 0; i < Mathf.Min(joints.Length, point.positions.Length); i++)
        {
            var drive = joints[i].xDrive;
            drive.target = (float)(point.positions[i] * Mathf.Rad2Deg);
            joints[i].xDrive = drive;
        }

        timer += Time.fixedDeltaTime;
        float duration = (float)point.time_from_start.sec + (float)point.time_from_start.nanosec * 1e-9f;

        if (timer >= duration)
        {
            timer = 0f;
            currentPointIndex++;
        }
    }
}
```

#### 9.4 충돌 회피 (0.5시간)

MoveIt의 충돌 검사는 Planning Scene에 추가된 객체와 로봇 간 충돌을 자동으로 회피합니다:

```python
def add_collision_object(scene):
    from moveit_msgs.msg import CollisionObject
    from shape_msgs.msg import SolidPrimitive

    # 장애물 (테이블) 추가
    table = CollisionObject()
    table.header.frame_id = "base_link"
    table.id = "table"

    table_shape = SolidPrimitive()
    table_shape.type = SolidPrimitive.BOX
    table_shape.dimensions = [0.8, 0.5, 0.05]

    table_pose = geometry_msgs.msg.Pose()
    table_pose.position.x = 0.4
    table_pose.position.y = 0.0
    table_pose.position.z = -0.025

    table.primitives = [table_shape]
    table.primitive_poses = [table_pose]
    table.operation = CollisionObject.ADD

    scene.add_object(table)

    # 충돌 회피 플래닝
    group.set_pose_target(above_table_pose)
    plan = group.plan()  # 자동으로 테이블 충돌 회피
```

이제 이 충돌 정보를 Unity로 전송하여 시각화할 수 있습니다.

**Unity에서 충돌 객체 동기화**:
```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Moveit;

public class CollisionSceneSync : MonoBehaviour
{
    private ROSConnection ros;
    public string planningSceneTopic = "/planning_scene";

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.Subscribe<PlanningSceneMsg>(planningSceneTopic, OnPlanningScene);
    }

    void OnPlanningScene(PlanningSceneMsg msg)
    {
        // Planning Scene 정보로 Unity 씬 업데이트
        // 충돌 객체 생성/위치 업데이트
        Debug.Log($"Planning scene updated with {msg.world.collision_objects.Length} objects");
    }
}
```

#### 9.5 과제
1. URDF로 6-DOF 로봇 팔 MoveIt 설정 완료하기
2. 3개 이상의 목표 지점에 대해 모션 플래닝 실행 및 경로 시각화
3. 계획된 Trajectory를 Unity에서 재생하여 시뮬레이션
4. **심화**: 충돌 객체(장애물)가 있는 환경에서 플래닝 성공률 비교 리포트

---

## 10주차: Pick and Place 구현

### 학습 목표
- Pick and Place 파이프라인 전체 구현
- 그리퍼(Gripper) 메커니즘 이해
- 모션 시퀀스 설계
- End-to-End 통합

### 세부 내용

#### 10.1 Pick and Place 개요 (0.5시간)

```
전체 워크플로우:

1. 객체 감지 (카메라) → 2. 접근 위치 계산 → 3. Pre-grasp 포즈로 이동
4. 그리퍼 열기 → 5. Grasp 포즈로 이동 → 6. 그리퍼 닫기
7. Lift → 8. Place 포즈로 이동 → 9. 그리퍼 열기 (놓기) → 10. Retreat
```

#### 10.2 실습: 그리퍼 구현 (1시간)

```c#
using UnityEngine;

public class GripperController : MonoBehaviour
{
    public float gripperSpeed = 30f;
    public float openAngle = 45f;
    public float closeAngle = 0f;

    private ArticulationBody leftFinger;
    private ArticulationBody rightFinger;
    private bool isOpen = true;

    void Start()
    {
        var fingers = GetComponentsInChildren<ArticulationBody>();
        // 일반적으로 첫 번째는 왼쪽, 두 번째는 오른쪽
        if (fingers.Length >= 2)
        {
            leftFinger = fingers[0];
            rightFinger = fingers[1];
        }
    }

    public void OpenGripper()
    {
        if (isOpen) return;
        SetFingerTarget(openAngle, -openAngle);
        isOpen = true;
    }

    public void CloseGripper()
    {
        if (!isOpen) return;
        SetFingerTarget(closeAngle, closeAngle);
        isOpen = false;
    }

    private void SetFingerTarget(float leftTarget, float rightTarget)
    {
        if (leftFinger != null)
        {
            var drive = leftFinger.xDrive;
            drive.target = leftTarget;
            leftFinger.xDrive = drive;
        }
        if (rightFinger != null)
        {
            var drive = rightFinger.xDrive;
            drive.target = rightTarget;
            rightFinger.xDrive = drive;
        }
    }

    // 물체 잡기 (Trigger를 통한 부착)
    private void OnTriggerEnter(Collider other)
    {
        if (!isOpen && other.CompareTag("Pickable"))
        {
            other.transform.SetParent(transform);
            other.GetComponent<Rigidbody>().isKinematic = true;
        }
    }

    public void ReleaseObject()
    {
        if (transform.childCount > 0)
        {
            var obj = transform.GetChild(0);
            obj.SetParent(null);
            var rb = obj.GetComponent<Rigidbody>();
            rb.isKinematic = false;
            rb.velocity = GetComponentInParent<Rigidbody>()?.velocity ?? Vector3.zero;
        }
    }
}
```

#### 10.3 실습: Pick and Place 시퀀스 (1.5시간)

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using System.Collections;

public class PickAndPlaceController : MonoBehaviour
{
    public ArticulationBody[] armJoints;
    public GripperController gripper;

    [Header("Waypoints")]
    public Transform homePose;
    public Transform preGraspPose;
    public Transform graspPose;
    public Transform liftPose;
    public Transform placePose;

    public float moveDuration = 1.0f;
    public float gripperDelay = 0.5f;

    void Start()
    {
        StartCoroutine(PickAndPlaceRoutine());
    }

    IEnumerator PickAndPlaceRoutine()
    {
        while (true) // 계속 반복
        {
            // 1. Home → Pre-grasp
            yield return MoveToPose(preGraspPose);

            // 2. 그리퍼 열기
            gripper.OpenGripper();
            yield return new WaitForSeconds(gripperDelay);

            // 3. Pre-grasp → Grasp
            yield return MoveToPose(graspPose);

            // 4. 그리퍼 닫기
            gripper.CloseGripper();
            yield return new WaitForSeconds(gripperDelay);

            // 5. Grasp → Lift
            yield return MoveToPose(liftPose);

            // 6. Lift → Place
            yield return MoveToPose(placePose);

            // 7. 그리퍼 열기 (객체 놓기)
            gripper.ReleaseObject();
            gripper.OpenGripper();
            yield return new WaitForSeconds(gripperDelay);

            // 8. Place → Home
            yield return MoveToPose(homePose);

            yield return new WaitForSeconds(1.0f);
        }
    }

    IEnumerator MoveToPose(Transform targetPose)
    {
        // 역기구학 (IK) 계산 또는 조인트 각도 보간
        // 여기서는 단순화된 접근: 직접 Transform 보간
        float elapsed = 0f;
        Vector3 startPos = transform.position;
        Quaternion startRot = transform.rotation;

        while (elapsed < moveDuration)
        {
            float t = elapsed / moveDuration;
            t = SmoothStep(t); // 이징 함수
            transform.position = Vector3.Lerp(startPos, targetPose.position, t);
            transform.rotation = Quaternion.Slerp(startRot, targetPose.rotation, t);
            elapsed += Time.deltaTime;
            yield return null;
        }
    }

    float SmoothStep(float t)
    {
        return t * t * (3f - 2f * t); // 가속-감속
    }
}
```

#### 10.4 실습: ROS 서비스로 Pick and Place 호출 (0.5시간)

```c#
// Unity 측 Service Provider
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.UnityRoboticsDemo;

public class PickAndPlaceService : MonoBehaviour
{
    private ROSConnection ros;
    public string serviceName = "/pick_and_place";

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.ImplementService<PickAndPlaceRequest, PickAndPlaceResponse>(serviceName, ExecutePickAndPlace);
    }

    PickAndPlaceResponse ExecutePickAndPlace(PickAndPlaceRequest request)
    {
        Debug.Log($"Pick and place requested: from ({request.source_x}, {request.source_y}) to ({request.target_x}, {request.target_y})");

        // 실제 Pick and Place 실행
        PickAndPlaceController controller = GetComponent<PickAndPlaceController>();

        // 비동기 실행 (서비스는 완료를 기다리지 않고 즉시 응답)
        return new PickAndPlaceResponse
        {
            success = true,
            message = "Pick and place started"
        };
    }
}
```

```python
# ROS 클라이언트
#!/usr/bin/env python3
import rospy
from unity_robotics_demo_msgs.srv import PickAndPlace, PickAndPlaceRequest

rospy.init_node('pick_and_place_client')
rospy.wait_for_service('/pick_and_place')
client = rospy.ServiceProxy('/pick_and_place', PickAndPlace)

req = PickAndPlaceRequest()
req.source_x = 0.3
req.source_y = 0.1
req.target_x = -0.2
req.target_y = 0.3

resp = client(req)
rospy.loginfo(f"Result: {resp.message}")
```

#### 10.5 과제
1. Niryo One 또는 UR5로 Pick and Place 전체 사이클 구현
2. 그리퍼가 실제로 물체를 잡고 이동하는 시뮬레이션 완성
3. ROS 서비스로 Pick and Place 트리거 구현
4. **심화**: 그리퍼 힘/토크 센서 데이터를 ROS로 발행 (Force-Torque Sensor API 활용)
5. **심화**: 중간 프로젝트를 Pick and Place로 확장

---

## 11주차: 합성 데이터 생성

### 학습 목표
- 합성 데이터(Synthetic Data) 개념 이해
- 도메인 랜덤화(Domain Randomization) 기법
- Unity에서 합성 데이터 생성 파이프라인 구축
- 데이터셋 저장 및 관리

### 세부 내용

#### 11.1 합성 데이터 개요 (0.5시간)

| 구분 | 실제 데이터 | 합성 데이터 |
|---|---|---|
| 수집 비용 | 높음 (로봇, 센서, 노동) | 낮음 (GPU 시간) |
| 레이블 정확도 | 수동 작업 (오류 가능) | 자동 (완벽한 정답) |
| 다양성 | 제한적 | 무제한 (랜덤화) |
| 프라이버시 | 이슈 가능 | 문제 없음 |
| 규모 | 수천-수만 장 | 수백만 장 가능 |

**도메인 랜덤화 요소**:

| 요소 | 랜덤화 범위 |
|---|---|
| 조명 | 방향, 강도, 색온도, 그림자 |
| 질감 | 난반사/정반사 계수, 패턴 |
| 카메라 포즈 | 위치 ±0.1m, 회전 ±15° |
| 배경 | 색상, 패턴, 에셋 배치 |
| 물체 포즈 | 위치, 회전, 스케일 |
| 센서 노이즈 | 가우시안, 드롭아웃, 블룸 |

#### 11.2 실습: 도메인 랜덤화 스크립트 (1시간)

```c#
using UnityEngine;
using System.Collections.Generic;

public class DomainRandomizer : MonoBehaviour
{
    [Header("Lighting")]
    public Light[] lights;
    public float lightIntensityMin = 0.5f;
    public float lightIntensityMax = 2.0f;

    [Header("Camera")]
    public Camera simulationCamera;
    public float cameraPositionRange = 0.2f;
    public float cameraRotationRange = 20f;

    [Header("Objects")]
    public GameObject[] randomizeObjects;
    public Material[] randomMaterials;

    [Header("Background")]
    public Color[] backgroundColors;

    void Start()
    {
        RandomizeAll();
    }

    public void RandomizeAll()
    {
        RandomizeLights();
        RandomizeCamera();
        RandomizeObjectMaterials();
        RandomizeBackground();
    }

    void RandomizeLights()
    {
        foreach (Light light in lights)
        {
            light.intensity = Random.Range(lightIntensityMin, lightIntensityMax);
            light.color = Random.ColorHSV(0f, 1f, 0.5f, 1f, 0.5f, 1f);
            light.transform.rotation = Random.rotationUniform;
        }
    }

    void RandomizeCamera()
    {
        if (simulationCamera == null) return;
        Vector3 basePos = simulationCamera.transform.localPosition;
        simulationCamera.transform.localPosition = basePos + Random.insideUnitSphere * cameraPositionRange;
        simulationCamera.transform.localRotation = Quaternion.Euler(
            Random.Range(-cameraRotationRange, cameraRotationRange),
            Random.Range(-cameraRotationRange, cameraRotationRange),
            0
        );
    }

    void RandomizeObjectMaterials()
    {
        if (randomMaterials.Length == 0) return;

        foreach (GameObject obj in randomizeObjects)
        {
            Renderer renderer = obj.GetComponent<Renderer>();
            if (renderer != null)
            {
                renderer.material = randomMaterials[Random.Range(0, randomMaterials.Length)];
            }
        }
    }

    void RandomizeBackground()
    {
        if (backgroundColors.Length == 0 || Camera.main == null) return;
        Camera.main.backgroundColor = backgroundColors[Random.Range(0, backgroundColors.Length)];
    }
}
```

#### 11.3 실습: 합성 데이터 캡처 파이프라인 (1시간)

```c#
using UnityEngine;
using System.Collections;
using System.IO;

public class SyntheticDataCapture : MonoBehaviour
{
    [Header("Capture Settings")]
    public Camera captureCamera;
    public int imageWidth = 640;
    public int imageHeight = 480;
    public int totalSamples = 1000;
    public float captureInterval = 0.1f;

    [Header("Output")]
    public string outputDirectory = "SyntheticData";

    private DomainRandomizer randomizer;
    private int captureCount = 0;

    void Start()
    {
        randomizer = GetComponent<DomainRandomizer>();
        if (randomizer == null)
            randomizer = gameObject.AddComponent<DomainRandomizer>();

        // 출력 디렉토리 생성
        string path = Path.Combine(Application.dataPath, outputDirectory);
        Directory.CreateDirectory(Path.Combine(path, "RGB"));
        Directory.CreateDirectory(Path.Combine(path, "Depth"));
        Directory.CreateDirectory(Path.Combine(path, "Segmentation"));
        Directory.CreateDirectory(Path.Combine(path, "Annotations"));

        StartCoroutine(CaptureRoutine());
    }

    IEnumerator CaptureRoutine()
    {
        RenderTexture rgbRT = new RenderTexture(imageWidth, imageHeight, 24);
        RenderTexture depthRT = new RenderTexture(imageWidth, imageHeight, 24, RenderTextureFormat.RFloat);

        while (captureCount < totalSamples)
        {
            // 도메인 랜덤화
            randomizer.RandomizeAll();

            yield return new WaitForSeconds(captureInterval);

            // RGB 캡처
            captureCamera.targetTexture = rgbRT;
            captureCamera.Render();
            Texture2D rgbImage = RenderTextureToTexture2D(rgbRT);

            // Depth 캡처
            captureCamera.targetTexture = depthRT;
            captureCamera.Render();
            Texture2D depthImage = RenderTextureToTexture2D(depthRT);

            // 저장
            string basePath = Path.Combine(Application.dataPath, outputDirectory);
            File.WriteAllBytes(
                Path.Combine(basePath, "RGB", $"frame_{captureCount:D6}.png"),
                rgbImage.EncodeToPNG()
            );
            File.WriteAllBytes(
                Path.Combine(basePath, "Depth", $"frame_{captureCount:D6}.exr"),
                depthImage.EncodeToEXR()
            );

            // 메타데이터 저장 (JSON)
            SaveMetadata(captureCount);

            captureCount++;
            Debug.Log($"Captured {captureCount}/{totalSamples}");

            yield return null;
        }

        Debug.Log($"Data capture complete! {totalSamples} samples saved to {outputDirectory}");
    }

    Texture2D RenderTextureToTexture2D(RenderTexture rt)
    {
        RenderTexture activeRT = RenderTexture.active;
        RenderTexture.active = rt;

        Texture2D tex = new Texture2D(rt.width, rt.height);
        tex.ReadPixels(new Rect(0, 0, rt.width, rt.height), 0, 0);
        tex.Apply();

        RenderTexture.active = activeRT;
        return tex;
    }

    void SaveMetadata(int index)
    {
        // 카메라 포즈, 객체 위치 등 메타데이터 저장
        string basePath = Path.Combine(Application.dataPath, outputDirectory, "Annotations");
        string json = JsonUtility.ToJson(new CaptureMetadata
        {
            frame = index,
            cameraPosition = captureCamera.transform.position,
            cameraRotation = captureCamera.transform.rotation.eulerAngles,
            timestamp = Time.time
        }, true);
        File.WriteAllText(Path.Combine(basePath, $"frame_{index:D6}.json"), json);
    }

    [System.Serializable]
    struct CaptureMetadata
    {
        public int frame;
        public Vector3 cameraPosition;
        public Vector3 cameraRotation;
        public float timestamp;
    }
}
```

#### 11.4 합성 데이터를 활용한 AI 학습 파이프라인 (0.5시간)

```
Unity 시뮬레이션
    │
    ▼
합성 데이터 생성 (RGB + Depth + Segmentation + Bounding Box)
    │
    ▼
데이터 전처리 (정규화, 증강, 포맷 변환)
    │
    ▼
모델 학습 (TensorFlow / PyTorch)
    │
    ▼
학습된 모델 → ROS 서비스로 배포
    │
    ▼
Unity에서 모델 추론 결과 시각화
```

**COCO 포맷으로 내보내기 예시**:
```python
import json
import os

def convert_to_coco(annotation_dir, output_file):
    """Unity 메타데이터를 COCO JSON 포맷으로 변환"""
    coco = {
        "images": [],
        "annotations": [],
        "categories": [
            {"id": 1, "name": "cube"},
            {"id": 2, "name": "cylinder"},
            {"id": 3, "name": "sphere"}
        ]
    }

    ann_id = 1
    for filename in sorted(os.listdir(annotation_dir)):
        if not filename.endswith('.json'):
            continue

        with open(os.path.join(annotation_dir, filename)) as f:
            meta = json.load(f)

        frame_num = meta['frame']

        coco["images"].append({
            "id": frame_num,
            "file_name": f"frame_{frame_num:06d}.png",
            "width": 640,
            "height": 480
        })

        for obj in meta.get('objects', []):
            coco["annotations"].append({
                "id": ann_id,
                "image_id": frame_num,
                "category_id": obj['category_id'],
                "bbox": obj['bbox'],  # [x, y, w, h]
                "area": obj['bbox'][2] * obj['bbox'][3],
                "iscrowd": 0
            })
            ann_id += 1

    with open(output_file, 'w') as f:
        json.dump(coco, f)
```

#### 11.5 과제
1. 3가지 이상의 객체 (서로 다른 모양/색상)가 있는 환경 구성
2. Domain Randomization을 적용하여 500장의 RGB-D 합성 데이터 생성
3. 생성된 데이터셋으로 물체 감지 모델 학습 (YOLO 또는 간단한 CNN)
4. **심화**: 학습된 모델을 ROS 서비스로 배포하고 Unity에서 실시간 추론 시각화

---

## 12주차: 디지털 트윈 기초

### 학습 목표
- 디지털 트윈(Digital Twin) 개념 이해
- 실제 로봇 ↔ 가상 로봇 동기화
- ROS를 통한 실시간 상태 동기화
- HIL (Hardware-in-the-Loop) 시뮬레이션

### 세부 내용

#### 12.1 디지털 트윈 개념 (1시간)

| 수준 | 설명 | 예시 |
|---|---|---|
| **Digital Model** | 수동 동기화 (설계 단계) | CAD 모델 |
| **Digital Shadow** | 단방향 동기화 (실제 → 가상) | 실시간 모니터링 |
| **Digital Twin** | 양방향 동기화 (실제 ↔ 가상) | 원격 제어 + 시뮬레이션 |

**디지털 트윈의 장점**:
- 위험 없이 알고리즘 테스트
- 생산 중단 없이 레이아웃 최적화
- 예측 유지보수
- 원격 모니터링 및 제어

#### 12.2 실습: 실제 ROS 로봇과 Unity 동기화 (1.5시간)

**Step 1: 로봇 상태 구독 (실제 → Unity)**

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Sensor;
using System.Collections.Generic;

public class DigitalTwinSync : MonoBehaviour
{
    private ROSConnection ros;

    // 실제 로봇 관절 이름 → Unity ArticulationBody 매핑
    public Dictionary<string, ArticulationBody> jointMap = new Dictionary<string, ArticulationBody>();
    public string jointStateTopic = "/robot/joint_states";

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.Subscribe<JointStateMsg>(jointStateTopic, OnJointState);

        // Unity 로봇의 ArticulationBody 매핑 구축
        ArticulationBody[] bodies = GetComponentsInChildren<ArticulationBody>();
        foreach (var body in bodies)
        {
            jointMap[body.name] = body;
        }

        Debug.Log($"Digital twin initialized with {jointMap.Count} joints");
    }

    void OnJointState(JointStateMsg msg)
    {
        for (int i = 0; i < msg.name.Length; i++)
        {
            string jointName = msg.name[i];
            if (jointMap.ContainsKey(jointName))
            {
                var body = jointMap[jointName];
                var drive = body.xDrive;
                drive.target = (float)(msg.position[i] * Mathf.Rad2Deg);
                body.xDrive = drive;
            }
        }
    }
}
```

**Step 2: Unity 상태를 ROS로 발행 (Unity → 실제)**

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using RosMessageTypes.Sensor;

public class UnityStatePublisher : MonoBehaviour
{
    private ROSConnection ros;
    public string odomTopic = "/unity/odometry";
    private Rigidbody rb;

    void Start()
    {
        ros = ROSConnection.GetOrCreateInstance();
        ros.RegisterPublisher<OdometryMsg>(odomTopic);
        rb = GetComponent<Rigidbody>();
    }

    void FixedUpdate()
    {
        // 실제 로봇의 센서 데이터를 Unity 시뮬레이션으로 대체
        OdometryMsg odom = new OdometryMsg
        {
            header = new RosMessageTypes.Std.HeaderMsg
            {
                frame_id = "odom",
                stamp = RosMessageTypes.BuiltinInterfaces.TimeMsg.Now()
            },
            child_frame_id = "base_footprint",
            pose = new RosMessageTypes.Geometry.PoseWithCovarianceMsg
            {
                pose = new RosMessageTypes.Geometry.PoseMsg
                {
                    position = new RosMessageTypes.Geometry.PointMsg(
                        transform.position.x,
                        transform.position.y,
                        transform.position.z
                    ),
                    orientation = new RosMessageTypes.Geometry.QuaternionMsg(
                        transform.rotation.x,
                        transform.rotation.y,
                        transform.rotation.z,
                        transform.rotation.w
                    )
                }
            },
            twist = new RosMessageTypes.Geometry.TwistWithCovarianceMsg
            {
                twist = new RosMessageTypes.Geometry.TwistMsg(
                    new RosMessageTypes.Geometry.Vector3Msg(
                        rb.velocity.x, rb.velocity.y, rb.velocity.z
                    ),
                    new RosMessageTypes.Geometry.Vector3Msg(
                        rb.angularVelocity.x, rb.angularVelocity.y, rb.angularVelocity.z
                    )
                )
            }
        };

        ros.Publish(odomTopic, odom);
    }
}
```

#### 12.3 HIL (Hardware-in-the-Loop) 시뮬레이션 (0.5시간)

```
┌───────────────────┐     ROS (실시간)     ┌───────────────────┐
│   Physical Robot  │ ◄──────────────────► │   Unity Digital   │
│   (또는 MCU 보드)  │                     │     Twin          │
│                   │                     │                   │
│  - Joint angles   │  /joint_states      │  - 3D 시각화      │
│  - IMU data       │  /imu/data          │  - 센서 데이터     │
│  - Encoder values │  /encoders          │  - 환경 시뮬레이션  │
└───────────────────┘                     └───────────────────┘
```

HIL 시나리오 예시:
```c#
using UnityEngine;
using System.Collections.Generic;

public class HardwareInTheLoop : MonoBehaviour
{
    [Header("HIL Configuration")]
    public bool useHardwareEncoder = false;  // 실제 인코더 vs 시뮬레이션
    public float encoderNoiseStd = 0.001f;   // 인코더 노이즈 모델

    // 실제 하드웨어의 지연을 시뮬레이션
    private Queue<(float time, float value)> latencyBuffer = new Queue<(float, float)>();
    public float simulatedLatency = 0.05f; // 50ms 지연

    public float ApplyEncoderNoise(float cleanValue)
    {
        if (!useHardwareEncoder) return cleanValue;

        float noisy = cleanValue + GaussianRandom(0, encoderNoiseStd);
        return ApplyLatency(noisy);
    }

    float ApplyLatency(float value)
    {
        latencyBuffer.Enqueue((Time.time, value));

        while (latencyBuffer.Count > 0 && latencyBuffer.Peek().time < Time.time - simulatedLatency)
        {
            value = latencyBuffer.Dequeue().value;
        }

        return value;
    }

    static float GaussianRandom(float mean, float stdDev)
    {
        float u1 = Random.value;
        float u2 = Random.value;
        return mean + stdDev * Mathf.Sqrt(-2f * Mathf.Log(u1)) * Mathf.Cos(2f * Mathf.PI * u2);
    }
}
```

#### 12.4 실습: 간단한 디지털 트윈 데모 (0.5시간)

1. ROS에서 `turtlesim` 또는 실제 로봇의 `/joint_states`를 녹화 (`rosbag`)
2. Unity에서 기록된 bag 파일 재생하여 로봇 움직임 동기화
3. Unity 환경의 장애물을 ROS Planning Scene으로 전송
4. 양방향 동기화 검증 (Unity에서 로봇 움직이면 ROS에 반영)

#### 12.5 과제
1. 실제 ROS 로봇 (또는 시뮬레이터)의 joint states를 Unity에 반영하는 디지털 셰도우 구현
2. Unity에서 가상 센서 데이터(LiDAR)를 ROS로 발행하여 RViz에서 시각화
3. HIL 개념을 적용한 로봇 제어 루프 지연 분석 리포트
4. **심화**: Unity 디지털 트윈을 ROS 2 액션 서버와 통합

---

## 13주차: 고급 주제

### 학습 목표
- 멀티 로봇 시뮬레이션
- 강화학습(RL)과 Unity 연동 개요
- HRI (Human-Robot Interaction) 시뮬레이션
- Unity ML-Agents 소개

### 세부 내용

#### 13.1 멀티 로봇 시뮬레이션 (1시간)

```c#
using UnityEngine;
using Unity.Robotics.ROSTCPConnector;
using System.Collections.Generic;

public class MultiRobotManager : MonoBehaviour
{
    [System.Serializable]
    public class RobotInstance
    {
        public string robotName;
        public GameObject robotPrefab;
        public Vector3 spawnPosition;
        public int rosPortOffset = 0; // 각 로봇에 다른 ROS 포트

        [HideInInspector] public GameObject instance;
        [HideInInspector] public ROSConnection rosConnection;
    }

    public List<RobotInstance> robots = new List<RobotInstance>();

    void Start()
    {
        foreach (var robot in robots)
        {
            SpawnRobot(robot);
        }
    }

    void SpawnRobot(RobotInstance robot)
    {
        // 로봇 인스턴스 생성
        robot.instance = Instantiate(robot.robotPrefab, robot.spawnPosition, Quaternion.identity);
        robot.instance.name = robot.robotName;

        // 각 로봇에 독립적인 ROS 연결 생성
        robot.rosConnection = robot.instance.AddComponent<ROSConnection>();
        robot.rosConnection.RosIPAddress = "127.0.0.1";
        robot.rosConnection.RosPort = 10000 + robot.rosPortOffset;

        // 토픽에 로봇 이름 프리픽스 추가
        // 예: /robot1/joint_states, /robot2/joint_states
        Debug.Log($"Spawned {robot.robotName} at {robot.spawnPosition} on port {10000 + robot.rosPortOffset}");
    }
}
```

#### 13.2 Unity ML-Agents + Robotics (1시간)

**ML-Agents 개요**:
- Unity 공식 오픈소스 RL 프레임워크
- PyTorch 기반 학습
- 로봇 제어 정책 학습에 활용 가능

```c#
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Sensors;
using Unity.MLAgents.Actuators;

public class RobotArmAgent : Agent
{
    public ArticulationBody[] joints;
    public Transform target;
    public Transform endEffector;
    public GripperController gripper;

    public override void OnEpisodeBegin()
    {
        // 에피소드 시작 시 무작위 초기화
        target.localPosition = new Vector3(
            Random.Range(-0.3f, 0.3f),
            Random.Range(0.1f, 0.4f),
            Random.Range(-0.2f, 0.2f)
        );
    }

    public override void CollectObservations(VectorSensor sensor)
    {
        // 관찰 정보 (Observation Space)
        sensor.AddObservation(endEffector.localPosition);     // 3
        sensor.AddObservation(endEffector.localRotation);     // 4
        sensor.AddObservation(target.localPosition);          // 3
        sensor.AddObservation(joints[0].jointPosition[0]);    // 1
        sensor.AddObservation(joints[1].jointPosition[0]);    // 1
        // 총 12차원
    }

    public override void OnActionReceived(ActionBuffers actions)
    {
        // 행동 (Action Space) - 조인트 제어
        for (int i = 0; i < joints.Length; i++)
        {
            var drive = joints[i].xDrive;
            drive.target += actions.ContinuousActions[i] * 5f;
            joints[i].xDrive = drive;
        }

        // 보상 (Reward)
        float distance = Vector3.Distance(endEffector.position, target.position);
        if (distance < 0.05f)
        {
            SetReward(1.0f);
            EndEpisode();
        }
        else
        {
            AddReward(-0.01f); // 매 스텝 소량 패널티
            AddReward(-distance * 0.1f); // 거리 기반 패널티
        }
    }

    public override void Heuristic(in ActionBuffers actionsOut)
    {
        // 키보드 수동 제어 (테스트용)
        var actions = actionsOut.ContinuousActions;
        actions[0] = Input.GetAxis("Horizontal");
        actions[1] = Input.GetAxis("Vertical");
    }
}
```

**ML-Agents 학습 실행**:
```bash
# RL 학습 명령어
mlagents-learn config/robot_arm_config.yaml --run-id=robot_arm_v1
```

#### 13.3 HRI (Human-Robot Interaction) 시뮬레이션 (0.5시간)

```c#
using UnityEngine;
using UnityEngine.AI;

public class HumanWorkerSimulation : MonoBehaviour
{
    public NavMeshAgent agent;
    public Transform[] waypoints;
    public Transform robotWorkspace;

    public float safeDistance = 1.5f; // 로봇과 안전 거리
    public float waitTimeAtPoint = 3.0f;

    private int currentWaypoint = 0;
    private bool isWaiting = false;
    private Animator animator;

    enum WorkerState
    {
        Walking,
        Waiting,
        AvoidingRobot,
        Observing
    }
    private WorkerState state = WorkerState.Walking;

    void Start()
    {
        animator = GetComponent<Animator>();
        MoveToNextWaypoint();
    }

    void Update()
    {
        float distToRobot = Vector3.Distance(transform.position, robotWorkspace.position);

        if (distToRobot < safeDistance)
        {
            // 로봇과 너무 가까움 - 회피
            state = WorkerState.AvoidingRobot;
            Vector3 avoidDir = (transform.position - robotWorkspace.position).normalized;
            agent.SetDestination(transform.position + avoidDir * 3f);
        }
        else if (agent.remainingDistance < 0.5f && !isWaiting)
        {
            // 웨이포인트 도착 - 대기
            state = WorkerState.Waiting;
            isWaiting = true;
            Invoke(nameof(MoveToNextWaypoint), waitTimeAtPoint);
        }
    }

    void MoveToNextWaypoint()
    {
        currentWaypoint = (currentWaypoint + 1) % waypoints.Length;
        agent.SetDestination(waypoints[currentWaypoint].position);
        isWaiting = false;
        state = WorkerState.Walking;
    }

    void OnDrawGizmos()
    {
        // 안전 거리 시각화
        Gizmos.color = Color.yellow;
        Gizmos.DrawWireSphere(transform.position, safeDistance);
    }
}
```

#### 13.4 추가 고급 주제 (선택, 0.5시간)

| 주제 | 설명 | 난이도 |
|---|---|---|
| **O3DE와 Unity 비교** | Open 3D Engine (Amazon)과 Unity의 로봇 시뮬레이션 비교 | 중급 |
| **Unity Volume Cloud** | 대규모 환경에서의 LiDAR 안개/비 시뮬레이션 | 고급 |
| **Custom Sensor Plugin** | 자체 센서 타입 개발 (초음파, 열화상 등) | 고급 |
| **ROS 2 Nav2 통합** | Unity TurtleBot3 + Nav2 Navigation Stack | 중급 |
| **Federated Simulation** | 여러 Unity 인스턴스 분산 시뮬레이션 | 고급 |

#### 13.5 과제
1. 2대 이상의 로봇이 동일 환경에서 동시에 작동하는 멀티 로봇 시뮬레이션 구현
2. ML-Agents를 사용한 간단한 로봇 팔 도달(task) 학습 (10,000 스텝)
3. 작업자(Agent)가 로봇과 협업하는 HRI 시나리오 설계 및 구현
4. **심화**: 학습된 ML-Agents 정책을 ONNX로 내보내고 ROS에서 추론

---

## 14주차: 기말 프로젝트

### 프로젝트 개요
지금까지 학습한 모든 내용을 종합하여 **Unity Robotics Hub 기반 종합 로봇 시뮬레이션 시스템** 구현

### 주제 예시

| 주제 | 설명 | 추천 난이도 |
|---|---|---|
| **스마트 팩토리 디지털 트윈** | 컨베이어 벨트 + 로봇 팔 Pick and Place + 센서 모니터링 | 중급 |
| **자율 주행 로봇 내비게이션** | TurtleBot3 + LiDAR + ROS Nav2 통합 | 중급 |
| **휴머노이드 로봇 시뮬레이션** | URDF 임포트 + 조인트 제어 + 센서 | 고급 |
| **협동 로봇 HRI 시스템** | 인간 작업자 + 안전 로봇 + 비전 시스템 | 고급 |
| **ROS 기반 원격 수술 시뮬레이터** | 다중 로봇 팔 + VR/AR 연동 | 고급 |
| **AI 쓰레기 분류 로봇** | 합성 데이터 학습 + 물체 인식 + 분류 | 중급 |

### 요구사항

| 카테고리 | 상세 항목 | 필수/선택 |
|---|---|---|
| **Unity 씬** | 최소 5개 이상의 3D 오브젝트, 조명, 충돌 환경 | 필수 |
| **로봇 모델** | URDF 기반 로봇, 최소 4-DOF | 필수 |
| **ROS 통합** | Unity ↔ ROS 양방향 통신 (최소 2개 토픽) | 필수 |
| **센서** | 최소 1개 가상 센서 (카메라/LiDAR/IMU) | 필수 |
| **제어** | ROS 메시지로 로봇 제어 | 필수 |
| **도메인 랜덤화** | 적용 (조명, 자세, 텍스처 중 2가지) | 선택 (가산점) |
| **ML-Agents** | RL 학습 통합 | 선택 (가산점) |
| **디지털 트윈** | 실제/가상 동기화 | 선택 (가산점) |
| **VR/AR** | XR 연동 | 선택 (가산점) |

### 제출 형식

```
team_XX_final/
├── UnityProject/
│   ├── Assets/
│   │   ├── Scripts/
│   │   ├── Prefabs/
│   │   ├── Scenes/
│   │   └── SyntheticData/ (선택)
│   └── ProjectSettings/
├── ROS/
│   ├── src/
│   └── launch/
├── docs/
│   ├── README.md (필수)
│   ├── architecture.md
│   └── demo.mp4 (선택)
└── evaluation/
    └── self_assessment.md
```

### 평가 기준

| 평가 항목 | 배점 |
|---|---|
| **기능 완성도** (모든 요구사항 충족, 안정적 작동) | 30% |
| **기술 깊이** (고급 기능 활용, 최적화) | 20% |
| **코드 품질** (구조화, 주석, 에러 처리) | 15% |
| **ROS 통합 품질** (지연, 안정성, 메시지 설계) | 15% |
| **문서화** (README, 아키텍처 설명) | 10% |
| **발표 및 시연** (10분 발표 + 5분 Q&A) | 10% |

### 일정
- **13주차**: 프로젝트 주제 선정 및 팀 구성 (3인)
- **14주차 전반**: 구현 및 테스트
- **14주차 후반**: 중간 점검 (멘토링)

---

## 15주차: 기말 발표 및 총평

### 발표 일정
- 팀당 15분 (10분 발표 + 5분 Q&A)
- 라이브 데모 필수 (녹화본은 백업)

### 발표 내용 구성

| 섹션 | 시간 | 내용 |
|---|---|---|
| 문제 정의 | 2분 | 어떤 문제를 해결하는가? |
| 아키텍처 | 2분 | 시스템 구성도 (Unity + ROS) |
| 주요 기능 | 3분 | 실제 데모 시연 |
| 기술적 도전 | 2분 | 어려웠던 점과 해결 방법 |
| 향후 계획 | 1분 | 개선점 및 확장 방안 |

### 총평 및 복습 (수업 시간 내)

| 주제 | 내용 |
|---|---|
| **과정 복습** | 1~14주차 주요 개념 요약 |
| **자주 하는 실수** | URDF 임포트 문제, TCP 연결 오류, 좌표계 변환 |
| **추가 학습 자료** | 아래 참고 자료 섹션 참조 |
| **커뮤니티** | ROS Discourse, Unity Robotics Forum, GitHub Discussions |
| **수료증** | 과정 수료증 배부 |

---

# 3. 평가 기준

## 3.1 성적 배분

| 항목 | 비율 | 세부 기준 |
|---|---|---|
| 출석 | 10% | 결석 1회당 -2%, 지각 3회 = 결석 1회 |
| 과제 | 20% | 주 1회, 총 13회 과제 (최하위 3회 제외) |
| 중간 프로젝트 | 30% | 8주차 발표 및 제출 |
| 기말 프로젝트 | 40% | 15주차 발표 및 제출 |

## 3.2 과제 감점 기준

| 항목 | 감점 |
|---|---|
| 지연 제출 (1일당) | -10% (최대 -50%) |
| 미작동 코드 | -30% |
| 주석 미포함 | -10% |
| ROS 연결 실패 | -20% |
| 표절 | 0점 처리 |

---

# 4. 참고 자료

## 4.1 공식 문서

| 자료 | 링크 |
|---|---|
| Unity Robotics Hub | https://github.com/Unity-Technologies/Unity-Robotics-Hub |
| ROS-TCP-Connector | https://github.com/Unity-Technologies/ROS-TCP-Connector |
| URDF Importer | https://github.com/Unity-Technologies/URDF-Importer |
| Unity Simulation Sensors | https://docs.unity3d.com/Simulation/manual/ |
| Unity ML-Agents | https://github.com/Unity-Technologies/ml-agents |
| ROS 공식 문서 | https://wiki.ros.org/ |
| ROS 2 공식 문서 | https://docs.ros.org/en/humble/ |
| MoveIt 2 문서 | https://moveit.picknik.ai/ |

## 4.2 추천 튜토리얼

| 난이도 | 튜토리얼 | 링크 |
|---|---|---|
| 초급 | Unity Roll-a-Ball | https://learn.unity.com/project/roll-a-ball |
| 초급 | Unity ROS Publisher/Subscriber | Unity-Robotics-Hub/tutorials/ros_unity_integration |
| 중급 | Pick and Place Tutorial | Unity-Robotics-Hub/tutorials/pick_and_place |
| 중급 | TurtleBot3 Navigation | Unity-Robotics-Hub/tutorials/turtlebot3_slam |
| 고급 | ML-Agents Robot Arm | ML-Agents/examples |
| 고급 | MoveIt + Unity 통합 | MoveIt 2 튜토리얼 |

## 4.3 참고 서적

| 제목 | 저자 | 비고 |
|---|---|---|
| "Programming Robots with ROS" | Morgan Quigley, Brian Gerkey, William D. Smart | ROS 기초 |
| "ROS Robotics by Example" | Carol Fairchild, Dr. Thomas L. Harman | ROS 실습 |
| "Unity in Action" | Joe Hocking | Unity 기초 |
| "Deep Reinforcement Learning Hands-On" | Maxim Lapan | RL + ML-Agents |

## 4.4 추천 프로젝트 아이디어 (심화 학습용)

- **Unity + Isaac Sim 연동**: USD 포맷을 통한 두 플랫폼 간 에셋 공유
- **Digital Twin of 실제 로봇**: ROS 2 + Unity로 실제 로봇의 디지털 트윈 구축
- **ROS 2 + Unity + WebRTC**: 웹 브라우저에서 원격 로봇 모니터링
- **Multi-Robot Warehouse**: 여러 로봇의 중앙 관제 시스템
- **Unity + O3DE 비교 연구**: 두 오픈 3D 엔진의 로봇 시뮬레이션 성능 비교

---

> **문서 버전**: v1.0  
> **최종 업데이트**: 2026년 5월  
> **작성자**: Sisyphus (OhMyOpenCode)
