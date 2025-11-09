# 2025 소프트뱅크 해커톤 – 클라우드로 미래를 만들다  
## Final Submission: *Blue-Green Deployment Playground*

---

## 🧩 Architecture Overview

Terraform 기반 IaC로  
**ASG Blue-Green 무중단 배포**, **VPC 네트워킹**, **CI/CD 자동화**, **Observability** 구성.  

전체 인프라는 **AWS Well-Architected Framework 6대 원칙**  
(운영 우수성, 보안, 신뢰성, 성능 효율, 비용 최적화, 지속 가능성)에 기반해 설계.

---

## 🎯 테마 선정 배경  
### *なぜこのテーマを選んだのか？*

> “배포 과정을 스트레스가 아닌 즐거운 경험으로 바꾸자.”

- **시간 효율화**: 전체 CI/CD 대신 필요한 Step만 실행해 배포 시간 단축  
- **Fun-to-Deploy**: 배포 과정을 대시보드 시각화·애니메이션·BGM으로 이벤트화  
- **Slack 통합 제어**: Slash Command 기반으로 워크플로우별 배포 제어  
- **실시간 피드백**: 대시보드와 Slack 알림으로 배포 상태를 시각적·즉각적으로 확인  

> 반복되는 배포를 하나의 이벤트처럼 설계.  
> **보는 재미와 안정성이 공존하는 배포 경험**을 목표로 함.

---

## ⚙️ 기술 스택

<div align="left">

### 🖥️ Frontend
<span style="background-color:#1f2937;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">React</span>
<span style="background-color:#2563eb;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">JavaScript</span>
<span style="background-color:#06b6d4;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">TailwindCSS</span>

---

### ⚙️ Backend
<span style="background-color:#4b5563;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Node.js</span>
<span style="background-color:#f97316;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Spring Boot (JDK 17)</span>
<span style="background-color:#2d3748;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Python</span>

---

### 🗄️ Database
<span style="background-color:#facc15;color:#000;padding:4px 8px;border-radius:6px;font-weight:600;">DynamoDB</span>
<span style="background-color:#dc2626;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">ElastiCache for Redis</span>

---

### 🧪 Test
<span style="background-color:#10b981;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">JUnit</span>
<span style="background-color:#059669;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Spring-Test</span>
<span style="background-color:#047857;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">JaCoCo</span>

---

### ☁️ Infrastructure
<span style="background-color:#2563eb;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">AWS</span>
<span style="background-color:#9333ea;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Terraform</span>

---

### 🔄 CI/CD
<span style="background-color:#1e40af;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">GitHub Actions</span>
<span style="background-color:#facc15;color:#000;padding:4px 8px;border-radius:6px;font-weight:600;">CodePipeline</span>
<span style="background-color:#f59e0b;color:#000;padding:4px 8px;border-radius:6px;font-weight:600;">CodeBuild</span>
<span style="background-color:#f43f5e;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">CodeDeploy</span>
<span style="background-color:#0891b2;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Lambda</span>
<span style="background-color:#eab308;color:#000;padding:4px 8px;border-radius:6px;font-weight:600;">ECR</span>

---

### 📈 Monitoring / Observability
<span style="background-color:#047857;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">CloudWatch</span>
<span style="background-color:#111827;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Slack Bot API</span>

---

### 🐳 Container
<span style="background-color:#0ea5e9;color:#fff;padding:4px 8px;border-radius:6px;font-weight:600;">Docker</span>

</div>

---

## ☁️ 인프라 구성 개요

<p align="center">
  <img width="900" alt="Cloud Architecture" src="https://github.com/user-attachments/assets/2ef69f6b-d853-4ced-9cbc-e368f9d8ff46" />
</p>

- **CloudFront + S3**: 정적 리소스 배포  
- **WAF + ALB**: HTTPS 보호 및 접근 제어  
- **멀티 AZ 이중화**: Blue/Green ASG 기반 고가용성 확보  
- **Redis (Pub/Sub)**: 실시간 메시지 송수신 처리  
- **DynamoDB**: 메시지 로그 저장 및 확장성 확보  
- **CloudWatch**: 전체 파이프라인 상태 모니터링  
- **Slack 연동형 CI/CD**: 워크플로우 제어 및 실시간 배포 알림 제공  

---

## 🔧 CI 파이프라인 구조

<p align="center">
  <img width="1200" alt="CI Pipeline" src="https://github.com/user-attachments/assets/5ed05219-2544-4604-9a63-de573c2eee00" />
</p>

> GitHub → CodePipeline → CodeBuild → CodeDeploy → EC2 (Blue/Green)

### 주요 단계
1. **Source**: GitHub에서 소스 가져와 아티팩트 생성  
2. **Test (Optional)**: 단위 테스트 및 코드 검증 수행  
3. **Build**: `.jar` 빌드 및 ECR 업로드  
4. **Deploy**: CodeDeploy가 Blue/Green ASG를 관리하며 헬스체크 후 트래픽 전환  

---

## 💬 Slack 연동 워크플로우

- **배포 제어**: Slack Slash Command로 각 워크플로우 실행  
- **자동 트리거**: 커밋 메시지에 `deploy: auto` 포함 시 파이프라인 자동 실행  
- **대시보드 연동**: Slack 알림에 `Go to Dashboard` 버튼 제공  

<p align="center">
  <img width="1200" alt="Slack CI Options" src="https://github.com/user-attachments/assets/25260920-86fb-43aa-9309-f24d73be48e0" />
</p>

<p align="center">
  <img width="1400" alt="Slack Notification" src="https://github.com/user-attachments/assets/3c9102a5-d48f-4a2e-935a-a2464229efc7" />
</p>

---

## 🚀 CD (Blue/Green Deployment)

<p align="center">
  <img width="800" alt="CD Diagram" src="https://github.com/user-attachments/assets/3bd8f6fe-7f11-4d70-98b8-1798c3036999" />
</p>

- **배포 절차**
  1. CodePipeline → CodeDeploy로 전달  
  2. Blue ASG 유지, Green ASG 신규 생성  
  3. CodeDeploy Agent가 ECR에서 최신 이미지를 가져와 배포  
  4. 모든 인스턴스가 헬스체크 통과 시 ALB 트래픽 전환  
  5. 일정 시간 안정화 후 Blue 종료 (Rollback 대비)

<p align="center">
  <img width="1000" alt="Deploy Status 1" src="https://github.com/user-attachments/assets/172e54b3-5683-41bc-b1b3-de659aa84802" />
</p>

<p align="center">
  <img width="1000" alt="Deploy Status 2" src="https://github.com/user-attachments/assets/6dcb5db2-b838-4b2c-9487-6afb1829073b" />
</p>

---

## 🧪 부하 테스트

| 항목 | 결과 |
|------|------|
| 테스트 인원 | 100명 |
| RPS | 10 × (1…3) |
| 평균 응답 시간 | 60ms |
| 최대 응답 시간 | 400ms |

<p align="center">
  <img width="1000" alt="Load Test Process" src="https://github.com/user-attachments/assets/cd9e3172-74a3-496b-85cf-72ade5660f20" />
</p>

<p align="center">
  <img width="600" alt="Load Test Result" src="https://github.com/user-attachments/assets/5970165f-b3a3-41ed-94cb-748bf6518d01" />
</p>

---

## 📊 Observability

- **CloudWatch Logs / Metrics**: EC2 로그, CPU 사용률, 메모리 모니터링  
- **멀티 AZ 평균 CPU 사용률 시각화**  
- **Lambda 기반 Slack 알림 연동**  
- **배포 상태 및 성능 지표를 WebSocket으로 대시보드에 전달**  

<p align="center">
  <img width="800" alt="Observability" src="https://github.com/user-attachments/assets/4287b2f4-1844-4d0b-bcd7-8bbb20197430" />
</p>

---

## 🖥️ 대시보드

- **Frontend**: React + TailwindCSS + WebSocket  
- **기능**: 배포 단계별 상태 표시 및 Slack 연동 로그 출력  
- **배포 구조**:  
  - S3 정적 호스팅 → CloudFront → Route53 서브도메인 연결  
  - CloudFront 배포 도메인을 Slack Lambda에 전달  
  - Slack 버튼 클릭 시 대시보드로 이동  

<p align="center">
  <img width="400" alt="Dashboard Open" src="https://github.com/user-attachments/assets/7b3fd80b-19d2-4bbd-8afe-82ab2b089996" />
</p>

---

## 🧠 프로젝트 요약

- IaC 기반 자동화된 클라우드 운영 환경  
- ASG Blue-Green 배포로 무중단 서비스 제공  
- Slack 통합형 CI/CD 파이프라인으로 협업 효율 극대화  
- 대시보드 실시간 시각화 및 피드백 루프 구현  
- AWS Well-Architected 6대 원칙 기반 구조 설계  

---

## 📅 프로젝트 정보

| 구분 | 내용 |
|------|------|
| 팀명 | CloudWave |
| 행사 | SoftBank Hackathon 2025 |
| 주제 | Fun-to-Deploy: 즐거운 배포 경험 구현 |
| 기간 | 2025.10 ~ 2025.11 |
| 주요 기술 | AWS, Terraform, Slack API, React, CI/CD, Blue-Green Deploy |

---

## 📚 Repository 구조
.
├── frontend/ # React 대시보드
├── backend/ # Node.js & Spring Boot API 서버
├── terraform/ # IaC 구성 (VPC, ALB, EC2, ECR 등)
├── lambda/ # Slack 알림 및 자동화 함수
├── .github/workflows/ # CI/CD Workflow 정의
└── docs/ # 아키텍처 다이어그램, 테스트 결과 문서
---

### Made by **Orange Team**  
SoftBank Hackathon 2025 | AWS × Terraform × Slack × CI/CD
