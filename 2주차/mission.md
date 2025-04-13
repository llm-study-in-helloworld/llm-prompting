# Prompt Engineering 실습: 이미지 처리 API 아키텍처 생성

## ✨ 목적: Prompt 로 복잡한 아키텍처 설계 자동 생성하기

> 이 문서는 이미지 처리 API 시스템 아키텍처를 프롬프트 엔지니어링으로 만들어내는 연습을 위한 실습 예제입니다.
> 
> 목표는 아키텍처 설계, 프로젝트 구조, 자원 정의, 비용 산정까지 모든 내용을 "LLM Prompt" 로 만들어내도록 연습하는 것입니다.

---

## ✅ 전체 과제 목표 정리

1. 복잡한 기능 요구사항을 LLM 을 통해 표로 정리하는 Prompt 설계
2. 시스템 아키텍처를 텍스트 다이어그램으로 생성하는 Prompt 설계
3. 실제 프로젝트 폴더 구조를 생성하는 Prompt 설계
4. 필요한 인프라 자원을 표로 정리하는 Prompt 설계
5. 선택지 별 평균 비용과 특징을 표로 정리하는 Prompt 설계

---

## 1. 요구사항 분석 Prompt 실습

### 📝 과제 목표
- 복잡한 기능 요구 사항을 LLM 을 통해 정리된 요구사항 표로 도출하는 Prompt 작성하기

### 🎯 기대 출력 예시
| 구분 | 설명 |
|------|------|
| 클라이언트 요청 | 이미지 URL 로 API 호출 |
| API 서버 동작 | 요청을 받고 Queue 에 전달 후 URL 반환 |
| 이미지 처리 | 약 10초 소요, Worker 에서 처리 |
| 결과 저장소 | S3 에 업로드 후 URL 생성 |
| 모니터링 | Prometheus, Grafana 로 처리 현황 수집 및 시각화 |

---

## 2. 전체 아키텍처 다이어그램 생성 Prompt 실습

### 📝 과제 목표
- 시스템 아키텍처를 텍스트 기반 다이어그램으로 생성하는 Prompt 설계

### 🎯 기대 출력 예시
```
[Client] → [API Server (NestJS)] → [Queue (Kafka / Redis)] → [Worker] → [S3]
                                            → [Prometheus] → [Grafana]
```

---

## 3. 프로젝트 폴더 구조 생성 Prompt 실습

### 📝 과제 목표
- 실제 프로젝트 폴더/파일 구조를 자동으로 생성하는 Prompt 설계

### 🎯 기대 출력 예시
```
project-root/
|— docker-compose.yml
|— api-server/
|   |— src/
|       |— app.module.ts
|       |— image.controller.ts
|       |— image.service.ts
|— worker/
|   |— src/
|       |— app.module.ts
|       |— queue.processor.ts
|       |— image.processor.service.ts
|— prometheus/
|   |— prometheus.yml
|— grafana/
|   |— provisioning/
|       |— dashboards/
|       |— datasources/
```

---

## 4. 필요한 인프라 자원 정리 Prompt 실습

### 📝 과제 목표
- 아키텍처에 필요한 인프라 자원을 표 형태로 정리하는 Prompt 설계

### 🎯 기대 출력 예시
| 자원 | 설명 |
|----------|----------|
| AWS S3 | 이미지 업로드 및 저장 |
| Kafka / Redis | 비동기 작업 큐 |
| Prometheus | 메트릭 수집 및 모니터링 |
| Grafana | 대시보드 시각화 |
| Docker Compose | 로컬 개발 및 배포 관리 |

---

## 5. 선택지별 비용 분석 Prompt 실습

### 📝 과제 목표
- 선택 가능한 기술들의 평균 비용과 특징을 요약하는 Prompt 설계

### 🎯 기대 출력 예시
| 선택지 | 평균 비용 | 특징 |
|-------------|-------------|-------------|
| Kafka | EC2 t3.medium 무료 티어 사용 가능, 고성능 통신 | 고성능, 확장성 뛰어남 |
| Redis | ElastiCache 약 $20/월 | 빠른 처리 속도, 메모리 기반 |
| S3 | 약 $0.023/GB 저장 | 파일 스토리지 표준 |
| Prometheus + Grafana | EC2 t2.micro 무료 | 오픈소스, 확장성 우수 |

---

## ✅ 결론: 프롬프트 설계 연습 로드맵

1. **요구사항 표 정리 Prompt 만들기**
2. **시스템 아키텍처 다이어그램 Prompt 만들기**
3. **폴더 구조 생성 Prompt 만들기**
4. **필요 자원 정리 Prompt 만들기**
5. **비용 분석 Prompt 만들기**

각 연습 후 실제로 LLM 에 적용하고, 출력 결과를 다듬어보세요! ✍️
