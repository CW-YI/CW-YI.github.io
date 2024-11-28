---
layout: post
title: Deployment and Monitoring 
categories: Memo
tags: [SE study]
---

# Deloyment and Monitoring

## 효율적인 배포 전략

![image.png](/assets/images/Deloyment and Monitoring/image.png)

(롤아웃* → 발표, 생산, 출시 등을 뜻함)

### **배포 전략들**

- recreate : 이전 버전 A가 종료 된 후 신규 버전 B가 롤아웃됨
- rolling(ramped) :  신규 버전 B가 천천히 롤아웃되며 이전 버전 A를 교체
- blue/green : 신규 버전 B가 이전 버전 A와 함께 배포된 후 트래픽이 신규인 B로 교체
- canary : 신규 버전 B가 일부 사용자에게 배포된 후 전체 롤아웃으로 진행
- A/B testing : 신규 버전 B는 특정 조건에서 사용자의 하위 집합으로 배포
- shadow : 신규 버전 B는 이전 버전 A와 함께 실제 트래픽을 수신하지만 응답에 영향을 미치지 않고 숨어있음

### **배포 전략 요약**

- recreate 방법은 서비스가 중단되기 때문에 사용X
- 개발/스테이징 배포는 특별한 설정이 없는 rolling 방법이 좋음
- 프로덕션 환경 배포는 rolling이나 blue/green 배포가 일반적
- 안정성에 대한 확신이 없는 경우 canary나, A/B test, shadow 배포 방법을 사용할 수 있음

### **CI/CD 파이프라인을 구성할 때 고려해야하는 요소**

![image1.png](/assets/images/Deloyment and Monitoring/image1.png)

### **배포 전략을 세울 때 고려해야 하는 요소**

![image2.png](/assets/images/Deloyment and Monitoring/image2.png)

### **단계별 배포 파이프라인**

![image3.png](/assets/images/Deloyment and Monitoring/image3.png)

https://www.msaschool.io/operation/deployment/deployment-three/

https://velog.io/@appti/%EB%B0%B0%ED%8F%AC%EB%A5%BC-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A0%84%EC%97%90-%EB%B0%98%EB%93%9C%EC%8B%9C-%EC%95%8C%EC%95%84%EC%95%BC-%ED%95%A0-%EA%B2%83%EB%93%A4

---

## 효율적인 모니터링

### **클라우드 모니터링 전략**

1. 클라우드 리소스 시각화
2. 자동화된 알림 설정 → 이벤트 알람을 통해 인시던트를 빠르고 효율적으로 관리

### **리소스 최적화를 위한 실질적인 방법**

1. 자동화된 인스턴스 관리
2. 스케일링 전략 (수직/수평)
3. RI(Reserved Instances) SP(Saving plans) 활용

### **클라우드 비용 최적화를 위한 방법**

1. 정기적인 사용량 모니터링을 통해 불필요한 리소스 파악 후 제거
2. 자동 스케일링을 설정하여 필요할 때만 리소스를 할당, 사용량이 감소할 때 자동으로 축소
3. 예약 인스턴스와 스팟 인스턴스를 활용해 비용을 절감
4. 멀티 클라우드 전략을 도입하여 각 클라우드 제공업체의 장점을 최적화
5. 태그 및 카테고리화를 통해 리소스를 체계적으로 관리하고 비용을 정확히 추적
6. 비용 관리 도구를 사용해 실시간으로 비용을 추적하고 분석하여, 예산 초과를 방지하고 비용 절감

### **모니터링 도구**

- **Splunk**
    - 데이터 수집, 분석 및 시각화를 위한 로그 관리 및 분석 도구로, DevOps의 환경에서 활용됨
    - 장점
        - 강력한 로그 분석 기능 및 데이터 시각화
        - 확장 가능한 플랫폼 / 광범위한 데이터 소스와 통합 지원
    - 단점
        - 복잡한 설정과 높은 비용, 성능 최적화가 필요할 수 있음
- **BigPanda**
- **DynaTrace**
    - 애플리케이션 성능 모니터링(APM) 도구, AI 기반의 문제 진단과 자동화된 분석을 제공
    - 장점
        - AI 기반 분석으로 문제 탐지 및 해결이 빠름
        - 실시간으로 전체 스택 모니터링 / 컨테이너와 클라우드 환경 최적화
    - 단점
        - 상대적으로 높은 비용 / 사용 학습 곡선이 존재
- **PagerDuty**
- **AppDynamics**
    - 애플리케이션 성능 관리 도구, 성능 및 사용자 경험을 실시간으로 모니터링
    - 장점
        - 애플리케이션 중심의 깊은 가시성 제공
        - 데이터 기반의 실시간 분석 / 사용자 경험 중심의 성능 관리
    - 단점
        - 고급 설정에 시간에 리소스가 소요 / 비용이 비교적 높음
- **Moogsoft**
- **Datadog**
- **Edgedelta**

https://blog.kyobodts.co.kr/2024/09/03/%ED%9A%A8%EC%9C%A8%EC%A0%81%EC%9D%B8-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EB%AA%A8%EB%8B%88%ED%84%B0%EB%A7%81-%EC%A0%84%EB%9E%B5%EA%B3%BC-%EB%8F%84%EA%B5%AC/

https://clickup.com/ko/blog/146161/aiops-tools