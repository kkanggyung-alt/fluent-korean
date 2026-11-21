# CLAUDE.md

Claude Code용 한국어 출력 스타일(output-style) 플러그인 저장소임. 코드와 빌드 단계는 없음.

## 확인 방법

- 빌드·테스트 명령 없음
- 사본 일치 확인: `diff -r plugins/fluent-korean/output-styles .claude/output-styles` (출력 없으면 정상)
- JSON 형식 확인: `python3 -m json.tool .claude-plugin/marketplace.json && python3 -m json.tool plugins/fluent-korean/.claude-plugin/plugin.json`
- 실제 동작은 Claude Code에서 `/plugin marketplace add kkanggyung-alt/fluent-korean` 후 `/config`에서 스타일을 골라 확인함

## 폴더 구조

- `plugins/fluent-korean/output-styles/` — 배포본 출력 스타일 2종(`fluent-korean.md`: 코딩 지침 유지, `fluent-korean-not-coding.md`: 미유지)
- `.claude/output-styles/` — 이 저장소 작업용 사본(배포본과 내용이 같아야 함)
- `plugins/fluent-korean/.claude-plugin/plugin.json` — 플러그인 메타데이터·버전
- `.claude-plugin/marketplace.json` — 마켓플레이스 등록 정보

## 하면 안 되는 것

- 출력 스타일을 한쪽만 고치지 않음. 두 폴더를 함께 고침
- 스타일 내용을 바꾸면서 `plugin.json`의 `version`을 그대로 두지 않음
- README의 한국어 본문은 사람이 쓴 글이므로 요청 없이 다시 쓰지 않음
- 기본 브랜치(`claude/fluent-korean-plugin-7o68bt`)에 직접 푸시하지 않음. 브랜치를 만들어 PR로 올림
