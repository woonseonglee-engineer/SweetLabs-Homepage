# SweetLabs 홈페이지

스윗랩스 공식 홈페이지. 단일 HTML 파일, 의존성 없음, GitHub Pages 호스팅.

## 파일 구조

```
sweetlabs-site/
├── index.html    # 사이트 본체 (HTML+CSS+JS 한 파일)
├── CNAME         # 커스텀 도메인 (sweetlabs.co.kr)
└── README.md     # 이 파일
```

---

## GitHub Pages 배포 5분 가이드

### 1. GitHub 레포 생성
1. GitHub에서 새 레포 만들기 → 이름은 `sweetlabs-site` 같은 거 아무거나 (Public 권장)
2. 이 폴더의 파일들을 그 레포에 푸시:

```bash
cd sweetlabs-site
git init
git add .
git commit -m "Initial homepage"
git branch -M main
git remote add origin https://github.com/<your-username>/sweetlabs-site.git
git push -u origin main
```

### 2. GitHub Pages 켜기
1. 레포 → **Settings** → 좌측 메뉴 **Pages**
2. **Source**: Deploy from a branch
3. **Branch**: `main` / `/ (root)` 선택 → Save
4. 1~2분 기다리면 `https://<your-username>.github.io/sweetlabs-site/` 에서 확인 가능

### 3. 커스텀 도메인 (sweetlabs.co.kr) 연결

**A. GitHub Pages 설정**
- Settings → Pages → **Custom domain** 칸에 `sweetlabs.co.kr` 입력 → Save
- (CNAME 파일은 이미 레포에 있으니까 자동 인식됨)

**B. 도메인 등록 업체 (가비아/후이즈 등) DNS 설정**

루트 도메인(`sweetlabs.co.kr`)을 쓰는 경우 → **A 레코드** 4개를 추가:

| 타입 | 호스트 | 값 |
|------|--------|-----|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

그리고 **www** 서브도메인용 CNAME도 같이:

| 타입 | 호스트 | 값 |
|------|--------|-----|
| CNAME | www | `<your-username>.github.io` |

**C. HTTPS 활성화**
- DNS 전파 후 (보통 30분~몇 시간) Settings → Pages 에서 **Enforce HTTPS** 체크박스 활성화
- Let's Encrypt 인증서 자동 발급됨

---

## 수정하기

`index.html` 한 파일만 고치면 끝. 푸시하면 1~2분 안에 반영됨.

**자주 바꾸는 것들:**
- 카피 문구: HTML 본문 직접 수정
- 색상/타이포: `<style>` 안의 `:root { --bg, --fg, ... }` CSS 변수
- 통계 숫자: `.stat-num` 부분
- 이메일 주소: `hello@sweetlabs.co.kr` 검색해서 일괄 변경

---

## 디자인 메모

- **레퍼런스**: Tesla. 풀스크린 섹션 + 한 문장 + 큰 여백.
- **톤**: 순백 다크. `#000` 바탕에 `#fff` 텍스트, 미세한 그라데이션과 그리드 라인으로 깊이감.
- **타이포**: Inter (영문 디스플레이) + Pretendard (한글 본문).
- **모션**: Hero 페이드업, 스크롤 시 reveal, 자이로 회전 애니메이션.
- **반응형**: 900px / 768px 브레이크포인트.

---

© 2026 SweetLabs Co., Ltd.
