```markdown
---
title: React useEffect 패턴 모음
date: 2025-08-11
tags: [react, hooks, effect]
categories: react
description: 의존성, cleanup, 비동기 처리 패턴
---

### 1) 의존성 관리
- ESLint 플러그인 `react-hooks/exhaustive-deps`로 누락 방지

### 2) cleanup
```tsx
useEffect(() => {
  const id = setInterval(() => {/* ... */}, 1000);
  return () => clearInterval(id);
}, []);
