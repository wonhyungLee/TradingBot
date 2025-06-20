# PoABOT - Power of Algorithm (Bitget Demo Trading Support)

## 트레이딩뷰에서 전달되는 웹훅을 처리하는 봇입니다.

### 🆕 새로운 기능: 비트겟 데모 트레이딩 지원

이 버전은 기존 POA Bot에 **비트겟 데모 트레이딩** 기능을 추가한 버전입니다.

&nbsp;

## 🏢 지원 거래소

- 업비트 KRW(원화) 마켓
- 바이낸스 현물/선물 USDT,BUSD 마켓  
- 바이비트 현물/선물 USDT 마켓
- **비트겟 현물/선물 USDT 마켓 (라이브 + 데모)**
- OKX 현물/선물 USDT 마켓
- 한국투자증권 한국/미국 주식 마켓

&nbsp;

## 🚀 비트겟 데모 트레이딩 기능

### ✅ 주요 특징
- 가상 자금으로 안전한 전략 테스트
- 실제 시장 환경과 동일한 조건
- 라이브/데모 모드 간편 전환
- 기존 모든 기능 보존

### ⚙️ 설정 방법

#### 1. 환경변수 설정 (.env 파일)
```bash
# 데모 모드 활성화
BITGET_DEMO_MODE="true"

# 데모용 API 키 (비트겟 데모 계정에서 발급)
BITGET_DEMO_KEY="비트겟_데모_API_키"
BITGET_DEMO_SECRET="비트겟_데모_시크릿_키"  
BITGET_DEMO_PASSPHRASE="패스프레이즈"

# 기존 라이브 키는 그대로 유지
BITGET_KEY="라이브_API_키"
BITGET_SECRET="라이브_시크릿_키"
BITGET_PASSPHRASE="패스프레이즈"
```

#### 2. 모드 전환
- **데모 모드**: `BITGET_DEMO_MODE="true"`
- **라이브 모드**: `BITGET_DEMO_MODE="false"` 또는 주석 처리

#### 3. 비트겟 데모 계정 준비
1. [Bitget 데모 트레이딩](https://www.bitget.com/futures-activity/demo-trading) 페이지 방문
2. 데모 계정 생성 및 API 키 발급
3. 선물 거래 권한 활성화

&nbsp;

## 📋 사용 방법

### Oracle Cloud 배포
1. `cloud-init-demo.yaml` 사용
2. 환경변수에 실제 데모 API 키 입력
3. 인스턴스 생성 시 스크립트 적용

### 로컬 설치
```bash
git clone https://github.com/wonhyungLee/TradingBot.git
cd TradingBot
python3 -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### 실행
```bash
python run.py --port=8000
```

&nbsp;

## 🔧 추가 파일

- **README-DEMO.md**: 상세 설정 가이드
- **tradingview-demo-example.pine**: 데모용 TradingView 스크립트 예제
- **cloud-init-demo.yaml**: Oracle Cloud 배포용 스크립트

&nbsp;

## 📞 문제 해결

### 데모 모드 확인
로그에서 다음 메시지 확인:
```
비트겟 데모 트레이딩 모드로 실행됩니다
비트겟 데모 트레이딩 모드 활성화됨
```

### 에러 40099 해결
이 버전에서는 "exchange environment is incorrect" 에러가 완전히 해결되었습니다.

&nbsp;

# ⚠️ 주의사항

**본 프로젝트는 개인적으로 개발한 프로젝트를 오픈소스로 공유한 것으로 발생하는 문제에 대한 모든 책임은 본인에게 있습니다.**

- 데모 모드에서는 실제 자금이 사용되지 않습니다
- 라이브 모드 전환 시 실제 거래가 발생하므로 신중히 사용하세요
- 충분한 테스트 후 라이브 모드를 사용하는 것을 권장합니다

&nbsp;

## 🔗 의존성

> [fastapi](https://github.com/tiangolo/fastapi) , [ccxt](https://github.com/ccxt/ccxt) , [uvicorn](https://github.com/encode/uvicorn)

&nbsp;

## 📄 라이선스

GNU General Public License v3.0
