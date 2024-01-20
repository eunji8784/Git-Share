# 📚 목차
- [💡 Git Flow](#-git-flow)
- [💡 Issue, Pull Request Convention](#-issue-pull-request-convention)
  - [📌 Issue 제목 Convention](#-issue-제목-convention)
  - [📌 PR 제목 Convention](#-pr-제목-convention)
- [💡 Branch Convention](#-branch-convention)
  - [✏️ Branch 네이밍 규칙](#️-branch-네이밍-규칙)
- [💡 Commit Message Convention](#-commit-message-convention)
  - [🛠️ Commit Message 구조](#️-commit-message-구조)
    - [✅ 태그 (Tag) - 필수](#-태그-tag---필수)
    - [✅ 제목 (Subject) - 필수](#-제목-subject---필수)
    - [✅ 본문 (Body) - 선택](#-본문-body---선택)
    - [✅ 꼬리말 (Footer) - 선택](#-꼬리말-footer---선택)
  - [📝 Commit Message 템플릿](#-commit-message-템플릿)
  - [🖤 Commit Message Tag](#-commit-message-tag)


---

# 💡 Git Flow
```
1. develop 브랜치를 생성한다. (초기에 한번)
2. Issue를 생성한다.
3. develop branch base의 local - feature branch를 생성한다.
4. Add - Commit - Push - Pull Request 의 과정을 거친다.
5. Pull Request가 작성되면 작성자 이외의 다른 팀원이 Code Review를 한다.
6. Code Review가 완료되면 Pull Request 작성자가 develop branch로 Merge 한다.
7. Merge가 끝난 후에는 해당 Issue를 Close한다.
8. remote - develop branch에 새로운 코드가 Merge 될 때마다 모든 팀원 local - develop pull 받아 최신 상태를 유지한다.
9. main은 모든 작업이 끝난 후 develop에서 Merge 시킨다.
```

# 💡 Issue, Pull Request Convention
- Issue와 PR은 1개의 feature 단위로 생성한다.
- 작업 단위를 너무 크게 잡지 않는다.
  
## 📌 Issue 제목 Convention
```
[영어 대문자] 내용
```
<details>
<summary>ex</summary>
<img width="810" alt="스크린샷 2024-01-20 오후 4 32 51" src="https://github.com/eunji8784/Git-Share/assets/70746467/e6db96e9-d34f-4198-812c-cf660d92e72c">
</details>

- 내용은 다른 사람이 알아볼 수 있게 본인이 작업할 내용을 적는다
- 🔗 [Issue 템플릿](.github/ISSUE_TEMPLATE/)

## 📌 PR 제목 Convention
```
[영어 대문자] #이슈 번호 - 해당 이슈 내용
```
<details>
<summary>ex</summary>
<img width="519" alt="스크린샷 2024-01-20 오후 4 29 53" src="https://github.com/eunji8784/Git-Share/assets/70746467/2e5b35e5-1f23-4be3-b936-cea008a45308">
</details>

- 이슈와 내용이 동일할 필요는 없다
- 이슈 번호는 동일 해야 함
- 🔗 [Pull Reqeust 템플릿](.github/PULL_REQUEST_TEMPLATE.md)

# 💡 Branch Convention
- 브랜치 단위 = 이슈 단위 = PR 단위
  
| 종류 | 설명 |
| :--: | :-----: |
| main | 최종 버전 브랜치 (프로덕션 브랜치) |
| develop | 제품 출시 전 개발 브랜치 |
| feature | 기능 개발 브랜치 (develop base) |
| fix | 개발 과정에서 발생한 버그를 수정하는 브랜치 (develop base) |
| hotfix | 출시 버전에서 발생한 버그를 수정하는 브랜치 |
| refactor | 기능 수정 없이 코드의 품질만 개선하는 브랜치 (develop base) |

## ✏️ Branch 네이밍 규칙
```
feature/{issue-number}-{feature-name}
fix/{issue-number}-{feature-name}
ex) feature/#24-login
```
- main과 develop은 원래 이름 그대로 사용한다.
- {feature-name}은 최대한 간단하게 지정한다.
- 띄어쓰기는 '-'를 사용한다.

# 💡 Commit Message Convention
```
- 자신의 코드가 직관적으로 바로 파악할 수 있다고 생각하지 말 것
- 한 커밋에는 한 가지 문제만 담는다 (기능 단위로 나누기)
- 너무 많은 문제를 한 커밋에 담으면 추적하기 어렵다
```

## 🛠️ Commit Message 구조
```
태그(tag): 제목(subject)
본문(body)
꼬릿말(footer)
```

### ✅ 태그 (Tag) - 필수
```
- 태그는 영어로 쓰되 첫 문자는 대문자로 한다
- "태그: 제목"의 형태이며, : 뒤에만 space가 있음에 유의
예) Feat: ~, Fix: ~, Docs: ~ 
```

### ✅ 제목 (Subject) - 필수
```
 - 제목 끝에 특수문자는 삽입하지 말 것 예) 마침표(.), 느낌표(!), 물음표(?)
 - 제목은 영문 기준 50자 이내
 - 제목은 개조식 구문으로 작성 (말하고자 하는 내용을 요점 위주로 작성)
 - 제목과 본문을 한 줄 띄워 분리하기
```

### ✅ 본문 (Body) - 선택
```
 - 본문에는 변경한 내용과 이유를 설명하되, "어떻게" 보다 "무엇을", "왜"를 설명
 - 본문 내용은 양에 구애받지 않고 최대한 상세히 작성
 - 본문에 여러줄의 메시지를 작성할 땐 "-"로 구분 (한 줄당 72자)
```

### ✅ 꼬리말 (Footer) - 선택
```
1. 꼬리말은 optional이고 이슈 트래커 ID를 작성한다.
2. 꼬리말은 "유형: #이슈 번호" 형식으로 사용
3. 여러 개의 이슈 번호를 적을 때는 쉼표로 구분
4. 이슈 트래커 유형은 다음 중 하나를 사용한다
 - Fixes: 이슈 수정중 (아직 해결되지 않은 경우)
 - Resolves: 이슈를 해결했을 때 사용
 - Ref: 참고할 이슈가 있을 때 사용
 - Related to: 해당 커밋에 관련된 이슈번호 (아직 해결되지 않은 경우)
ex) Fixes: #53 Related to: #17, #24
```
 
## 📝 Commit Message 템플릿 
```
################
# <태그>: <제목> 의 형식으로 제목을 아래 공백줄에 작성
# 제목은 50자 이내 / 변경사항이 "무엇"인지 명확히 작성 / 끝에 마침표 금지
# 예) ✨ Feat: 로그인 기능 추가

# 바로 아래 공백은 지우지 마세요 (제목과 본문의 분리를 위함)

################
# 본문(구체적인 내용)을 아랫줄에 작성
# 여러 줄의 메시지를 작성할 땐 "-"로 구분 (한 줄은 72자 이내)

################
# 꼬릿말(footer)을 아랫줄에 작성 (현재 커밋과 관련된 이슈 번호 추가 등)
# 예) Fixes: #53 Related to: #17, #24
```


## 🖤 Commit Message Tag 

| 태그 이름| 설명 |
| :--: | :-----: |
| ✨ Feat | 새로운 기능을 추가하는 경우 |
| 🐛 Fix | 버그, 오류 해결 |
| 📝 Docs | README나 WIKI 등의 문서 개정 |
| ✅ Chore | 빌드 태스트 업데이트, 패키지 매니저를 설정하는 경우(프로덕션 코드 변경 X) |
| 🚑️ !HOTFIX | 급하게 치명적인 버그를 고쳐야하는 경우 |
| 💄 Style | 코드 포맷 변경, 세미 콜론 누락, 코드 수정이 없는 경우 |
| 🎨 design | CSS 등 사용자 UI 디자인 변경 |
| ⚰️ Delete | 쓸모없는 코드 삭제 |
| 🚚 Move | 프로젝트 내 파일이나 코드의 이동 |
| 🔥 Remove |	사용하지 않는 파일 혹은 폴더 삭제 |
| ⏪️ Rename | 파일 혹은 폴더 명 수정 |
| ♻️ Refactor | 프로덕션 코드 리팩토링, 새로운 기능이나 버그 수정없이 현재 구현을 개선한 경우 |
| 💡 Comment | 필요한 주석 추가 및 변경 |
| ⚡️ Test | 테스트 추가, 테스트 리팩토링(프로덕션 코드 변경 X) |
| 🧭 Dev | 개발 환경 세팅 |
| ➕ Add | Feat 이외의 부수적인 코드 추가, 라이브러리 추가, 새로운 파일 생성 시 |
| 🚧 In progress | 아직 완성하지는 못했지만 진행중인 부분을 커밋해야할 경우 |
| 🔀 Merge | 다른 브랜치를 merge 할 때 사용 |

