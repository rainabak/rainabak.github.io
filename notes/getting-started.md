---
title: 프론트엔드 정리 시작하기
date: 2025-08-11
tags: [setup, workflow]
categories: fe
description: 레포 구조와 글 작성 규칙
---

## 폴더 구조
- `notes/`에 마크다운 파일을 추가하면 글이 됩니다.
- Front matter의 `title`, `date`, `tags`, `categories`만 채우면 자동 반영.

## 글 작성 규칙(예시)
- 파일명은 `react-useEffect-tips.md` 처럼 주제-키워드 형태
- 코드 블록은 삼중 백틱으로
```js
const el = document.querySelector('#app');
