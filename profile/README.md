<!-- 중앙 카드 컨테이너 -->
<div align="center">
  <table width="100%" style="max-width:1100px;margin:0 auto;border:1px solid #444;border-radius:14px;padding:28px;box-shadow:0 4px 14px rgba(0,0,0,0.12);">
    <tr><td>

      <!-- 헤더 -->
      <div align="center" style="margin-bottom:24px">
        <h1 style="margin:0">🌩️ 2025 소프트뱅크 해커톤</h1>
        <blockquote style="margin:12px 0 0 0">“클라우드로 미래를 만들다”</blockquote>
      </div>

      <!-- 배지 묶음 -->
      <div align="center" style="margin:18px 0">
        <p>
          <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
          <img src="https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white" />
          <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white" />
        </p>
        <p>
          <img src="https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white" />
          <img src="https://img.shields.io/badge/Spring Boot-6DB33F?logo=springboot&logoColor=white" />
          <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" />
          <img src="https://img.shields.io/badge/Amazon DynamoDB-4053D6?logo=amazondynamodb&logoColor=white" />
          <img src="https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white" />
        </p>
        <p>
          <img src="https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black" />
          <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" />
          <img src="https://img.shields.io/badge/Tailwind CSS-06B6D4?logo=tailwindcss&logoColor=white" />
        </p>
        <p>
          <img src="https://img.shields.io/badge/GitHub Actions-2088FF?logo=githubactions&logoColor=white" />
          <img src="https://img.shields.io/badge/AWS CodePipeline-527FFF?logo=awscodepipeline&logoColor=white" />
          <img src="https://img.shields.io/badge/AWS CodeBuild-FF9900?logo=awscodebuild&logoColor=white" />
          <img src="https://img.shields.io/badge/AWS CodeDeploy-FF9900?logo=awscodedeploy&logoColor=white" />
          <img src="https://img.shields.io/badge/AWS Lambda-FF9900?logo=awslambda&logoColor=white" />
        </p>
        <p>
          <img src="https://img.shields.io/badge/Amazon CloudWatch-FF4F8B?logo=amazoncloudwatch&logoColor=white" />
          <img src="https://img.shields.io/badge/Slack-4A154B?logo=slack&logoColor=white" />
          <img src="https://img.shields.io/badge/JUnit5-25A162?logo=junit5&logoColor=white" />
          <img src="https://img.shields.io/badge/JaCoCo-D82623?logo=jacoco&logoColor=white" />
        </p>
      </div>

      <hr style="border:none;border-top:1px solid #444;margin:20px 0" />

      <h3 align="center">SoftBank Hackathon 2025 | 팀 <code>Orange</code></h3>

      <!-- 섹션 카드: 왜 이 테마인가 -->
      <table align="center" width="95%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="left">
          <h2 align="center" style="margin-top:4px">🎯 왜 이 테마를 선택했는가?</h2>
          <h3 align="center" style="margin-top:-8px"><em>なぜこのテーマを選んだのか？</em></h3>

          <blockquote style="margin:8px auto">“배포 과정을 스트레스가 아닌 즐거운 경험으로 전환하자.”</blockquote>

          ✅ 시간 효율화: 전체 CI/CD를 항상 실행하지 않고 필요한 Step만 선택해 배포 시간 단축<br/>
          ✅ Fun-to-Deploy: 대시보드 시각화, 애니메이션, BGM으로 배포를 이벤트화<br/>
          ✅ Slack 통합 제어: Slash Command로 워크플로우별 유연한 배포 관리<br/>
          ✅ 실시간 피드백: 배포 상태를 시각화하고 Slack 알림으로 즉각 확인<br/>

          <blockquote style="margin:8px auto">반복적인 배포 과정을 “보는 재미와 안정성이 공존하는 경험”으로 재구성</blockquote>
        </td></tr>
      </table>

      <!-- 섹션 카드: 아키텍처 -->
      <table align="center" width="95%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="center">
          <h2 style="margin-top:4px">🏗️ 아키텍처</h2>
          <h3 style="margin-top:-8px">Architecture Overview</h3>

          <p style="max-width:900px;margin:10px auto">
            Terraform 기반 IaC로 ASG Blue Green 무중단 배포, VPC 네트워킹, CI/CD 자동화, Observability 구축을 수행<br/>
            전체 인프라는 AWS Well Architected Framework 6대 원칙(운영 우수성, 보안, 신뢰성, 성능 효율, 비용 최적화, 지속 가능성)에 기반해 설계
          </p>

          <p>
            <img width="850" style="max-width:100%;height:auto" alt="Cloud Architecture"
                 src="https://github.com/user-attachments/assets/2ef69f6b-d853-4ced-9cbc-e368f9d8ff46" />
          </p>

          <table align="center" style="border:1px solid #444;border-radius:10px;padding:12px;margin:8px auto;">
            <tr><td align="left">
              ✅ CloudFront + S3 정적 리소스 배포<br/>
              ✅ WAF + ALB 통한 HTTPS 트래픽 보호<br/>
              ✅ 멀티 AZ Blue Green ASG로 고가용성 확보<br/>
              ✅ Redis Pub/Sub으로 실시간 메시징<br/>
              ✅ DynamoDB로 로그 관리 및 확장성 확보<br/>
              ✅ CloudWatch 기반 모니터링과 알림 시스템<br/>
            </td></tr>
          </table>
        </td></tr>
      </table>

      <!-- 섹션 카드: CI/CD -->
      <table align="center" width="95%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="center">
          <h2 style="margin-top:4px">🚀 CI/CD & Blue/Green Deployment</h2>

          <p>
            <img width="1100" style="max-width:100%;height:auto" alt="CI Pipeline"
                 src="https://github.com/user-attachments/assets/5ed05219-2544-4604-9a63-de573c2eee00" />
          </p>

          <p><strong>GitHub → CodePipeline → CodeBuild → CodeDeploy → EC2 (Blue Green)</strong></p>

          <div align="left" style="max-width:900px;margin:0 auto;text-align:left">
            1️⃣ Source: GitHub에서 소스 아티팩트 생성<br/>
            2️⃣ Test(선택): 단위 테스트 수행<br/>
            3️⃣ Build: <code>.jar</code> 빌드와 ECR 업로드<br/>
            4️⃣ Deploy: CodeDeploy가 ASG를 관리하며 헬스체크 후 트래픽 전환<br/>
          </div>

          <p>
            <img width="800" style="max-width:100%;height:auto" alt="CD Diagram"
                 src="https://github.com/user-attachments/assets/3bd8f6fe-7f11-4d70-98b8-1798c3036999" />
          </p>

          <div align="left" style="max-width:900px;margin:0 auto;text-align:left">
            — Blue ASG 유지, Green ASG 신규 생성<br/>
            — CodeDeploy Agent가 ECR 이미지 가져와 배포<br/>
            — 모든 인스턴스 헬스체크 통과 후 ALB 트래픽 전환<br/>
            — 일정 시간 안정화 후 Blue 종료(롤백 대비)<br/>
          </div>
        </td></tr>
      </table>

      <!-- 섹션 카드: Slack -->
      <table align="center" width="95%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="center">
          <h2 style="margin-top:4px">💬 Slack 연동 워크플로우</h2>

          <div align="left" style="max-width:900px;margin:0 auto;text-align:left">
            — Slash Command 기반 배포 제어<br/>
            — 커밋 메시지 <code>deploy: auto</code> 시 자동 트리거<br/>
            — Slack 알림의 <em>Go to Dashboard</em> 버튼으로 대시보드 이동<br/>
          </div>

          <p>
            <img width="1100" style="max-width:100%;height:auto" alt="Slack CI Options"
                 src="https://github.com/user-attachments/assets/25260920-86fb-43aa-9309-f24d73be48e0" />
          </p>
          <p>
            <img width="1200" style="max-width:100%;height:auto" alt="Slack Notification"
                 src="https://github.com/user-attachments/assets/3c9102a5-d48f-4a2e-935a-a2464229efc7" />
          </p>
        </td></tr>
      </table>

      <!-- 섹션 카드: Observability -->
      <table align="center" width="95%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="center">
          <h2 style="margin-top:4px">📊 Observability Dashboard</h2>

          <div align="left" style="max-width:900px;margin:0 auto;text-align:left">
            — CloudWatch Logs, Metrics로 EC2 로그, CPU, 메모리 모니터링<br/>
            — Lambda를 통한 Slack 알림 전송<br/>
            — WebSocket으로 실시간 대시보드 업데이트<br/>
          </div>

          <p>
            <img width="850" style="max-width:100%;height:auto" alt="Observability"
                 src="https://github.com/user-attachments/assets/4287b2f4-1844-4d0b-bcd7-8bbb20197430" />
          </p>
        </td></tr>
      </table>

      <!-- 섹션 카드: 부하 테스트 -->
      <table align="center" width="80%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="center">
          <h2 style="margin-top:4px">📈 부하 테스트 결과</h2>

          <table>
            <tr><td><strong>항목</strong></td><td><strong>결과</strong></td></tr>
            <tr><td>테스트 인원</td><td>100명</td></tr>
            <tr><td>RPS</td><td>10 × (1…3)</td></tr>
            <tr><td>평균 응답 시간</td><td>60ms</td></tr>
            <tr><td>최대 응답 시간</td><td>400ms</td></tr>
          </table>

          <p>
            <img width="700" style="max-width:100%;height:auto" alt="Load Test Result"
                 src="https://github.com/user-attachments/assets/5970165f-b3a3-41ed-94cb-748bf6518d01" />
          </p>
        </td></tr>
      </table>

      <!-- 섹션 카드: 핵심 성과 -->
      <table align="center" width="95%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="center">
          <h2 style="margin-top:4px">📊 핵심 성과</h2>

          <table>
            <tr><td align="center"><strong>영역</strong></td><td><strong>성과</strong></td></tr>
            <tr><td align="center"><strong>배포 안정성</strong></td><td>ASG Blue Green 배포로 무중단 서비스 구현</td></tr>
            <tr><td align="center"><strong>응답 성능</strong></td><td>부하 테스트 통과(평균 60ms, 최대 400ms)</td></tr>
            <tr><td align="center"><strong>협업 효율</strong></td><td>Slack 통합 CI/CD로 배포 리드타임 단축</td></tr>
            <tr><td align="center"><strong>관측 가능성</strong></td><td>실시간 대시보드와 피드백 루프 완성</td></tr>
          </table>
        </td></tr>
      </table>

      <!-- 섹션 카드: 프로젝트 정보 -->
      <table align="center" width="75%" style="border:1px solid #444;border-radius:12px;padding:18px;margin:16px auto;">
        <tr><td align="center">
          <h2 style="margin-top:4px">📅 프로젝트 정보</h2>

          <table>
            <tr><td align="center"><strong>구분</strong></td><td><strong>내용</strong></td></tr>
            <tr><td align="center">팀명</td><td><code>ORANGE</code></td></tr>
            <tr><td align="center">행사</td><td>SoftBank Hackathon 2025</td></tr>
            <tr><td align="center">주제</td><td>Fun to Deploy, 즐거운 배포 경험 구현</td></tr>
            <tr><td align="center">기간</td><td>2025.10 ~ 2025.11</td></tr>
          </table>
        </td></tr>
      </table>

    </td></tr>
  </table>
</div>
