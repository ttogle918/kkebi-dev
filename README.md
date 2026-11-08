# kkebi.dev 블로그

GitHub Pages(Jekyll)로 빌드되는 블로그예요. 글은 마크다운 파일 하나로 올려요.

## 글 쓰는 법

`_posts/` 에 `YYYY-MM-DD-영문-제목.md` 이름으로 파일을 만들어요. 파일 이름의 영문 제목이 주소가 돼요(`/posts/영문-제목/`).

```markdown
---
layout: post
title: "글 제목"
description: "카드에 보일 한 줄 요약"
tags: [kkebi, 측정]
---
본문을 마크다운으로 써요.
```

- 미래 날짜는 빌드에서 빠져요.
- 읽는 시간은 본문 길이로 자동 계산돼요.
- 사실 주장·수치는 직접 측정한 것만 적어요.

## 로컬 미리보기

- 가장 빠른 길: `preview/index.html` 을 브라우저로 열어요(레이아웃 모양 확인용 정적 파일).
- 실제 빌드(선택): Ruby 가 있으면 `bundle install` 후 `bundle exec jekyll serve` → http://localhost:4000
- 로컬 환경이 없어도 GitHub 에 푸시하면 Pages 가 알아서 빌드해요.

## Pages 설정 순서

1. GitHub 에 저장소를 만들고 이 폴더를 `main` 으로 푸시해요.
2. 저장소 Settings → Pages → Source: **Deploy from a branch**, Branch: `main` / `/ (root)`.
3. Custom domain 에 `kkebi.dev` 입력(저장소 루트의 `CNAME` 파일과 같아요).
4. DNS 가 확인되면 **Enforce HTTPS** 체크.

## DNS (가비아)

| 종류 | 호스트 | 값 |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | `<user>.github.io` |

DNS 반영에는 수 분~수 시간이 걸릴 수 있어요.

## 구성

- `_config.yml` 사이트 설정(플러그인은 jekyll-feed · jekyll-seo-tag · jekyll-sitemap 만)
- `_layouts/` `default` · `post`, `_includes/` 헤더·푸터·글 카드
- `index.html` 홈, `tags.html` 태그, `about.md` 소개, `404.html`
- `assets/css/style.css` 색은 kkebi 앱·랜딩과 같은 토큰(밝게/어둡게 자동)
- RSS 는 `/feed.xml`

## 채워야 할 자리표시

- `about.md` 의 소개 단락
- `_posts/` 의 예시 글 2개(내용 교체 또는 삭제)
- `_config.yml` 의 `description`
