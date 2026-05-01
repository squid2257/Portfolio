# 오현준 Portfolio — 작품 추가 가이드

## 폴더 구조

```
portfolio/
├── index.html              ← 메인 포트폴리오 페이지
├── css/
│   └── style.css           ← 전체 공통 스타일
├── js/
│   └── main.js             ← 스크롤·필터 인터랙션
├── assets/
│   └── resume.pdf          ← 이력서 PDF (교체 필요)
└── projects/
    ├── project-01/
    │   └── index.html      ← 작품 상세 페이지
    ├── project-02/
    │   └── index.html
    └── ...                 ← 새 작품마다 폴더 추가
```

---

## 새 작품 추가하는 법

### 1. 폴더 복사
`projects/project-01/` 폴더를 복사해서 `projects/project-11/` 처럼 번호를 붙여 만드세요.

### 2. 작품 상세 페이지 수정 (`projects/project-11/index.html`)
파일 안에서 `▼` 주석이 달린 부분만 바꾸면 됩니다:

| 항목 | 위치 | 수정 내용 |
|------|------|-----------|
| 카테고리 | `.project-category` | `영상/모션` / `개발/코딩` / `게임` / `그래픽 디자인` |
| 제목 | `.project-title` | 작품 제목 |
| 한 줄 소개 | `.project-subtitle` | 작품 설명 |
| 메타 정보 | `.project-meta-item` | 연도, 툴, 기간 등 |
| 커버 이미지 | `.project-cover-img` | `<img src="cover.jpg">` 로 교체 |
| 본문 | `.project-body` | 배경, 과정, 회고 텍스트 |
| 갤러리 | `.project-gallery` | `<img src="...">` 로 교체 |
| 이전/다음 링크 | `.project-nav-bottom` | 연결할 작품 경로와 제목 수정 |

### 3. 메인 페이지에 카드 추가 (`index.html`)
`<!-- WORKS LIST -->` 와 `<!-- / WORKS LIST -->` 사이에 아래 블록을 복사해서 붙여넣기:

```html
<a href="projects/project-11/index.html" class="work-item reveal" data-category="motion">
  <div class="work-thumb">
    <div class="work-thumb-img" style="background:#1a1a2e;">
      <span class="thumb-label">영상/모션</span>
    </div>
  </div>
  <div class="work-meta">
    <span class="work-num">011</span>
    <div class="work-info">
      <h3 class="work-title">작품 제목</h3>
      <p class="work-desc">짧은 설명 — 툴, 기간, 키워드 등</p>
    </div>
    <span class="work-year">2026</span>
    <span class="work-arrow">→</span>
  </div>
</a>
```

`data-category` 값은 필터 버튼과 일치시키세요:
- `motion` → 영상/모션
- `dev` → 개발/코딩
- `game` → 게임
- `graphic` → 그래픽 디자인

---

## 커버 이미지 추가하는 법
작품 폴더 안에 이미지를 넣고 `<img>` 태그로 교체:

```html
<!-- 기존 -->
<div class="project-cover-img reveal">── 커버 이미지 / 영상 embed ──</div>

<!-- 교체 후 -->
<img class="project-cover-img reveal" src="cover.jpg" alt="작품명 커버" style="object-fit:cover;" />
```

유튜브 영상을 넣고 싶다면:
```html
<div class="project-cover-img reveal" style="padding:0; overflow:hidden;">
  <iframe width="100%" height="100%" src="https://www.youtube.com/embed/VIDEO_ID"
    frameborder="0" allowfullscreen style="display:block;"></iframe>
</div>
```

---

## SNS / 이메일 수정
`index.html` 하단 `#contact` 섹션의 `href` 값을 실제 주소로 바꾸세요.

## Resume PDF 교체
`assets/resume.pdf` 파일을 같은 이름으로 덮어쓰면 됩니다.
