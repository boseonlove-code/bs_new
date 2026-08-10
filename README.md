# One-page Static Blog

GitHub에 저장하고 Vercel 또는 Netlify로 바로 배포할 수 있는 **1페이지 정적 블로그**입니다.

## 구조

- `index.html` — 사이트 전체. 글 목록과 글 본문을 같은 페이지에서 표시
- `posts.json` — 게시글 목록/본문 관리 파일
- `site.json` — 사이트 이름, 도메인, 네이버 인증 토큰 메모용
- `sitemap.xml` — 검색엔진 제출용 사이트맵
- `robots.txt` — 검색로봇 접근 및 sitemap 위치
- `vercel.json` — Vercel 설정
- `netlify.toml` — Netlify 설정

## 배포 전 변경

`https://YOUR-DOMAIN.example`을 실제 배포 도메인으로 변경합니다. 대상 파일은 `index.html`, `site.json`, `sitemap.xml`, `robots.txt`입니다.

네이버 서치어드바이저의 HTML 메타태그 인증값은 `index.html`의 `naver-site-verification`에 입력합니다.

## 새 글 게시

`posts.json` 배열에 게시글 객체를 추가한 뒤 GitHub에 커밋하면 됩니다. `published`가 `false`인 글은 화면에 표시되지 않습니다.

## Vercel

GitHub 저장소를 연결하고 Framework Preset은 `Other`로 설정합니다. 빌드 명령과 Output Directory는 비워 둡니다.

## Netlify

GitHub 저장소를 연결합니다. Build command는 비우고 Publish directory는 `.`으로 설정합니다.

## 검색엔진 참고

이 프로젝트는 실제 HTML 문서가 `index.html` 하나인 1페이지 구조입니다. 개별 글은 해시(`#글ID`)로 같은 페이지 안에서 표시하므로 `sitemap.xml`에도 루트 URL만 포함했습니다.
