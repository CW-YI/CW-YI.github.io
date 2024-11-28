---
layout: single
title: Open-Source 
categories: Memo
tags: [SE study]
---

# Open-source

## Open Source Software

- **Definition**
    - 개방형 협업을 통해 개발 및 관리되는 소프트웨어

- **Fundamental Principles**
    - 커뮤니티
    - 투명성
    - 공개 협업
    - 신속한 프로토타입 제작
    - 포용적 능력주의

- **Types of Licenses**
    - MIT
        - 소스 코드 공개 의무 X, 동일한 라이센스 적용 X, 상업적 이용 O
    - BSD
        - 소스 코드 공개 의무 X, 동일한 라이센스 적용 X, 상업적 이용 O
        - GPL보다 덜 제한적
    - Apache
        - 소스 코드 공개 의무 X, 동일한 라이센스 적용 X, 상업적 이용 O
        - BSD와 비슷하나 특허권에 관한 내용이 포함됨
    - GPL
        - 소스 코드 공개 의무 O, 동일한 라이센스 적용 O, 상업적 이용 O
        - 의무사항이 타 라이센스에 비해 엄격한 편
        - https://wiki.kldp.org/wiki.php/OpenSourceLicenseGuide#s-3.2.1
    - MPL 2.0, LPGL, EPL, AGPL 등

- **참고 자료**
    - https://aws.amazon.com/ko/what-is/open-source/
    - https://www.ibm.com/kr-ko/topics/open-source

---

## Open Source Project

- **Contribution Process**
    - Issue
        - 프로젝트에 대한 질의응답이나 버그 제보, 개선 방안에 대한 논의가 이루어짐
        - 기여할만한 항목을 찾아 의견을 남기거나, 개선 방안을 제시하는 것이 가능
    - Fork
        - 다른 프로젝트의 저장소를 깃허브의 내 계정으로 복제해 오는 것
        - 작업 사항을 내 계정으로 포크해 온 저장소에 우선 기록한 후, 수정한 내용이 원본 저장소에 반영되도록 요청(Pull Request)하는 방식으로 진행
        - 원본 저장소로부터 포크해 온 저장소를 최신화 상태로 유지하는 것도 중요
    - PR(Pull Request)
        - 내 수정 사항을 원본 저장소에 pull request → 이후 승인을 통해 merge가 되었다면, 해당 프로젝트의 기여자 목록에 올라가게 됨

- **Documentation**
    - 오픈 소스 프로젝트를 공개할 때 필요한 문서들
    - License 문서
    - README 문서
    - CONTRIBUTING 문서
    - https://github.com/KMU-OSS-Laboratory/Github_Document_Guide

- **Code Review**
    - 작성한 코드를 점검하고 피드백을 교환
    - 코드 리뷰 시 확인해야 할 사항들
        - 유지 보수성
        - 재사용성
        - 안정성
        - 확장성
        - 테스트
    - https://github.com/meshkorea/front-end-engineering/blob/main/conventions/code-review/index.md

- **Conventions**
    - 프로젝트의 일관성과 가독성 유지를 위한 코드 작성 규칙
    - 네이밍 컨벤션, 커밋 컨벤션 등

- **참고 자료**
    - https://seongjin.me/how-to-contribute-to-open-source/

---

## Utilizing Open Source

- **Benefits**
    - 비용 절감
    - 자유로운 사용과 수정
    - 커스터마이즈 가능성
    - 커뮤니티 지원
    - 투명성

- **Limitations**
    - 기술 지원의 부족
    - 유지 보수의 어려움
    - 보안 문제
    - 기능의 제한
    - 문서화의 부족
    - https://wikidocs.net/250639

- **Examples**
    - Linux → 1991년 개발된 오픈소스 운영체제
    - Apache → 가장 널리 사용되는 웹 서버 소프트웨어 중 하나
    - Mozilla → 모질라 재단에서 개발한 웹 브라우저 시리즈
    - https://wikidocs.net/250638
    - React → MIT 라이센스
    - Flask → 백엔드
    - VScode