# Portfolio

백엔드 개발자 Sinhyuk의 포트폴리오 사이트. 정적 HTML로만 구성.

## Structure

```
portfolio/
├── index.html                        # 메인 랜딩 페이지
└── projects/
    ├── moch/index.html               # 프로젝트 1
    ├── anomaly-detection/index.html  # 프로젝트 2
    └── kafka-cluster/index.html      # 프로젝트 3
```

각 디렉토리 이름이 URL 경로가 됩니다. 예: `https://username.github.io/portfolio/projects/moch/`

## 로컬에서 확인

```bash
cd portfolio
python3 -m http.server 8000
# http://localhost:8000 접속
```

## GitHub Pages 배포

1. GitHub에서 새 레포지토리 생성 (예: `portfolio`)
2. 이 폴더의 내용을 푸시:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<USERNAME>/portfolio.git
   git push -u origin main
   ```
3. 레포 **Settings → Pages** 이동
4. **Source**: `Deploy from a branch` 선택
5. **Branch**: `main` / `/ (root)` 선택 → Save
6. 1~2분 후 `https://<USERNAME>.github.io/portfolio/` 에서 접속 가능

## 커스텀 도메인 (선택)

1. `portfolio/` 에 `CNAME` 파일 생성, 내용에 도메인 입력 (예: `sinhyuk.dev`)
2. 도메인 DNS에서 CNAME 레코드를 `<USERNAME>.github.io` 로 추가
3. GitHub Pages 설정에서 Custom domain 입력 후 Enforce HTTPS 체크

## 새 프로젝트 추가

1. `projects/<프로젝트-이름>/index.html` 생성
2. 기존 프로젝트 페이지 중 하나를 복사해서 내용만 수정
3. 메인 `index.html`의 `<ul class="project-list">` 에 항목 추가:
   ```html
   <li>
     <a href="./projects/<프로젝트-이름>/" class="project">
       ...
     </a>
   </li>
   ```

## 수정해야 할 곳

메인 `index.html` 하단에서:
- 이메일: `your.email@example.com`
- GitHub: `@yourusername`
- 블로그, LinkedIn 링크

## 디자인 노트

- **Dark + Monospace + Serif accent** 조합의 에디토리얼 스타일
- 폰트: JetBrains Mono (본문/코드) + Fraunces (헤드라인 세리프)
- 외부 의존성 없음 (Google Fonts만 사용). 완전 정적.
- 모든 페이지가 단일 HTML 파일. 빌드 스텝 없음.
