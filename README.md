# 협력업체 명함 관리 — CADDIS 레이저

CADDIS 레이저 협력업체 명함을 GitHub Pages로 관리하는 아카이브.

---
https://caddis-gr.github.io/caddis-contacts/

## 파일 구조

```
caddis-contacts/
├── index.html        ← 명함 뷰어 (건드릴 일 없음)
├── companies.json    ← 업체 데이터 (여기만 편집)
└── README.md
```

---

## GitHub Pages 설정 (최초 1회)

1. 이 repo → **Settings → Pages**
2. Source: `Deploy from a branch`
3. Branch: `main` / `/ (root)`
4. 저장 → 30초 후 `https://{username}.github.io/caddis-contacts/` 접속 확인

---

## 업체 추가 방법

### 1단계 — Claude에게 명함 사진 전송

```
"명함 추가해줘" + 명함 사진 첨부
```

Claude가 아래 형식의 JSON 블록을 반환합니다.

### 2단계 — companies.json 편집

GitHub 웹에서 `companies.json` 클릭 → ✏️ 연필 아이콘 → 마지막 `}` 뒤에 `,` 추가 후 붙여넣기 → **Commit changes**

### JSON 항목 형식

```json
{
  "id": "V005",
  "company": "업체명",
  "person": "담당자",
  "position": "직책",
  "mobile": "010-0000-0000",
  "tel": "031-0000-0000",
  "fax": "031-0000-0000",
  "email": "name@company.com",
  "addr": "주소",
  "specialty": "전문분야",
  "cats": ["외주"],
  "primary": "주거래처",
  "xlsxlink": "",
  "memo": "메모"
}
```

### cats (거래 분류) 옵션

| 값 | 의미 |
|----|------|
| `"외주"` | 레이저 외주가공 업체 |
| `"자재"` | 원자재 납품 업체 |
| `"AS"` | 장비 A/S 업체 |
| `"소모품"` | 소모품 공급 업체 |
| `"장비"` | 장비 판매/임대 업체 |

복수 분류 가능: `"cats": ["외주", "자재"]`

### xlsxlink — 외주관리 xlsx 연결

외주 업체인 경우 Google Drive 공유 URL 입력:
```json
"xlsxlink": "https://drive.google.com/file/d/XXXX/view"
```
카드에 `📊 외주관리 xlsx →` 버튼이 자동으로 표시됩니다.

---

## 업체 ID 규칙

| 코드 | 용도 |
|------|------|
| V001~ | 외주가공 업체 |
| M001~ | 자재 납품 업체 |
| E001~ | 장비/AS 업체 |
| S001~ | 소모품 업체 |

---

## 현재 등록 업체

| ID | 업체명 | 분류 | 비고 |
|----|--------|------|------|
| V004 | 주식회사 신영스틸 | 외주 | 주거래처, JOB-2026-006/007 |

---

## 연관 시스템

- **외주가공관리_CADDIS레이저.xlsx** — 발주·건명·현황판
- **자재관리시스템_CADDIS레이저.xlsx** — 입고·재고·잔재·스크랩
- [레이저절단_자동화시스템_요약.md](../레이저절단_자동화시스템_요약.md)
