# ChromaShift 🎮

Flutter Flame을 사용한 색상 매칭 게임입니다.

## 📱 게임 설명

색상을 변경하여 다가오는 게이트와 같은 색상으로 맞춰서 통과하세요!
시간이 지날수록 게이트 속도가 빠르게 증가합니다.

### 🎯 게임 방법

- **모바일/터치**: 화면 왼쪽/오른쪽을 터치하여 색상 변경
- **PC/키보드**: 방향키(←→)로 색상 변경
- **목표**: 게이트와 같은 색상으로 맞춰서 통과
- **게임 오버**: 색상이 다르면 즉시 게임 오버!

### 🎨 색상 변경 순서

```
[ Blue ] <-> [ Green ] <-> [ Brown ] <-> [ Yellow ] <-> [ Red ]
```

- **기본 색상**: Brown
- 양쪽 끝 색상(Blue, Red)에서는 한 방향으로만 이동 가능

## ✨ 주요 기능

### 🎮 게임 플레이
- 원근법 효과가 적용된 3D 게이트
- 시간에 따른 난이도 증가 (속도 상승)
- 직관적인 터치/키보드 컨트롤
- 실시간 점수 및 시간 표시
- 색상 인디케이터 HUD

### 📊 통계 시스템 (NEW!)
- **전체 통계**: 최고 점수, 최장 생존 시간, 평균 점수 등
- **랭킹**: Top 10 점수/생존시간/게이트 통과 순위
- **색상별 통계**: 5가지 색상별 성공률 및 상세 통계
- **업적 시스템**: 15개의 달성 가능한 업적
- **로컬 저장**: Hive 데이터베이스로 모든 플레이 기록 저장
- **크로스 플랫폼**: 안드로이드, iOS, 웹 모두 지원

## 🚀 실행 방법

### 1. 의존성 설치
```bash
flutter pub get
```

### 2. Hive 코드 생성 (처음 한 번만)
```bash
flutter pub run build_runner build --delete-conflicting-outputs
```

### 3. 앱 실행

**Chrome (웹):**
```bash
flutter run -d chrome
```

**Android/iOS:**
```bash
flutter run
```

## 📂 프로젝트 구조

```
lib/
├── models/                    # 데이터 모델
│   ├── game_record.dart      # 게임 기록
│   └── achievement.dart      # 업적
├── services/                  # 비즈니스 로직
│   ├── database_service.dart # 데이터베이스 CRUD
│   └── statistics_service.dart # 통계 계산
├── pages/                     # UI 페이지
│   └── statistics_page.dart  # 통계 화면
├── chroma_shift.dart         # 게임 메인 로직
├── player_square.dart        # 플레이어 컴포넌트
├── gate.dart                 # 게이트 컴포넌트
├── game_over_overlay.dart    # 게임 오버 화면
└── main.dart                 # 앱 진입점 + 메뉴
```

## 🛠️ 기술 스택

- **Flutter**: 크로스 플랫폼 UI 프레임워크
- **Flame Game Engine** (^1.16.0): 2D 게임 엔진
- **Hive** (^2.2.3): 고속 NoSQL 로컬 데이터베이스
- **Material Design 3**: 모던한 UI/UX

## 📊 통계 시스템 상세

통계 시스템에 대한 자세한 내용은 [STATISTICS_README.md](STATISTICS_README.md)를 참고하세요.

### 저장되는 데이터
- 플레이 시각, 점수, 플레이 시간
- 통과한 게이트 수, 실패한 색상
- 색상별 통과 횟수 (Blue, Green, Brown, Yellow, Red)
- 색상 전환 횟수

### 4개의 통계 탭
1. **전체 통계**: 주요 기록 및 평균 통계
2. **랭킹**: 점수/생존시간/게이트 Top 10
3. **색상별 통계**: 5가지 색상의 성공률
4. **업적**: 15개 달성 가능 업적

## 🎯 업적 목록 (총 19개)

- 🎮 첫 발걸음 - 첫 게임 플레이
- 🌟 점수 100/500/1000/5000 달성
- ⏱️ 생존 10/30/60초
- 🚪 게이트 10/25/50개 통과
- 📊 총 플레이 10/50회
- ⌚ 총 플레이 시간 1시간
- 🎨 색상별 마스터 (5개)
  - 🔵 블루 마스터 - 파란색 10번 이상 통과, 실패 0회
  - 🟢 그린 마스터 - 녹색 10번 이상 통과, 실패 0회
  - 🟤 브라운 마스터 - 갈색 10번 이상 통과, 실패 0회
  - 🟡 옐로우 마스터 - 노란색 10번 이상 통과, 실패 0회
  - 🔴 레드 마스터 - 빨간색 10번 이상 통과, 실패 0회

## 💡 게임 팁

1. **색상 순서 암기**: Blue-Green-Brown-Yellow-Red 순서를 외우세요
2. **미리 준비**: 다음 게이트 색상을 보고 미리 색상을 맞추세요
3. **최소 이동**: 색상 거리가 가까운 방향으로 이동하세요
4. **연습**: 처음엔 느리지만 시간이 지나면 속도가 빨라집니다!

## 🌐 지원 플랫폼

- ✅ Android
- ✅ iOS
- ✅ Web (Chrome, Edge, Safari)
- ✅ Windows
- ✅ macOS
- ✅ Linux

## 📝 라이센스

Copyright © 2026 Jammy Bastards. All rights reserved.
