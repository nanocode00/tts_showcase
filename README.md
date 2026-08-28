# 말로(Mallo) TTS Final Showcase

고령 사용자를 위한 Voice-first 키오스크 주문 시스템 **말로(Mallo)**의 TTS(Text-to-Speech) 최종 평가 정적 쇼케이스입니다.

- **GitHub Pages 배포 URL**: https://nanocode00.github.io/tts_showcase/

## 개요

- **모델 비교**: MeloTTS baseline vs MeloTTS fine-tuned G_2800 (대표 주문 문장 3종, 6개 WAV)
- **Adaptive Speed Levels**: 고령 사용자 친화적 발화 속도(Level 0: 0.95x, Level 1: 0.85x, Level 2: 0.70x) 및 문장 분절 정책 (대표 주문 문장 3종, 9개 WAV)
- **공통 텍스트 정규화**: 수사·금액 단위 한글화(`normalize_korean_text_for_tts`) 적용
- **독립 정적 배포**: 백엔드, API, 외부 네트워크 의존성 없이 GitHub Pages에서 100% 동작 (상대 경로 참조)

## 사이트 구성

- `index.html`: 통합 쇼케이스 메인 페이지 (모델별 비교 및 Level 0·1·2 전체 청음)
- `model-comparison.html`: MeloTTS Baseline vs Fine-tuned G_2800 모델 비교 전용 페이지
- `speed-levels.html`: Adaptive Speed Levels (Level 0·1·2) 속도·분절 비교 전용 페이지
- `results.json`: 15개 합성 음성의 레이턴시, 재생 시간, 샘플레이트, 입력 텍스트 메타데이터
- `audio/`: 프로젝트 자체 작성 문장으로 합성된 44.1kHz mono WAV 파일 15개

## 로컬 확인

```bash
python3 -m http.server 8000
```
브라우저에서 `http://localhost:8000/` 접속

## 데이터 출처 및 라이선스 고지

본 TTS 모델은 AI Hub 「감성 및 발화 스타일 동시 고려 음성합성 데이터」(데이터셋 번호 71349)를 활용해 학습되었습니다.
공개된 음성 샘플은 AI Hub 원천·라벨링·재가공 데이터가 아니며, 프로젝트에서 직접 작성한 새로운 문장을 학습된 모델로 생성한 결과물입니다.
