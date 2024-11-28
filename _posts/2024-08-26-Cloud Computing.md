---
layout: single
title: Cloud Computing 
categories: Memo
tags: [SE study]
---

# Cloud Computing

## 클라우드 컴퓨팅 개요

### **클라우딩 컴퓨팅의 정의 및 개념**

- 클라우드 컴퓨팅은 클라우드(인터넷)을 통해 서버, 스토리지, 데이터베이스, 네트워킹, 소프트웨어, 분석 등의 컴퓨팅 서비스를 제공

### 클라우드 서비스 모델의 개요

- IaaS(Infrastructure as a Service)
    - 가장 기본적인 범주, 클라우드를 통해 주문형 인프라 리소스를 제공
- PaaS(Platform as a Service)
    - 클라우드를 통해 필요한 모든 리소스를 제공
- SaaS(Software as a Service)
    - 전체적인 클라우드 기반 어플리케이션을 제공

- 클라우드 IaaS, PaaS, SaaS 차이

![image.png](/assets/images/Cloud Computing/image.png)

### 클라우딩 컴퓨팅의 이점과 한계

- 이점
    - 비용 / 속도 / 뛰어난 확장성 / 생산성 / 성능 / 안정성 / 보안
- 한계
    - 공급 업체 종속의 위험
    - 기본 클라우드 인프라에 대한 낮은 제어 수준
    - 데이터 개인 정보 보호 및 온라인 위협과 같은 보안 위험에 대한 우려

https://azure.microsoft.com/ko-kr/resources/cloud-computing-dictionary/what-is-cloud-computing

https://cloud.google.com/learn/advantages-of-cloud-computing?hl=ko

---

## 클라우드 서비스 제공업체

### 클라우드 서비스 제공업체 정의

- CPS(클라우드 서비스 제공업체)
    - 기업에서 네트워크를 통해 주문형으로 액세스할 수 있는 클라우드 기반 컴퓨팅 등의 확장 가능한 컴퓨터 리소스를 제공하는 제 3자 회사

### 클라우드 서비스 제공업체 비교

- AWS
    - 모든 범주에서 사용자가 요구하는 기능을 제공
    - AWS만 사용해도 전체 인프라 스트럭쳐를 통합 운영 가능
- Azure
    - 윈도우 플랫폼에 강함
- Google Cloud
    - 제공된 크레딧 안에서 자유로운 서비스 이용이 가능
    - 데이터 분석과 머신 러닝에 강함
    - 다양한 브라우저에 대한 호환성이 좋음
- AWS, Azure, Google Cloud 비교

![image1.png](/assets/images/Cloud Computing/image1.png)

https://www.apptunix.com/blog/aws-vs-azure-vs-google-cloud-platform/

---

## 클라우드 컴퓨팅 트렌드

### 서버리스 컴퓨팅 이점

- 서버리스 컴퓨팅이란?
    - 사용량에 따라 백엔드를 제공하는 방법
- 서버리스 컴퓨팅의 이점
    - 낮은 비용 / 간편한 확장성 / 간단한 백엔드 코드 / 시간 단축
    - https://www.cloudflare.com/ko-kr/learning/serverless/why-use-serverless/
- AWS 서버리스 서비스
    - https://aws.amazon.com/ko/serverless/
- Azure 서버리스 서비스
    - https://azure.microsoft.com/ko-kr/solutions/serverless

### 엣지 컴퓨팅

- 엣지 컴퓨팅이란?
    - 정보 저장 및 컴퓨팅 능력을 해당 정보를 생성하는 디바이스와, 이를 소비하는 사용자에게 더 가까이 제공하는 프로세스
- 중요성
    - 기업이 원시 데이터를 보다 효율적으로 수집하고 분석할 수 있음

### 하이브리드 클라우드와 멀티 클라우드

- 하이브리드 클라우드란?
    - 기업이 프라이빗 클라우드와 퍼블릭 클라우드를 결합하여 하나의 인프라처럼 사용하는 클라우드 컴퓨팅 전략
- 멀티 클라우드란?
    - 여러 퍼블릭 클라우드 서비스 공급자를 동시에 사용하는 클라우드 컴퓨팅 전략

→ 하이브리드 클라우드는 민감한 데이터와 어플리케이션을 보호하는 데 중점을 두고 일반적인 작업은 퍼블릭 클라우드에서 처리할 수 있는 반면, 멀티 클라우드는 벤더 종속성을 최소화하고 서비스 가용성과 비용 효율성을 높이기 위해 여러 클라우드 공급자를 동시에 사용하는데 의의를 둠.

https://www.samsungsds.com/kr/cloud-glossary/difference-hybrid-cloud-multi-cloud.html

---

## 클라우드 보안

### 클라우드 보안

- 클라우드 보인아리나?
    - 클라우드 기반의 어플리케이션, 데이터, 인프라를 보호하기 위한 사이버 보안 조치의 모음.
- 클라우드 보안 작동 방식
    - 데이터의 보호 보장, 규정 준수 지원 등에 대한 제어를 제공하기 위한 프로세스, 기술을 함께 구현하는 방법에 중점을 둠
    - 클라우드 서비스 제공업체(CSP)는 일반적으로 공유 책임 모델을 따름
        - 보안에 관해서는 제공업체와 고객 모두의 책임

### 클라우드 보안 솔루션 종류

- ID 및 액세스 관리(IAM)
- 데이터 손실 방지(DLP)
- 보안 정보 및 이벤트 관리(SIEM)
- 공개 키 인프라(PKI)

---

## 컨테이너와 오케스트레이션

### 컨테이너화

- 컨테이너화란?
    - 어플리케이션의 코드를 모든 인프라에서 실행하는 데 필요한 모든 파일 및 라이브러리와 함께 제공하는 소프트웨어 배포 프로세스
- 컨테이너 오케스트레이션이란?
    - 컨테이너를 자동으로 관리할 수 있는 소프트웨어 기술
- 컨테이너 기술 유형
    - Docker
        - 다양한 플랫폼에서 컨테이너식 어플리케이션을 빌드 및 배포할 수 있는 오픈 소스 컨테이너 런타임 기술
    - Kubernetes
        - 방대한 수의 마이크로서비스를 배포, 조정 및 관리하는 데 사용하는 오픈 소스 컨테이너 오케스트레이션 도구
- Docker vs Kubernetes
    - 개발자는 Docker를 사용하여 컨테이너 이미지를 생성 및 조작하고, Kubernetes를 사용하여 여러 마이크로서비스를 대규모로 관리함

https://aws.amazon.com/ko/compare/the-difference-between-kubernetes-and-docker/

### 클라우드 컨테이너

- 클라우드 컨테이너란?
    - 어플리케이션 코드, 라이브러리 및 클라우드에서 실행하기 위해 필요한 기타 종속성이 포함된 소프트웨어 코드 패키지
- 클라우드 컨테이너의 이점?
    - 컨테이너를 다양한 클라우드 서버 또는 인스턴스에 배포하고 관리 가능
    - 배포 간소화 / 유연성 / 복원력 / 확장성
- 클라우드 컨테이너 사용 사례
    - 마이크로서비스
    - DevOps

https://aws.amazon.com/ko/what-is/cloud-containers/

### Kubernets

- 쿠버네티스 개요
    - 컨테이너화된 워크로드와 서비스를 관리하기 위한 오픈소스 플랫폼
- 쿠버네티스 역할
    - 서비스 디스커버리와 로드 밸런싱
    - 스토리지 오케스트레이션
    - 자동화된 롤아웃과 롤백
    - 자동화된 빈 패킹
    - 자동화된 복구
    - 시크릿과 구성관리

https://kubernetes.io/ko/docs/concepts/overview/

---

## 클라우드에서의 머신러닝과 AI

### 클라우드 서비스를 통한 머신러닝

- 클라우트 컴퓨팅을 활용한 머신러닝의 장점
    1. 머신러닝 모델 학습에 필요한 대규모의 컴퓨팅 자원을 유연하게 제공
    2. 머신러닝 모델의 개발과 배포를 간소화
    3. 머신러닝 모델의 확장성과 접근성을 향상
    4. 머신러닝 모델의 운영 비용 절감

### AI 및 ML 서비스

- Vertex AI
    - ML 모델과 AI 어플리케이션을 학습 및 배포하고 AI 기반 어플리케이션에서 사용할 대규모 언어모델(LLM)을 맞춤설정할 수 있게 해주는 ML 플랫폼
- SageMarker
    - 모든 사용 사례에서 ML을 지원하는 다양한 도구를 한 곳에 결합한 완전관리형 서비스

---

## 클라우드 자동화 및 DevOps

### 클라우드 환경에서 자동화의 중요성

- 하이브리드 환경과 멀티클라우드 환경은 사용자 관리의 복잡성을 높이기 때문에 수동으로 리소스 및 어플리케이션을 효과적으로 유지관리, 추적, 확장, 보호하기가 거의 불가능 → 자동화를 통해 일관성, 확장성, 속도 향상 가능

### DevOps 관행 및 도구

- DevOps란?
    - 소프트웨어 배포의 속도와 품질을 높이기 위한 새로운 업무 방식
- IaC(Infrastructure as Code, 코드형 인프라)란?
    - DevOps의 핵심 사례
    - 모델을 배포할 때마다 동일한 환경을 생성
- CI/CD란?
    - DevOps의 핵심 사례
    - 지속적인 통합 및 배포를 의미, 소프트웨어 개발 라이프사이클을 간소화하고 가속화하는 것이 목표
    - CI/CD 파이프라인이란?
        - CI/CD 프로세스를 자동화함으로써 인적 오류를 최소화하고, 프로세스에 대한 일관성을 유지하는 것이 목표

### Terraform vs Ansible

- Terraform과 Ansible은 모두 IaC를 프로비저닝 할 수 있으며, Ansible은 어플리케이션과 서비스도 가능
- Terraform은 원하는 상태를 정의하여 IT 인프라 구성을 유지하려 하는 선언적 프로그래밍 방식을 사용
- Ansible은 원하는 상태에 도달하는 단계를 정의하여 IT 인프라 구성을 유지하려고 하는 절차적 프로그래밍을 사용

https://www.redhat.com/ko/topics/automation/ansible-vs-terraform

---

## 클라우드 비용 관리

### 클라우드 비용 최적화 전략

- 클라우드 리소스의 규모 적정 조정
- 사용되지 않는 리소스 제거
- 데이터 전송 비용 절감
- 스팟 인스턴스 활용

https://www.akamai.com/ko/glossary/what-is-cloud-optimization

### 클라우드 비용 모니터링 및 관리 도구

- 클라우드 모니터링 툴
    - Google Opreation
    - Microsoft Azure Monitor
    - Amazon CloudWatch
    - NCI 및 NCM

https://www.nutanix.com/kr/info/cloud-monitoring#bestpractices

https://cloud.google.com/architecture/framework/cost-optimization/monitor?hl=ko