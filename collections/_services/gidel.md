---
title: "Gidel"
description: "FPGA 기반 고성능 비전 처리 솔루션"
date: 2019-10-03
weight: 5
header_transparent: false
fa_icon: false
icon: "assets/images/icons/icons8-merge-git-100.png"
thumbnail: "/assets/images/gen/services/service-8-thumbnail.webp"
image: "/assets/images/gen/services/service-8.webp"

hero:
  enabled: true
  heading: "Gidel"
  sub_heading: "FPGA 기반 고성능 비전 처리 솔루션"
  text_color: "#ffffff"
  background_color: ""
  background_gradient: true
  background_image_blend_mode: false # "overlay", "multiply", "screen"
  background_image: "/assets/images/gen/services/service-8.webp"
  fullscreen_mobile: false
  fullscreen_desktop: false
  height: 660px
  buttons:
    enabled: false
    list:
      - text: "Buy Now"
        url: "https://www.zerostatic.io/theme/jekyll-advance/"
        external: true
        fa_icon: false
        size: large
        outline: false
        style: "primary"
---

## FPGA 기반 고성능 비전 처리 솔루션

**Gidel**은 **FPGA 기술 기반의 결정론적 실시간 처리**와 **멀티 카메라 동기화**를 핵심으로 하는 고성능 머신 비전 처리 솔루션입니다. CPU/GPU 대비 **예측 가능한 이상 지연** 처리와 **프레임 레벨 연속 처리** 보장으로, 제로 프레임 로스가 요구되는 **고속 산업 검사·UAV·방산·의료** 등 다양한 분야에 즉시 적용 가능합니다.

---

## Gidel로 할 수 있는 것

### 결정론적 실시간 처리로 프레임 손실 제로
- CPU/GPU 대비 **예측 가능한 이상 지연** 처리
- 하드웨어 파이프라인으로 **프레임 레벨 연속 처리** 보장
- 실시간 임베디드 시스템에 적합한 **타이밍 정확도**

### 다중 인터페이스로 유연한 카메라 연결
- **GigE Vision / CoaXPress-12 / Camera Link** 등 주요 산업용 카메라 인터페이스 지원
- 단일 보드에서 복수 인터페이스 동시 이용 가능
- **PCIe 기반 고속 데이터 전송**으로 대역폭 최대 활용

### 실시간 FPGA 압축으로 대역폭 절감
- **JPEG / Lossless / Quality+** 등 다양한 압축 방식 지원
- FPGA에서 직접 압축 처리 → **CPU 부하 최소화**
- 화질 손실 없이 대역폭 절감 가능한 **Quality+ 압축** 기술

### InfiniVision으로 100대 이상 카메라 동기화
- **마이크로초 단위 동기화** 정확도
- 체적 영상, 멀티뷰 시스템 최적화
- 하드웨어 트리거 기반 **대규모 멀티카메라 제어**

---

## 주요 제품

### Frame Grabber — HawkEye 시리즈
- **지원 인터페이스**: GigE Vision / CoaXPress-12 / Camera Link
- PCIe 슬롯 장착형, FPGA 모델 선택 가능 (용량·성능에 따라)
- DMA 직접 전송, 제로 프레임 로스로 **시스템 성능 향상**
- **InfiniVision** 기술로 멀티카메라 동기화 확장 지원

---

### FantoVision — 엣지 컴퓨터

<div style="display:flex; gap:2rem; align-items:flex-start; margin-bottom:2rem;">
<div style="flex:1;" markdown="1">

- **FPGA + Jetson(NVIDIA)** 기반 AI 엣지 컴퓨팅 내장
- 현장(엣지)에서 직접 AI 추론 처리 → **클라우드 의존도 제거**
- **내환경 설계**: 광온도 범위, 진동·충격 내성, 소형·저전력
- UAV·드론·임베디드 환경 최적화

| 모델 | 특징 |
|---|---|
| FV20-GV | GigE Vision 지원, 소형 엣지 컴퓨터 |
| FV20-CL | Camera Link 지원 |
| FV40-CXP12 | CoaXPress-12 지원, 고해상도 처리 |
| FV40 | 고성능 확장형 |

</div>
<div style="flex-shrink:0;">
<img src="/assets/images/gen/services/service-8-thumbnail.webp" width="320">
</div>
</div>

---

### Camera Simulator — CamSim

<div style="display:flex; gap:2rem; align-items:flex-start; margin-bottom:2rem;">
<div style="flex:1;" markdown="1">

- **최대 해상도**: 16K × 65K 픽셀
- **메모리 옵션**: 1GB / 8GB / 16GB
- 실제 카메라 없이 영상 스트림 재현 → **개발·테스트 환경 구축 비용 절감**
- 반복 재현 가능한 테스트 시나리오 작성

| 모델 | 특징 |
|---|---|
| CamSim-CL | Camera Link 방식 |
| CamSim-X | 확장형 |

</div>
<div style="flex-shrink:0;">
<img src="/assets/images/gen/services/service-8-thumbnail.webp" width="320">
</div>
</div>

---

### Imaging Library — GIL

<div style="display:flex; gap:2rem; align-items:flex-start; margin-bottom:2rem;">
<div style="flex:1;" markdown="1">

- **CPU 오프로딩**: FPGA가 영상처리 담당 → CPU는 비즈니스 로직 집중
- **IP 코어 구성**: 필요 기능만 선택·조합하여 커스텀 파이프라인 구성
- **압축 IP 코어**: JPEG / Lossless / Quality+ 방식 지원
- **FPGA 가상화**: 하나의 FPGA를 다중 작업으로 분할 이용
- **GenICam 표준 & ProcVision Suite** 연동 지원

</div>
<div style="flex-shrink:0;">
<img src="/assets/images/gen/services/service-8-thumbnail.webp" width="320">
</div>
</div>

---

## 적용 분야

### 🏭 산업용 비전 & 이미지 처리
> ❌ 고속 라인에서 프레임 누락·지연 발생 / CPU 병목으로 실시간 처리 한계<br>→ ✅ **Zero Frame Loss 보장** / **FPGA 실시간 압축으로 CPU 부하 최소화**

- HawkEye PCIe + FPGA 압축 IP + SkyBoost(50배 향상) + GIL 커스텀 IP
- **Zero Frame Loss** 보장으로 고속 생산라인 100% 검사 가능
- 대용량 이미지 실시간 처리 및 저장

---

### 🚁 UAV / 드론 영상 시스템
> ❌ 드론 환경에서 데이터 전송 대역폭 부족 / 진동·충격으로 장비 신뢰성 문제<br>→ ✅ **FPGA 압축으로 전송 대역폭 절감** / **내환경 설계로 드론 환경 대응**

- FantoVision 탑재, FPGA 압축으로 전송 대역폭 절감
- **내환경 설계** (진동·충격·광온도 범위)로 드론 환경 대응
- 소형·저전력 설계로 드론 탑재 적합

---

### 🛡️ 방산·항공 영상 시스템
> ❌ 다중 카메라 동기화 정밀도 부족 / 군용 내환경 인증 요건<br>→ ✅ **InfiniVision 마이크로초 동기화** / **군용 내환경 인증 옵션 지원**

- HawkEye / FantoVision 조합, InfiniVision 다중 카메라 동기화
- ROI(관심영역) 추출 + FPGA 실시간 압축
- 군용 내환경 인증 옵션 지원

---

### 🏥 의료 영상
> ❌ 고동적 범위 영상의 실시간 처리 어려움 / 수술 중 다각도 내시경 제어 필요<br>→ ✅ **HDR IP 코어로 고동적 범위 처리** / **다각도 내시경 영상 지원**

- FantoVision AI + FPGA 기반 실시간 분석
- **HDR IP** 코어로 고동적 범위 영상 처리
- **ThermoMind**: FPGA 기반 적외선 이미지 진단 솔루션
- **270 Surgical SURROUND SCOPE**: 수술 중 다각도 내시경 영상 지원

---

### 🔬 광학 검변
> ❌ 다중 채널 동시 수집 시 타이밍 불일치 / 커스텀 검변 알고리즘 적용 어려움<br>→ ✅ **HawkEye 다중 채널 동시 수집** / **ProcVision Suite 커스텀 알고리즘 적용**

- HawkEye 다중 채널 동시 수집, FPGA 압축 IP로 실시간 처리
- ProcVision Suite 기반 커스텀 검변 알고리즘 적용
- InfiniVision으로 다중 카메라 동기화 → 전방위 결함 검출

---

### 🎬 체적 영상 & AR (Volumetric Video)
> ❌ 100대 이상 카메라 동기화 어려움 / 고화질 체적 영상 생성 비용<br>→ ✅ **InfiniVision 100+ 카메라 동기화** / **HDR + GIL Recording 고화질 영상**

- **InfiniVision** 100대 이상 카메라 동기화
- HDR IP + GIL Recording으로 고화질 체적 영상 생성
- **Intel FreeD / TrueView** 프로토콜 지원
- **NFL, 올림픽** 등 스포츠 중계 레퍼런스 보유

---

## 솔루션 시나리오

### 시나리오 ① 고해상도·대용량 이미지 분산처리

**구성 흐름**: 고속 카메라 → Gidel FantoVision → VCANUS Flowbroker → 처리노드 1/2/N → 분석 결과

| 핵심 가치 | 내용 |
|---|---|
| 데이터 소스 안정 고속 수집 | FantoVision FPGA로 프레임 드롭 없이 안정 수집 |
| 자동 부하 분산 처리 | VCANUS Flowbroker가 처리노드에 자동 분배 |
| 이중 효율 & 유연한 확장 | 처리노드 추가만으로 선형 성능 확장 |

---

### 시나리오 ② 스테이지 연동 정밀촬영 및 이미지 병합

**구성 흐름**: 엔코더 → FPGA HawkEye → 카메라+조명 → DMA 버퍼 → 병합 영상

| 핵심 가치 | 내용 |
|---|---|
| 위치 기반 트리거링 | 엔코더 신호로 정확한 촬영 위치 동기화 |
| 조명·카메라 동기화 | FPGA 하드웨어 트리거로 조명·카메라 동시 제어 |
| 실시간 이미지 병합 | DMA 버퍼 경유 즉시 병합 영상 영상 생성 |

---

### 시나리오 ③ 이상 지연 웹 기반 모니터링 및 AI 기반 실시간 분석

**구성 흐름**: 카메라 → 엣지 AI 처리 → 지능형 분석 → 이상 지연 전송 → 웹 대시보드

| 핵심 가치 | 내용 |
|---|---|
| 엣지 배착형 AI 처리 | FantoVision 현장에서 직접 AI 추론, 클라우드 불필요 |
| 이상 지연 웹 모니터링 | 현장 수집·분석 결과를 웹 대시보드로 실시간 전송 |
| 이중 효율 & 기대효과 | 불량 즉시 감지, 엄격 모니터링으로 인력 절감 |

---

## 전체 솔루션 핵심 메시지

| 구분 | 핵심 포인트 |
|---|---|
| **하드웨어** | FPGA 기반 결정론적 실시간 처리 → 예측 가능한 이상 지연, 제로 프레임 로스 |
| **소프트웨어** | ProcVision Suite + GIL → 커스텀 IP 구성, CPU 오프로딩 |
| **확장성** | InfiniVision 100+ 카메라 동기화, VCANUS Flowbroker 분산처리 |
| **엣지 AI** | FantoVision FPGA+Jetson → 현장 즉시 추론, 클라우드 미의존 |
| **적용 범위** | 산업비전, UAV, 방산, 의료, 스포츠 AR, ATE 등 광범위 |
