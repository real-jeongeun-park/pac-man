
# 👻 PAC-MAN

Java 기반 클래식 아케이드 게임 **PAC-MAN**입니다. 1980년 발매된 원작 게임을 JAVA로 재구현하는 것을 목표로 진행한 프로젝트입니다.


<img width="300" height="300" alt="1" src="https://github.com/user-attachments/assets/ca00015e-1692-4db7-a20d-60ed2f854bf4" />
<img width="300" height="300" alt="2" src="https://github.com/user-attachments/assets/be345396-8031-46ff-ae75-33285e1097d5" />
<img width="300" height="300" alt="3" src="https://github.com/user-attachments/assets/e829703d-3522-4d6e-8f96-348af5ed8851" />

## 📌 게임 소개

플레이어는 방향키로 Pacman을 조작해 맵에 흩어진 포인트를 모두 획득하면서, 자유롭게 맵을 배회하는 적(유령)을 피해 생존하는 게임입니다.

- 맵의 모든 포인트를 얻으면 **Level**이 올라가고, 새로운 맵이 초기화되며 적의 수와 이동 속도가 함께 증가합니다.
- 적과 충돌하면 생명력(**Lives**)이 하나 감소하며, 생명력이 0이 되면 `You Died!` 화면과 함께 게임이 종료됩니다.
- 포인트 획득 시 Score가 오르며, 화면 하단에 현재 Level / Score / 남은 생명력이 표시됩니다.

## 🛠 사용 기술 / 개발 환경

- **언어**: Java
- **개발 환경**: Eclipse (JAVA Project)
- **주요 API / 라이브러리**
  - `javax.swing`, `java.awt` — `JFrame`, `JPanel` 기반 게임 화면 구성
  - `Graphics2D` — 맵, 캐릭터, 텍스트 등 2차원 요소 렌더링
  - `javax.sound.sampled` (`AudioInputStream`, `Clip`) — 배경음 및 효과음 재생
  - `javax.swing.Timer` — 40ms(0.04초) 간격으로 `repaint()`를 호출해 화면을 지속적으로 갱신
  - `KeyAdapter` — 키보드 입력을 통한 Pacman 이동 제어

## 🧩 프로젝트 구조

프로젝트는 역할에 따라 3개의 클래스로 구성됩니다.

| 클래스 | 역할 |
|---|---|
| `Pacman.java` | `JFrame`을 상속받아 애플리케이션의 기본 창(화면 틀)을 구성 |
| `Model.java` | `JPanel`을 상속받아 게임 진행에 필요한 모든 로직(맵 생성, 이동, 충돌 판정, 점수 계산 등)을 구현 |
| `GameKeyControlAdapter.java` | `KeyAdapter`를 상속받아 사용자의 키보드 입력을 받아 Pacman의 이동을 제어 |

`Pacman.java`에서 `Model` 객체를 생성해 화면에 표시하고, `Model` 초기화 과정에서 `GameKeyControlAdapter` 객체를 생성해 `KeyListener`로 등록하는 구조입니다.

## 🎮 조작 방법

| 키 | 동작 |
|---|---|
| ↑ / ↓ / ← / → | Pacman 이동 |
| Space Bar | 게임 시작 / 재시작 |
| ESC | 게임 일시 중단 |

## 🖼 실행 화면

- **초기 화면**: 타이틀과 함께 `press Space Bar to start` 안내 표시
- **게임 화면**: 미로, Pacman, 적, 도트, 하단 상태바(Level / Score / Lives) 표시
- **종료 화면**: 생명력이 0이 되면 `You Died!` 알림과 함께 재시작 안내


## 📁 참고

자세한 설계 과정(순서도), 클래스 설계, 구현 코드 및 결과 분석은 `report.pdf`를 참고해 주세요.
