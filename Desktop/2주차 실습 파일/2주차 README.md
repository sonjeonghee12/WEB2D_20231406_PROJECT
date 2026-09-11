# [프로젝트명] — 웹게임(2D) 기반 그래픽 실습

> 컴퓨터그래픽스(2) | 2026학년도 2학기 | 담당교수: 최도현
> 작성자: (학번) / (이름)
> 최종 수정일: (YYYY-MM-DD)

---

## 목차

1. [프로젝트 개요](#1-프로젝트-개요)
2. [개발 환경](#2-개발-환경)
3. [x 주차 별 세부 내용]
4. [실행 방법](#5-실행-방법)
5. [트러블슈팅 기록](#6-트러블슈팅-기록)
6. [참고 자료](#7-참고-자료)

---

## 1. 프로젝트 개요

| 항목 | 내용 |
|---|---|
| 프로젝트명 | (예: Survivor 2D) |
| 장르 | 2D 탑뷰 서바이벌 액션 (Vampire Survivors 스타일) |
| 플랫폼 | Web (WebGL2) |
| 조작 | WASD / 방향키 이동, 자동 공격 |
| 한 줄 소개 | (자신의 게임을 한 문장으로 설명) |

---

## 2. 개발 환경

| 항목 | 값 |
|---|---|
| Unity 버전 | 6000.5.1f1 |
| Render Pipeline | Universal RP (2D Renderer) |
| Input System | New Input System (Input System Package) |
| UI | TextMesh Pro |
| 웹 빌드 | WebGL 2 (WebGPU 실험적 지원 별도) |

---

## 3. 2주차 — 프로젝트 준비 & 웹 빌드

### 3.1 프로젝트 초기 세팅

- [ ] Unity 6000.5.1f1로 2D URP 템플릿 프로젝트 생성
- [ ] `2주차_StarterProject.unitypackage` 임포트
- [ ] `CG2 Starter → Step 1 → Step 2 → Step 3` 순서로 씬 빌드
- [ ] ▶ Play 버튼으로 정상 동작 확인 (WASD 이동, 자동 공격, 적 스폰)

### 3.2 씬 구성 요약

```
Player      SpriteRenderer(Order 2) · Rigidbody2D · CircleCollider2D
            PlayerController · HitReceiver · Health · WeaponController

Enemy       SpriteRenderer(Order 1) · Rigidbody2D · CircleCollider2D
            EnemyAI · HitReceiver · Health

Projectile  SpriteRenderer(Order 3) · Rigidbody2D · CircleCollider2D(Trigger)
            Projectile

Canvas      Screen Space - Overlay · HUD(Script)
            HpBar / ExpBar / ScoreText / LevelText / TimeText / GameOverPanel
```

### 3.3 웹 빌드 확인

- [ ] `File → Build Profiles → Web → Build And Run`으로 브라우저 실행 확인
- [ ] 빌드 소요 시간: 약 ( )분
- [ ] 브라우저 정상 실행 여부: (예/아니오)

**웹 빌드 vs 에디터 Play 차이**

| 항목 | 에디터 Play | 웹 빌드 |
|---|---|---|
| 실행 속도 | 즉시 | 1~3분 |
| 확인 목적 | 로직 테스트 | 실제 브라우저 동작 확인 |

### 3.4 GitHub 업로드 체크리스트

- [ ] `.gitignore`에 `Library/`, `Temp/`, `Obj/`, `Build/`, `Logs/`, `UserSettings/` 포함 확인
- [ ] `Assets/`, `ProjectSettings/`, `Packages/`는 반드시 포함
- [ ] 개별 파일 100MB 초과 여부 확인 (대용량은 Git LFS 고려)

## 4. 실행 방법

### 에디터에서 실행

```
1. Unity 6000.5.1f1로 프로젝트 열기
2. Assets/StarterProject/Scenes/SampleScene 열기
3. ▶ Play 버튼 클릭
```

### 웹 빌드 실행

```
1. File → Build Profiles → Web 선택
2. Build And Run 클릭
3. 브라우저에서 자동 실행 확인
```

---

## 5. 트러블슈팅 기록

> 진행 중 겪은 문제와 해결 과정을 기록하세요 (선택 사항이지만 권장).

| 문제 | 원인 | 해결 방법 |
|---|---|---|
| (예: unitypackage 임포트 실패) | (예: 압축 구조 불일치) | (예: 개별 스크립트 수동 교체) |
| | | |

---

## 6. 참고 자료
- 수업 자료: 2주차 PPT
