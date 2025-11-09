<div align="center">

# 🌩️ 2025 소프트뱅크 해커톤
### **“클라우드로 미래를 만들다”**

---

## 🏁 Final Submission
### **アーキテクチャテーマ: “Blue-Green Deployment Playground”**
**Fun, Fast, and Reliable Deployment**

</div>

---

<div align="center">

## 🧩 Architecture Overview

</div>

> Terraform 기반 IaC를 통해
> **ASG Blue-Green 무중단 배포**, **VPC 네트워킹**, **CI/CD 자동화**, **Observability 구축**을 수행.
>
> 전체 인프라는 **AWS Well-Architected Framework 6대 원칙**
> (운영 우수성, 보안, 신뢰성, 성능 효율, 비용 최적화, 지속 가능성)에 기반해 설계.

---

<div align="center">

## 🎯 왜 이 테마를 선택했는가?
### *なぜこのテーマを選んだのか？*

</div>

> “배포 과정을 스트레스가 아닌 즐거운 경험으로 전환하자.”

- **시간 효율화**: 전체 CI/CD를 항상 실행하지 않고 필요한 Step만 선택해 배포 시간 단축
- **Fun-to-Deploy**: 대시보드 시각화·애니메이션·BGM으로 배포를 이벤트화
- **Slack 통합 제어**: Slash Command로 워크플로우별 유연한 배포 관리
- **실시간 피드백**: 배포 상태를 시각화하고 Slack 알림으로 즉각 확인

> 반복적인 배포 과정을 **“보는 재미와 안정성이 공존하는 경험”**으로 재구성.

---

<div align="center">

## ⚙️ 기술 스택

### 🖥️ Frontend
`React` `JavaScript` `TailwindCSS`

---

### ⚙️ Backend
`Node.js` `Spring Boot (JDK 17)` `Python`

---

### 🗄️ Database
`DynamoDB` `ElastiCache for Redis`

---

### 🧪 Test
`JUnit` `Spring-Test` `JaCoCo`

---

### ☁️ Infrastructure
`AWS` `Terraform`

---

### 🔄 CI/CD
`GitHub Actions` `CodePipeline` `CodeBuild` `CodeDeploy` `Lambda` `ECR`

---

### 📈 Monitoring / Observability
`CloudWatch` `Slack Bot API`

---

### 🐳 Container
`Docker`

</div>

---

<div align="center">

## ☁️ 인프라 구성 개요

<p>
<img width="900" alt="Cloud Architecture" src="https://github.com/user-attachments/assets/2ef69f6b-d853-4ced-9cbc-e368f9d8ff46" />
</p>

</div>

✅ **CloudFront + S3**로 정적 리소스 배포
✅ **WAF + ALB**를 통한 HTTPS 트래픽 보호
✅ **멀티 AZ Blue/Green ASG**로 고가용성 확보
✅ **Redis Pub/Sub**으로 실시간 메시징
✅ **DynamoDB**로 메시지 로그 관리 및 확장성 확보
✅ **CloudWatch** 기반 모니터링 및 알림 시스템

---

<div align="center">

## 🔧 CI 파이프라인 구조

<p>
<img width="1200" alt="CI Pipeline" src="https://github.com/user-attachments/assets/5ed05219-2544-4604-9a63-de573c2eee00" />
</p>

> GitHub → CodePipeline → CodeBuild → CodeDeploy → EC2 (Blue/Green)

</div>

1.  **Source**: GitHub에서 소스 아티팩트 생성
2.  **Test (Optional)**: 단위 테스트 수행
3.  **Build**: `.jar` 빌드 및 ECR 업로드
4.  **Deploy**: CodeDeploy가 ASG를 관리하며 헬스체크 후 트래픽 전환

---

<div align="center">

## 💬 Slack 연동 워크플로우

</div>

- Slash Command 기반 배포 제어
- 커밋 메시지 `deploy: auto` 시 자동 트리거
- Slack 알림 내 `Go to Dashboard` 버튼으로 이동

<p align="center">
<img width="1200" alt="Slack CI Options" src="https://github.com/user-attachments/assets/25260920-86fb-43aa-9309-f24d73be48e0" />
</p>
<p align="center">
<img width="1400" alt="Slack Notification" src="https://github.com/user-attachments/assets/3c9102a5-d48f-4a2e-935a-a2464229efc7" />
</p>

---

<div align="center">

## 🚀 CD (Blue/Green Deployment)

<p>
<img width="800" alt="CD Diagram" src="https://github.com/user-attachments/assets/3bd8f6fe-7f11-4d70-98b8-1798c3036999" />
</p>

</div>

- Blue ASG 유지, Green ASG 신규 생성
- CodeDeploy Agent가 ECR 이미지 가져와 배포
- 모든 인스턴스 헬스체크 통과 후 ALB 트래픽 전환
- 일정 시간 안정화 후 Blue 종료 (Rollback 대비)

<p align="center">
<img width="1000" alt="Deploy Status 1" src="https://github.com/user-attachments/assets/172e54b3-5683-41bc-b1b3-de659aa84802" />
</p>
<p align="center">
<img width="1000" alt="Deploy Status 2" src="https://github.com/user-attachments/assets/6dcb5db2-b838-4b2c-9487-6afb1829073b" />
</p>

---

<div align="center">

## 🧪 부하 테스트 결과

| 항목 | 결과 |
|:---:|:---:|
| 테스트 인원 | 100명 |
| RPS | 10 × (1…3) |
| 평균 응답 시간 | 60ms |
| 최대 응답 시간 | 400ms |

<br>

<p>
<img width="1000" alt="Load Test Process" src="https://github.com/user-attachments/assets/cd9e3172-74a3-496b-85cf-72ade5660f20" />
</p>
<p>
<img width="600" alt="Load Test Result" src="https://github.com/user-attachments/assets/5970165f-b3a3-41ed-94cb-748bf6518d01" />
</p>

</div>

---

<div align="center">

## 📊 Observability

</div>

- CloudWatch Logs / Metrics로 EC2 로그, CPU 사용률, 메모리 모니터링
- Lambda 기반 Slack 알림 전송
- WebSocket을 통해 실시간 대시보드 업데이트

<p align="center">
<img width="800" alt="Observability" src="https://github.com/user-attachments/assets/4287b2f4-1844-4d0b-bcd7-8bbb20197430" />
</p>

---

<div align="center">

## 🖥️ 대시보드 구성

</div>

- **Frontend**: React + TailwindCSS + WebSocket
- **기능**: CI/CD 단계별 상태 실시간 표시
- **배포 구조**:
  - S3 정적 웹 호스팅 → CloudFront → Route53
  - Slack Lambda 함수에 CloudFront 도메인 전달
  - Slack 버튼 클릭 시 대시보드로 이동

<p align="center">
<img width="400" alt="Dashboard Open" src="https://github.com/user-attachments/assets/7b3fd80b-19d2-4bbd-8afe-82ab2b089996" />
</p>

---

<div align="center">

## 🧠 프로젝트 요약

</div>

- IaC 기반 자동화된 클라우드 운영
- ASG Blue-Green 배포로 무중단 서비스 구현
- Slack 통합형 CI/CD로 협업 효율 향상
- 대시보드 실시간 모니터링 및 피드백 루프 완성
- AWS Well-Architected 6대 원칙 준수

---

<div align="center">

## 📅 프로젝트 정보

| 구분 | 내용 |
|:---:|:---|
| 팀명 | CloudWave |
| 행사 | SoftBank Hackathon 2025 |
| 주제 | Fun-to-Deploy: 즐거운 배포 경험 구현 |
| 기간 | 2025.10 ~ 2025.11 |
| 주요 기술 | AWS, Terraform, Slack API, React, CI/CD, Blue-Green Deploy |

</div>
