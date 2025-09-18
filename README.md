# 부수 기반 한자 학습 게임앱 📚

한자의 부수를 중심으로 의미·형태·발음을 직관적으로 학습할 수 있는 모바일 우선 게임입니다. SRS(간격 반복 시스템) 기반의 복습과 퀴즈 모드를 결합하여 효과적인 한자 학습을 제공합니다.

## ✨ 주요 기능

### 🎮 학습 시스템
- **부수 기반 학습**: 한자의 부수를 중심으로 체계적인 학습
- **SRS (Spaced Repetition System)**: 변형된 SM-2 알고리즘으로 최적화된 복습 스케줄링
- **4지선다 퀴즈**: 부수 힌트를 활용한 직관적인 퀴즈 시스템
- **즉시 피드백**: 실시간 정답 확인과 상세한 설명 제공

### 📊 개인화된 학습 경험
- **오늘의 학습 묶음**: 개인별 맞춤 학습 컨텐츠 추천
- **테마별 학습 세트**: 물/나무/사람 등 주제별 그룹 학습
- **학습 진도 추적**: 일일 연속 학습, 주간 XP, 레벨 시스템
- **성취 배지 시스템**: 학습 동기부여를 위한 다양한 성취 시스템

### 📖 단어장 및 검색
- **포괄적인 한자 데이터**: 1급까지의 확장된 한자 데이터베이스
- **고급 검색/필터링**: 급수별, 부수별, 학습 상태별 필터링
- **즐겨찾기 시스템**: 중요한 한자 북마크 기능
- **학습 상태 추적**: 개별 한자의 학습 진도 및 복습 상태

### 🔊 멀티미디어 지원
- **발음 오디오**: 정확한 한자 발음 학습 지원
- **시각적 디자인**: 잉크/아이보리 색상의 고대 문양 테마
- **접근성 지원**: 키보드 포커스, 적절한 폰트 크기 등

## 🛠 기술 스택

- **Frontend**: React 18, TypeScript
- **Styling**: Tailwind CSS v4
- **UI Components**: shadcn/ui
- **Icons**: Lucide React
- **Analytics**: Google Analytics 4
- **Build Tool**: Vite (추정)

## 🚀 시작하기

### 사전 요구사항
- Node.js 18.0.0 이상
- npm 또는 yarn

### 설치 및 실행

1. **저장소 클론**
```bash
git clone <repository-url>
cd hanzi-learning-app
```

2. **의존성 설치**
```bash
npm install
# 또는
yarn install
```

3. **개발 서버 실행**
```bash
npm run dev
# 또는
yarn dev
```

4. **브라우저에서 확인**
   - http://localhost:3000 에서 앱을 확인할 수 있습니다.

### Google Analytics 설정

1. Google Analytics 4 계정 생성
2. 새 속성 생성 후 측정 ID (G-XXXXXXXXXX) 획득
3. `/public/index.html` 파일에서 `GA_MEASUREMENT_ID`를 실제 측정 ID로 교체

```html
<!-- 교체 전 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>

<!-- 교체 후 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-YOUR-ACTUAL-ID"></script>
```

## 📁 프로젝트 구조

```
├── App.tsx                 # 메인 앱 컴포넌트
├── components/             # 리액트 컴포넌트들
│   ├── HomeScreen.tsx      # 홈 화면
│   ├── QuizScreen.tsx      # 퀴즈 화면
│   ├── VocabularyScreen.tsx # 단어장 화면
│   ├── AchievementScreen.tsx # 성취 화면
│   ├── QuizCard.tsx        # 퀴즈 카드 컴포넌트
│   ├── ProgressBar.tsx     # 진도 표시 바
│   ├── SessionComplete.tsx # 세션 완료 화면
│   └── ui/                 # shadcn/ui 컴포넌트들
├── lib/                    # 유틸리티 및 로직
│   ├── data.ts            # 한자, 부수, 퀴즈 데이터
│   ├── types.ts           # TypeScript 타입 정의
│   ├── srs.ts             # SRS 알고리즘 구현
│   ├── achievement.ts     # 성취 시스템 로직
│   └── audio.ts           # 오디오 재생 기능
├── styles/
│   └── globals.css        # 전역 스타일 (Tailwind v4)
└── public/
    └── index.html         # HTML 템플릿 (GA 포함)
```

## 🎯 주요 컴포넌트

### App.tsx
- 앱의 메인 컴포넌트
- 화면 라우팅 및 상태 관리
- 사용자 진도 및 SRS 카드 관리

### QuizScreen.tsx
- 퀴즈 인터페이스 제공
- 4지선다 문제 표시
- 실시간 피드백 및 점수 계산

### VocabularyScreen.tsx
- 한자 단어장 기능
- 검색 및 필터링
- 개별 한자 학습 시작

### AchievementScreen.tsx
- 성취 배지 표시
- 학습 통계 확인
- 진도 추적

## 📊 SRS (Spaced Repetition System)

본 앱은 변형된 SM-2 알고리즘을 사용하여 개인별 학습 패턴에 맞춘 복습 스케줄을 제공합니다:

- **Again**: 틀린 문제 - 1분 후 재복습
- **Hard**: 어려운 문제 - 기본 간격의 1.2배
- **Good**: 적절한 난이도 - 기본 간격 적용
- **Easy**: 쉬운 문제 - 기본 간격의 1.3배

## 🎨 디자인 시스템

- **컬러 팔레트**: 잉크/아이보리 기반의 고대 문양 테마
- **Typography**: 16px 기본 폰트 크기, 접근성 고려
- **Responsive**: 모바일 우선 디자인
- **Dark Mode**: 다크/라이트 모드 지원

## 📈 분석 및 추적

### 내장된 이벤트 추적
- `trackQuizStart(theme)` - 퀴즈 시작
- `trackQuizComplete(score, theme)` - 퀴즈 완료
- `trackAchievementUnlock(achievementId)` - 성취 달성
- `trackCharacterStudy(characterId)` - 개별 한자 학습

### 사용 예시
```javascript
// 퀴즈 시작 추적
window.trackQuizStart('nature');

// 성취 달성 추적
window.trackAchievementUnlock('first_week');
```

## 🔧 개발 가이드라인

### 코드 스타일
- TypeScript 엄격 모드 사용
- 함수형 컴포넌트 및 Hooks 사용
- shadcn/ui 컴포넌트 우선 사용

### 상태 관리
- React useState/useEffect 기반
- 로컬 스토리지 활용 (향후 구현 예정)
- SRS 카드 상태의 영속성 보장

### 접근성
- 키보드 네비게이션 지원
- 적절한 ARIA 라벨링
- 색상 대비 준수 (WCAG 2.1 AA)

## 🚧 향후 개발 계획

- [ ] 로컬 스토리지/IndexedDB 연동
- [ ] 서버 동기화 기능
- [ ] 소셜 기능 (친구, 리더보드)
- [ ] 더 다양한 퀴즈 타입
- [ ] 한자 쓰기 연습 기능
- [ ] 오프라인 모드 지원

## 🤝 기여하기

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이센스

이 프로젝트는 MIT 라이센스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

## 📞 문의

프로젝트에 대한 질문이나 제안사항이 있으시면 이슈를 생성해 주세요.

---

**부수 기반 한자 학습 게임앱**으로 효과적이고 재미있는 한자 학습을 시작해보세요! 🚀
