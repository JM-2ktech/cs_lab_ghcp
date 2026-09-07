# cs_lab_ghcp — GitHub Copilot 하네스 트랙

Copilot Studio 교안(입문·중급)과 **별개 트랙**입니다. Copilot Studio의
**GitHub Copilot 하네스** 위에서 Agent · Knowledge · Skill · Sandbox · Memory · Workflow 를 다룹니다.

소재는 **월말 법인카드 비용 대사**입니다. 명세 1,000행과 증빙 대장 997행을 맞춰 보고,
어긋난 3건을 찾아 회사 표준 양식 문서로 냅니다. 사내교육 3시간.

## 구성

| | 무엇 |
|---|---|
| `index.md` · `docs/*.md` | 수강생용 랩 사이트 (Jekyll · just-the-docs) |
| [docs/GHCP_Harness_비용대사_핸즈온.md](docs/GHCP_Harness_비용대사_핸즈온.md) | **강사용 설계 문서** (v2, 2026-08-26). 랩 본문의 근거 |
| `materials/` | 수강생 배포 재료 |
| `_instructions/` | 저작 규칙 · 재료 생성기 · **정답지**. 배포하지 않음 |

랩은 **넷**입니다(2026-09-02 확정). 설계 문서 §2·§7이 정본입니다.

| 페이지 | 분 | 무엇 |
|---|---|---|
| 시작 전에 | — | 재료 확인 · 하네스 선택 |
| Lab 1. 판단하는 Agent | 40 | Agent · 지식 · Sandbox 질의 · 대사 — **본류** |
| Lab 2. Skill | 35 | Skill · 표준 양식(docx · pdf) — **본류** |
| Lab 3. Memory와 게시 | 25 | Memory · 에이전트 화면 · 게시 |
| Lab 4. Workflow | 50 | 분류 · 에이전트 · M365 Copilot · 말단 |
| 피날레 | 2 | 오늘 한 것과 안 한 것 |

덱 넷(12 · 6 · 4 · 6분)이 랩 사이에 들어가 합계 180분입니다.

## ⚠️ 랩 본문은 프로브 이전 상태입니다

설계 문서 §9의 **프로브 여섯이 아직 미실측**입니다. 랩 페이지의 골격·완료 기준·축약 경로는
확정이지만, 실제 UI 라벨과 스크린샷은 프로브 뒤에 채웁니다. 미확정 스텝은 HTML 주석으로
자리만 잡아 두었습니다.

프로브 1·2(Sandbox가 xlsx를 여는가 / 결과 파일을 내려주는가)가 실패하면 §1.5에 따라
시나리오를 되돌립니다 — Lab 2가 통째로 바뀝니다. **그 전에는 배포하지 않습니다.**

## 실습 재료

설계 문서 §4가 정의한 4종입니다. `materials/` 만 수강생에게 배포합니다.

| 파일 | 무엇 |
|---|---|
| `카드내역_2026-07.xlsx` (+`.csv`) | 법인카드 명세 1,000행 + 하단 합계 `100,849,600` |
| `증빙대장_2026-07.xlsx` (+`.csv`) | 증빙 대장 997행 |
| `비용처리규정.docx` | Knowledge 로 올릴 처리 기준 |
| `비용처리_표준양식.docx` | Skill 이 쓸 회사 표준 템플릿 (워터마크 포함) |

`비용처리규정.md` 가 규정의 원본이고 docx 는 그 출력입니다 — **고칠 것은 md 쪽**입니다.
Knowledge 업로드가 PDF·Word·Excel·PowerPoint만 받아 docx 로 냅니다.

csv 판을 함께 두는 이유는 GHCP 하네스의 **대화 첨부 지원 형식에 xlsx 가 없기** 때문입니다
(이미지 · PDF · txt/csv/html/md · URL). 프로브 1에서 첨부 경로가 막히면 csv 로 갈아 끼웁니다.

```bash
python _instructions/make_materials.py      # 만든다 (시드 20260827 고정)
python _instructions/verify_materials.py    # 디스크의 파일만 읽어 다시 대사한다
```

심어 둔 불일치와 정답은 `_instructions/재료_설계와_정답.md` 에 있습니다.

## 사이트 빌드

```bash
bundle install
bundle exec jekyll serve      # http://localhost:4000/cs_lab_ghcp/
```

## 검증

```bash
bundle exec jekyll build
python _instructions/linkcheck.py            # 링크·앵커·스텝 번호
python _instructions/stylecheck.py           # 문체
python ../_tools/sync_infra.py               # 공유 인프라 드리프트
python _instructions/verify_materials.py     # 재료
```

`linkcheck` 의 「placeholder screenshots」는 아직 안 찍은 컷이라 정상입니다.
**ADVANCED · OTHER · step numbering 이 0이어야** 통과입니다.

## 형제 저장소

- `cs_lab` — Copilot Studio 입문(1일차). 공개 중. **공유 인프라 7종의 정본**
- `cs_lab_adv` — Copilot Studio 중급(2일차). 미배포
