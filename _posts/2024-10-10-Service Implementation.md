---
layout: post
title: Service Implementation 
categories: Memo
tags: [SE study]
---

# Service Implementation

## 서버 서비스 배포 방식

### **무중단 배포**

- 서비스 장애와 배포의 부담을 최소화
- 운영 중인 서비스를 중단하지 않고 신규 소프트웨어를 배포하는 기술

![image.png](/assets/images/Service/image.png)

### **롤링 배포(Rolling Deployment)**

- 무중단 배포의 가장 기본적인 방식
- 사용 중인 인스턴스 내에서 새 버전을 점진적으로 교체
    - 서비스 중인 인스턴스 하나를 로드밸런서에서 라우팅하지 않도록 한 뒤, 새 버전을 적용하여 다시 라우팅 하도록 하는 과정을 반복 → 모든 인스턴스에 새 버전의 어플리케이션을 배포
    - 인스턴스마다 차례로 배포를 진행하기 때문에 손쉽게 롤백이 가능
    - 구버전과 신버전이 공존하기 때문에 호환성 문제 발생 가능

![image1.png](/assets/images/Service/image1.png)

### **블루-그린 배포(Blue-Green Deployment)**

- 블루를 구버전, 그린을 신버전으로 지칭하여 붙여진 이름
- 운영 환경에 구버전과 동일하게 신버전의 인스턴스를 구성한 후, 로드밸런서를 통해 신버전으로 모든 트래픽을 전환하는 배포 방식
    - 구버전과 동일한 환경으로 인스턴스를 구성하기 때문에 실제 서비스 환경에서 신버전을 미리 테스트할 수 있고, 빠른 롤백이 가능
    - 배포가 완료된 후 남아 있는 구버전의 환경을 다음 배포에 재사용 가능
    - 시스템 자원이 두 배로 필요함

![image2.png](/assets/images/Service/image2.png)

### **카나리 배포(Canary Deployment)**

- 옛날 광부들이 카나리아 새를 이용해 가스 누출 위험을 감지한 것에서 유래, 잠재적 문제 상황을 미리 발견하기 위한 방식
- 신버전의 제공 범위를 늘려가면서 모니터링 및 피드백 과정을 거침
    - 로드밸런서를 통해 신버전을 경험하는 사용자를 조절할 수 있는 것이 특징
    - 실제 운영 환경에서 미리 테스트한다는 점이 블루-그린 배포와 비슷함
- 단계적 전환 방식을 통해 부정적 영향을 최소화, 상황에 따라 트래픽 양 조절 가능
- 버전 관리가 필요

![image3.png](/assets/images/Service/image3.png)

https://www.samsungsds.com/kr/insights/1256264_4627.html

---

## DevOps & Agile

- 소프트웨어 개발의 모든 측면에 효율성과 예측 가능성을 제공하는 두 가지 상호 보완적인 방법

### DevOps

- 기존 개발 팀과 운영 팀 간의 벽을 없애는 소프트웨어 제공 접근 방식
- 구축, 테스트 및 배포 프로세스를 최대한 자동화 → 이를 통해 새 소프트웨어 버전을 자주 릴리즈 할 수 있음
- 배포 파이프라인을 사용하여 여러 환경에 한 번에 배포하는 방식
- 코드형 인프라(IaC)를 사용 → 팀에서 관리 및 프로비저닝을 소프트웨어 개발 작업으로 처리할 수 있음

![image4.png](/assets/images/Service/image4.png)

### 애자일 방법론

- 협업, 신속한 소프트웨어 릴리스, 고객 피드백에 초점을 맞춘 반복적인 소프트웨어 개발 접근 방식
- 작업을 ‘스토리’라는 작은 단위로 나누고, ‘스프린트’라는 짧은 반복 기간 동안 작업
    - 각 스프린트에서는 새로운 소프트웨어 빌드를 출시

![image5.png](/assets/images/Service/image5.png)

https://www.netapp.com/ko/devops-solutions/what-is-devops/

https://unity.com/kr/topics/agile-vs-devops

https://aws.amazon.com/ko/compare/the-difference-between-agile-devops/

---

## CI/CD

### CI/CD (지속적 통합과 제공)

- CI(지속적 통합)
    - 개발자가 코드 변경 사항을 자동화된 빌드 및 테스트를 실행하는 중앙 저장소에 커밋하는 개발 방법
    - 지속적 통합 파이프라인에는 코드 커밋, 기본 자동 린팅, 종속성 확인, 소프트웨어 구축 및 빌드 아티팩트 생성 등 일련의 단계가 포함됨
    - Github, Gitlab 등과 같은 소스 코드 관리 시스템에서는 Jenkins와 같은 CI도구에서 각 코드 체크인 후 빌드 및 테스트 실행을 자동으로 시작할 수 있는 Webhook 통합을 제공
- CD(지속적 제공)
    - 지속적 통합이 마무리되는 지점
    - 애플리케이션을 클라우드 인프라 환경에 자동으로 전달
    - 새로운 코드 변경 사항과 테스트 완료된 코드 변경 사항을 클라우드 환경 전체에 적용 가능

### CI/CD 툴 예시

- Jenkins
    - 중앙 빌드 및 지속적인 통합 프로세스 가능
    - 소프트웨어 개발 프로젝트의 빌드 파이프라인 구성, 빌드 자동화의 확립, 배포 및 테스트 자동화 등을 지원
    - https://www.jenkins.io/
- CircleCI
    - 코드 구축, 테스트 배포에 이르기까지의 파이프라인 전반에 걸쳐 신속한 소프트웨어 개발 및 게시를 지원
    - Github Enterprise, Bitbucket과 통합하여 사용 가능
    - https://circleci.com/
- TeamCity
    - Java 환경에서 실행되며 Visual Studio 및 IDE와 통합 가능
    - Window와 Linux 모두 설치 가능하며, .Net 프로젝트도 지원
    - https://www.jetbrains.com/teamcity/
- Bamboo
    - https://www.atlassian.com/software/bamboo
- Gitlab
    - https://about.gitlab.com/
    - gitlab vs github action
        
        ![image6.png](/assets/images/Service/image6.png)
        

https://www.oracle.com/kr/devops/what-is-devops/