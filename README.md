# PDF 논문 · 보고서 쉬운 해설 & 카드뉴스 생성기

PDF를 올리면 Gemini가 초등학생 눈높이 해설, 3줄 요약, 카드뉴스 4장 구성안을 만들어 줍니다.

## 폴더 구조

```
├── api/analyze.js    # 서버리스 함수 (Gemini 호출, API 키 사용)
├── public/
│   ├── index.html    # 화면
│   └── app.js        # 화면 동작
├── vercel.json       # 함수 최대 실행 시간 설정
└── package.json
```
