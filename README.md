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

## Vercel 배포

1. 이 폴더 전체를 GitHub 저장소에 올립니다. (`.env` 파일은 올리지 마세요)
2. Vercel → **Add New → Project** → 저장소 선택 → **Import**
3. **Framework Preset: Other**로 두고, Build/Output 설정은 건드리지 않습니다.
4. **Environment Variables**에 추가한 뒤 **Deploy**
   - `GEMINI_API_KEY` : Gemini API 키 (필수)
   - `ACCESS_CODE` : 접속 코드 (선택, 설정하면 코드를 아는 사람만 사용 가능)
   - `GEMINI_MODEL` : 모델 변경 시에만 (기본값 `gemini-3.8-flash`)
5. 환경변수를 나중에 바꾸면 **Redeploy**해야 적용됩니다.

## 제한 사항

- PDF는 최대 4MB (Vercel 함수 요청 본문 한도 4.5MB 때문)
- 분석 시간이 길어질 수 있어 함수 최대 실행 시간을 60초로 설정했습니다.
