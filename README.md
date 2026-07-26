# jinpop.github.io

박성진 포트폴리오 — https://jinpop.github.io

프레임워크 없이 시맨틱 HTML + 단일 CSS로 만든 정적 페이지입니다.

## 구조

```
index.html   페이지 전체 (HTML · CSS · JS 인라인)
og.png       링크 프리뷰용 OG 이미지 (1200×630)
img/         프로젝트 스크린샷 (WebP)
```

## 구현 메모

- **폰트** — Pretendard Variable 동적 서브셋(jsdelivr CDN). 모노스페이스는 시스템 스택만 사용해 추가 로드 없음
- **다크 모드** — `<head>` 인라인 동기 스크립트로 첫 페인트 전에 테마를 확정(FOUC 방지). `localStorage` 접근이 차단된 환경에서도 `prefers-color-scheme` 폴백이 동작하고, JS가 꺼져 있어도 CSS 미디어 쿼리로 시스템 설정을 따름
- **모션** — `IntersectionObserver` 기반 1회성 fade-up. 초기 숨김 상태는 `html.js` 게이트 뒤에 두어 JS 실패 시에도 콘텐츠가 보이며, `prefers-reduced-motion: reduce`를 존중
- **내비게이션** — 뷰포트 중앙 띠(`rootMargin`)로 활성 섹션을 판정하고 `aria-current`로 표시
- **접근성** — 스킵 링크, 랜드마크·헤딩 구조, `:focus-visible` 링, 본문 대비 4.5:1 이상
- **성능** — 이미지 전량 WebP(총 192KB), `width`/`height` 명시로 CLS 방지, 외부 의존성·트래커 없음

## 로컬 실행

```bash
python3 -m http.server 4173
```
