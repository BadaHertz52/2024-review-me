<p align="center"><img src="https://github.com/user-attachments/assets/7794eb6a-5d04-4c21-b1f5-da5904de02ee" alt="리뷰미 로고" width="500px"/></p>

🔗 [리뷰미 배포 페이지](https://review-me.page)

🔗 [리뷰미 팀 깃허브 저장소](https://github.com/woowacourse-teams/2024-review-me)

# 🔎 리뷰미 프로젝트
프로젝트를 함께한 동료들에게 받은 리뷰를 통해 자신이 어떤 개발자인지 파악하고 표현하는 데 도움을 주는 서비스입니다.  

## ✨ 주요 기능
### ☑️ 리뷰 작성
- 리뷰를 받고 싶은 프로젝트에 대한 리뷰 링크 생성
- 생성된 리뷰 링크에 접속해 리뷰 작성
  
### ☑️ 리뷰 확인
- 비회원은 리뷰 링크 생성 시 입력한 비밀번호로 받은 리뷰 확인
- 회원은 로그인 후, 리뷰 링크 관리 페이지에서 생성한 리뷰 링크를 확인하고 받은 리뷰 확인
- '모아보기 페이지'에서 하나의 프로젝트에 대한 다건의 리뷰를 질문별로 차트를 통해 한눈에 확인
- 받은 리뷰 중 기억하고 싶은 문구를 형광펜으로 표시

### ☑️ 깃허브 OAuth 로그인
- 깃허브로 로그인한 회원은 생성한 여러 리뷰 링크와 작성한 리뷰들 확인 가능

## ⚙️ 기술 스택
### 프론트엔드
<p align="center"><img src="https://github.com/user-attachments/assets/7497d615-02f5-48e6-b5a2-847121c56df8" width="400px"/></p>

### 백엔드
<p align="center"><img src="https://github.com/user-attachments/assets/0a7aa302-b737-496d-9fec-54a8088da3b5" width="400px"/></p>


# 🐳 프로젝트 기여 내용
## 👩‍💻 **Technical Contributions**  

### 🖍 **형광펜 기능 구현**  
- 리뷰를 수정하지 않고, 선택한 문구에 형광펜을 표시하는 기능 직접 개발
  
- **크로스 브라우징 이슈 해결**
  - iOS `Selection` 객체 초기화 오류 수정  
  - 브라우저별 이벤트 최적화  
  - 모바일 브라우저의 네이티브 UI 대응  

### 🚀 **성능 최적화**  
- **번들 최적화**: Webpack `production` 모드 외에도 **Brotli 압축 추가 적용**
  
- **폰트 최적화**: Preconnect, Preload, 가변 다이나믹 서브셋 폰트 활용
  
- **이미지 로딩 최적화**: React 기반 Skeleton Loader 구현

### ⚙️ **개발 환경 구축**  
- **AWS CodePipeline을 활용한 CD 구축**
  
- Mock Server 환경 구축
  - Webpack에서 `MSW`를 활용하여 브라우저 및 Node.js에서 동작하는 목 서버 구현  
  - 인증 확인 시 쿠키 검증 기능 추가  
  - 세션 인증이 필요한 테스트를 간소화하는 콜백 기반 유틸 함수 개발
    
- 코드 저장 시 `Stylelint`를 활용하여 CSS 코드 정렬 환경 설정

- Google Analytics, Amplitude를 사용해 사용자 데이터 수집

### 📝 리뷰 작성 폼 구현 및 페이지 리팩토링  
- 사용자 테스트 기반 애자일 개발 방식 적용, `Recoil`을 활용한 리뷰 작성 폼 구현
  
- 리뷰 작성 페이지 리팩토링
  - 동적인 질문지 및 다양한 기능(리뷰 작성, 캐러셀, 프로그레스 바)이 혼재되어 상태가 복잡했던 페이지를 리팩토링 진행해 유지보수성, 확장성 개선
  - 단일 책임 원칙을 기반으로 분리된 커스텀 훅의 단위 테스트 작성 및 책임 범위 검증

### 💡 React Query 쿼리 캐싱 문제 해결
- 모아보기 페이지에서 질문별 리뷰 데이터를 정확하게 캐싱하도록 쿼리 키 구조 개선  
- 로그아웃 시 회원 페이지의 캐시 데이터를 삭제하여, 로그인/로그아웃 시 올바른 데이터 로드 보장 

### ⚡ 사용자 중심의 에러 핸들링 
- 에러 핸들링 전략 수립
  - 사용자가 직접 해결 방법을 선택할 수 있는 선택권을 제공하고, 사용자 플로우에 적합한 UI 적용
  - 예: 페이지 렌더링 중 API 요청 실패 시 새로고침 버튼과 홈 이동 버튼 제공
    
- **ErrorBoundary 직접 구현하여, 불필요한 에러 전파를 방지하고 사용자 플로우에 맞는 오류 UI 렌더링**
  - 기존 `react-error-boundary` 사용 시, `useQuery`의 `onError`에서 에러가 소비되지 않아 전파되는 문제 발생  
  - 에러 메시지를 분석하여, fallback이 필요한 경우에만 상태 업데이트하도록 개선

## 🥳 Collaborative Contributions
- 프론트엔드 업무 분담 및 일정 관리
- 프론트엔드 팀 회의 리딩 및 회의록 작성
- 백엔드와의 협업을 위한 커뮤니케이션: 프론트엔드 회의 내용을 공유하고 의견 조율
- 팀 문화 개선을 위한 체크인 점수 도입, 팀원 간 이해도를 높이기 위한 피드백 문화 구축

## 🧑‍💻 팀원 소개

### 프론트엔드
|  <img src="https://github.com/user-attachments/assets/467f08bd-043f-411a-b1da-090450d641b4" alt="bada" width="120px" max-height="120px">   |  <img src="https://github.com/user-attachments/assets/4851713e-e8c3-4c8a-8536-b63cac2e4dc6" alt="soosoo" width="120px" max-height="120px"> |   <img src="https://github.com/user-attachments/assets/a904d69c-c48b-4f75-a46d-47f6ddbe22d0" alt="fe" width="120px" max-height="120px"> | <img src="https://github.com/user-attachments/assets/12241d5a-ba87-4267-a82f-1704c497241b" alt="ollie" width="120px" max-height="120px"> |
| :---: | :---: | :---: | :---: |
| [🐋 바다](https://github.com/badahertz52)  | [😍 쑤쑤](https://github.com/soosoo22)    | [🔥 에프이](https://github.com/chysis)   | [👾 올리](https://github.com/ImxYJL)   |

### 백엔드
| <img src="https://review-me-blog.github.io/assets/images/sancho-a505ff332869b4eda5a1fa6cf296ddc8.jpeg" width="120px" max-height="120px">  |  <img src="https://review-me-blog.github.io/assets/images/aru-f1f92d2d3284aab8aa385afd817d2ae7.jpeg" width="120px" max-height="120px">   | <img src="https://review-me-blog.github.io/assets/images/kirby-c5c179939bc7a2fd587bcc2cbb6af129.png" width="120px" max-height="120px"> |   <img src="https://review-me-blog.github.io/assets/images/ted-a4f788b021e7619d4cc9ae7fc0ab336d.png" width="120px" max-height="120px">  |
| :---: | :---: | :---: | :---: |
| [🦧 산초](https://github.com/nayonsoso)  | [🤸🏻‍♂️ 아루](https://github.com/donghoony)   | [💃 커비](https://github.com/skylar1220)   | [🐻 테드](https://github.com/Kimprodp)   |

