# 원본 출처 및 포트폴리오 정리 기록

| 항목 | 내용 |
| --- | --- |
| 원본 팀 저장소 | https://github.com/yuudong123/ai-first-project |
| 복사 브랜치 | `master` |
| 기준 커밋 | [`09c495e0767aa615e5e6bd1f155bf65c41f7ded2`](https://github.com/yuudong123/ai-first-project/tree/09c495e0767aa615e5e6bd1f155bf65c41f7ded2) |
| 복사·정리일 | 2026-10-11 |
| 포트폴리오 작성자 | 홍유나 · `h-yuna-lab` |

팀 결과물의 특정 시점을 개인 포트폴리오 저장소의 `main` 브랜치로 정리했습니다. 원본의 개발 커밋 이력은 위 링크에 보존되어 있으며, 이 저장소의 초기 커밋은 복사본 정리 기록입니다.

## 개인 담당 근거

- [팀 마일스톤](team-milestones.md): 기간과 데이터 분석·전처리·EDA·특징 추출, 모델 학습·평가·SHAP 담당
- [상세 작업 명세](team-task-board.md): 모델·데이터 업무의 범위와 완료 기준
- [최종 발표자료](HydroTwin%20프로젝트%20최종%20발표자료%20%28수정%20완성본%29.pdf): 홍유나 AI/UIUX 역할, 모델 비교 결과와 프로젝트 화면
- 실제 코드: 17개 평균 특징, 사이클 분할, 51개 이동 구간, LightGBM 번들, TreeSHAP 진단

팀 문서에 배정된 개인 업무와 코드에서 확인되는 구현을 연결했습니다. Unity 구현, Kafka·API·웹 화면 구현, Docker·Jenkins 운영 전체를 개인 단독 성과로 표시하지 않았습니다.

## 보존 및 변경 범위

- GitHub 고정 커밋 ZIP의 원본 파일 87개를 복사했습니다.
- Python·JavaScript·노트북·설정·테스트 코드를 수정하지 않았습니다.
- 원본 README는 `README.original.md`에 보관하고, 루트 README를 포트폴리오 설명으로 교체했습니다.
- 이 출처 문서와 `screenshots/unity.jpg`, `screenshots/sensor-impact.jpg`를 추가했습니다.
- 원본에서 이미 추적 중이던 V5 생성 모델 파일 및 WebGL 빌드 파일은 그대로 보존했습니다. 새로운 Unity 빌드를 생성하지 않았습니다.
- 원본 Git에서 제외된 UCI 데이터, 전처리 결과, 상태 분류 모델, 로컬 인증정보는 복사하지 않았습니다.
- 개인 이력서·연락처가 들어 있는 입사지원서 HWP는 이 저장소에 포함하지 않았습니다.

## 화면 출처

두 JPEG는 최종 발표자료의 `HydroTwin 관제 시스템 | Web Dashboard` 페이지에 포함된 Unity 관제 화면과 이상 알림·SHAP 화면에서 추출했습니다. 이번 정리 중 새로 촬영한 화면이나 전체 서비스 실행 결과가 아닙니다.

## 검증 기록

2026-10-11 로컬 Python·Node 런타임에서 다음 원본 테스트를 확인했습니다.

- `tests/test_retrain_gate.py`: 9개 통과
- `tests/test_drift_detector.py`: 2개 통과
- `tests/test_sensor_bands.py`: 4개 통과
- `tests/test_equipment_state.cjs`, `tests/test_sensor_bands.cjs`: 합계 6개 통과

Python 검사는 로컬 NumPy·pandas와 별도로 준비한 pytest, FastAPI 0.116.1, httpx 0.28.1 환경에서 수행했습니다. API 테스트에 필요한 의존성이 처음에는 없어 해당 2개가 실패했으며, 의존성을 준비한 뒤 두 테스트의 통과를 확인했습니다. 전체 `requirements.txt`의 버전을 모두 설치한 환경에서 전체 테스트를 실행한 것은 아닙니다.

모델 재학습·추론 시간 재측정·Kafka·Docker·Jenkins·Unity 통합 실행은 수행하지 않았습니다. README의 정확도·Macro F1·추론 시간은 팀 최종 발표자료에 보고된 검증 수치를 인용했습니다.

## 문서와 코드의 차이

- 일부 기획 문서의 React·Tailwind와 달리 실제 웹 화면은 HTML·JavaScript·Chart.js입니다.
- 현재 파이프라인은 사이클 내 모든 10초 위치를 사용합니다. 발표자료의 모델 비교 수치가 현재 이동 구간 학습 코드를 다시 실행한 결과라고 단정하지 않았습니다.
- 발표자료의 초기 아키텍처 그림에 표시된 Kafka 토픽·추가 API 대신 현재 코드를 기준으로 README의 구조를 작성했습니다.
- 원본 README의 Unity 빌드가 로컬 자산이라는 설명과 달리, 기준 커밋에는 `web/Build/` 파일도 포함되어 있습니다. 편집용 Unity 프로젝트는 포함되어 있지 않습니다.

팀 코드·자료의 원본 출처와 저작자를 유지하고 별도의 라이선스를 새로 부여하지 않았습니다. UCI 데이터 라이선스는 원본 데이터셋의 CC BY 4.0을 따릅니다.
