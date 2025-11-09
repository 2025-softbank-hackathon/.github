<div align="center">

# 🌩️ 2025 소프트뱅크 해커톤  
### **“클라우드로 미래를 만들다”**

---

## 🏁 최종 발표  
### **アーキテクチャテーマ: “Blue-Green Deployment Playground”**  
**Fun, Fast, and Reliable Deployment**

</div>

---

<div align="center">

## Architecture Overview

> **Terraform 기반 IaC**를 통해  
> **ASG Blue-Green 무중단 배포**, **VPC 네트워킹**, **CI/CD 자동화**, **Observability 구축**을 구현했습니다.  
>  
> 모든 구성은 **AWS Well-Architected Framework 6대 원칙**  
> (운영 우수성, 보안, 신뢰성, 성능 효율, 비용 최적화, 지속 가능성)에 맞춰 설계되었습니다.

---

## 왜 이 테마를 선택했는가?  
### *なぜこのテーマを選んだのか？*

> “배포 과정을 스트레스가 아닌 즐거운 경험으로 만들자.”

- **시간 효율화:** 전체 CI/CD를 항상 수행하는 대신  
  필요한 Step만 선택해 빠른 배포 가능  
- **Fun-to-Deploy:** 단조로운 절차 대신  
  대시보드 시각화와 애니메이션, BGM으로 흥미 유발  
- **Slack 통합 제어:** Slash Command를 통해  
  워크플로우별 유연한 배포 관리  
- **실시간 피드백:** 배포 현황을 시각화하고  
  Slack 알림으로 실시간 피드백 제공  

> 반복되는 배포를 이벤트처럼 —  
> **“보는 재미와 안정성이 공존하는 배포 경험”** 을 목표로 했습니다.


---

<p align="center">
  <img width="750" alt="Chat Service Screenshot" src="https://github.com/user-attachments/assets/c092d1fa-7970-4339-a0ab-76cb129ef7b0" />
</p>

<p align="center">
  <img width="1000" alt="Service Flow" src="https://github.com/user-attachments/assets/647ac935-7678-4b67-b626-5f08ff5abaf9" />
</p>

---

<div align="center">

## ⚙️ 기술 스택

</div>

<table align="center">
  <tr>
    <td align="center"><b>Frontend</b></td>
    <td>React, JavaScript, TailwindCSS</td>
  </tr>
  <tr>
    <td align="center"><b>Backend</b></td>
    <td>Node.js, Spring Boot (JDK 17), Python</td>
  </tr>
  <tr>
    <td align="center"><b>Database</b></td>
    <td>DynamoDB, ElastiCache for Redis</td>
  </tr>
  <tr>
    <td align="center"><b>Test</b></td>
    <td>JUnit, Spring-Test, JaCoCo</td>
  </tr>
  <tr>
    <td align="center"><b>Infra</b></td>
    <td>AWS, Terraform</td>
  </tr>
  <tr>
    <td align="center"><b>CI/CD</b></td>
    <td>GitHub Actions, CodePipeline, CodeBuild, CodeDeploy, Lambda, ECR</td>
  </tr>
  <tr>
    <td align="center"><b>Monitoring</b></td>
    <td>CloudWatch, Slack Bot API</td>
  </tr>
  <tr>
    <td align="center"><b>Container</b></td>
    <td>Docker</td>
  </tr>
</table>

---

<p align="center">
  <img width="1000" alt="Cloud Architecture" src="https://github.com/user-attachments/assets/2ef69f6b-d853-4ced-9cbc-e368f9d8ff46" />
</p>

✅ **CloudFront + S3**로 정적 리소스 배포  
✅ **WAF + ALB**로 보호된 HTTPS 환경 구성  
✅ **멀티 AZ 기반 Blue/Green 배포**로 고가용성 확보  
✅ **Slack 연동형 CI/CD 파이프라인**으로 유연한 배포 제어  
✅ **Redis Pub/Sub**으로 실시간 메시지 송수신  
✅ **DynamoDB**로 로그 저장 및 확장성 확보  
✅ **CloudWatch Observability**로 파이프라인 모니터링

---

<div align="center">

## CI 파이프라인

</div>

<p align="center">
  <img width="1200" alt="CI Pipeline" src="https://github.com/user-attachments/assets/5ed05219-2544-4604-9a63-de573c2eee00" />
</p>

> GitHub(prod) → CodePipeline → CodeBuild → CodeDeploy → EC2 (Blue/Green)

**Workflow 단계**
1. **Source** — GitHub 소스 → Artifact 생성  
2. **Test (Optional)** — Source 단계 아티팩트 테스트  
3. **Build** — .jar 생성 → ECR 업로드  
4. **Deploy** — CodeDeploy → ASG Blue/Green 전환 (헬스체크 후 트래픽 전환)

---

### Slack 연동 & 개인화된 배포 제어

- Slack Slash Command로 Workflow 선택  
- `deploy: auto` 커밋 시 자동 트리거  
- Slack 알림에 `Go to Dashboard` 버튼 제공  

<p align="center">
  <img width="1200" alt="Slack CI Options" src="https://github.com/user-attachments/assets/25260920-86fb-43aa-9309-f24d73be48e0" />
</p>

<p align="center">
  <img width="1400" alt="Slack Notification" src="https://github.com/user-attachments/assets/3c9102a5-d48f-4a2e-935a-a2464229efc7" />
</p>

<p align="center">
  <img width="600" alt="Deploy Ready" src="https://github.com/user-attachments/assets/569c0936-52ad-48f6-8459-da4c1dafff74" />
</p>

---

<div align="center">

## 부하 테스트 결과

</div>

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

<div align="center">

## CD (Blue/Green Deployment)

</div>

- CodePipeline → CodeDeploy로 전달  
- 기존 **Blue ASG** 유지 → **Green ASG** 생성  
- Health Check 통과 시 **ALB 트래픽 전환 (All-at-once)**  
- Green 안정화 후 Blue 종료 (롤백 대비 일시 유지)

<p align="center">
  <img width="800" alt="CD Diagram" src="https://github.com/user-attachments/assets/3bd8f6fe-7f11-4d70-98b8-1798c3036999" />
</p>

<p align="center">
  <img width="1000" alt="Deploy Status 1" src="https://github.com/user-attachments/assets/172e54b3-5683-41bc-b1b3-de659aa84802" />
</p>

<p align="center">
  <img width="1000" alt="Deploy Status 2" src="https://github.com/user-attachments/assets/6dcb5db2-b838-4b2c-9487-6afb1829073b" />
</p>

---

<div align="center">

## Observability & Dashboard

</div>

**CloudWatch**
- EC2 로그 및 CPU 사용률 실시간 모니터링  
- 멀티 AZ 평균 CPU 그래프 제공  

**대시보드 개발**
- React + Tailwind + WebSocket 실시간 통신  
- 각 단계별 상태를 API & WebSocket으로 표시  

**배포**
- S3 정적 호스팅 → CloudFront 배포 → Route53 서브도메인 연결  
- Slack 알림 버튼으로 바로 대시보드 접근  

<p align="center">
  <img width="800" alt="Observability" src="https://github.com/user-attachments/assets/4287b2f4-1844-4d0b-bcd7-8bbb20197430" />
</p>

<p align="center">
  <img width="400" alt="Dashboard Open" src="https://github.com/user-attachments/assets/7b3fd80b-19d2-4bbd-8afe-82ab2b089996" />
</p>

---

<div align="center">

### Made with passion by  
**SoftBank Hackathon Team – “CloudWave”** ☁️  
**2025.11 | AWS × Terraform × Slack × Fun-to-Deploy**

</div>

