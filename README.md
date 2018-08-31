# Druwa-Development-Guide

Druwa developement Guide

## 개발환경 셋팅하기

본 가이드는 MacOS 를 기준으로 작성되었습니다. Windows 도 비슷할 것이라 예상합니다.

### 필요한 소프트웨어

- Editor: Visual Studio Code (https://code.visualstudio.com/) 현재까지 `TypeScript`에 대한 지원이 가장 좋습니다.
- MongoDB GUI - Robo 3T (https://robomongo.org/download)
- Git Manager - SourceTree (https://www.sourcetreeapp.com/)
- API Tester - Postman (https://www.getpostman.com/)

### Visual Studio Code

Visual Studio Code 개발환경 Setting 가이드입니다.

#### Visual Studio Code 플러그인 설치

VSCode 에서 유용한 플러그인들을 설치해줍니다.

1. Prettier (Requirement) - 코드를 Lint 에 맞춰서 예쁘게 정돈해주는 플러그인
2. ESLint (Requirement) - JavaScript Lint 검사해주는 플러그인
3. TSLint (Requirement) - TypeScript Lint 검사해주는 플러그인
4. Path Intellisense (Optional)
5. TypeScript Importer (Optional)

#### 기타 VSCode 설정들

Mac OS 를 기준으로 `Cmd + ,`를 눌러서 환경설정을 다음과 같이 해줍니다.

```json
{
  "workbench.colorTheme": "Atom One Dark",
  "atomKeymap.promptV3Features": true,
  "editor.multiCursorModifier": "ctrlCmd",
  "editor.tabSize": 2,
  "prettier.eslintIntegration": true,
  "eslint.autoFixOnSave": true,
  "tslint.autoFixOnSave": true,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "[sql]": {
    "editor.formatOnSave": false
  },
  "workbench.startupEditor": "newUntitledFile",
  "workbench.editor.enablePreviewFromQuickOpen": false,
  "workbench.editor.enablePreview": false,
  "editor.fontSize": 14,
  "window.zoomLevel": 0,
  "terminal.integrated.rendererType": "dom",
  "typescript.updateImportsOnFileMove.enabled": "never"
}
```

### Git Version Manager

Git Version Manager 는 `SourceTree`를 사용합니다. GUI 기반으로 사용하기 쉽고, 브랜치 확인이 용이하며, 분할 Commit 이 간편합니다.

- Download - https://www.sourcetreeapp.com/

### Git Commit Convention

개발자에게 있어서 Commit Message 를 작성하는 것은 매우 중요한 작업입니다. Message 만 보고, 이 Commit 이 어떠한 작업에 대한 Commit 인지 한 번에 알 수 있도로 작성합니다.
기본적으로 영문으로 작성하는 것을 원칙을 추천합니다.

**Commit Message 기본 룰**

```
작업한 메인 파일: 작업내용

See: Github issue #GITHUB_ISSUE_NUMBER (해당하는 Issue가 없을 경우 Skip)
```

**Commit Message 예시**

```
GithubController: Create new API feature to create new room

See: Github issue #11
```

## 작업 시작하기

개발을 시작하기에 앞서 전반적인 개발 프로세스에 대해서 설명합니다.

- Kanban Board - Zenhub (https://chrome.google.com/webstore/detail/zenhub-for-github/ogcgkffhplmphkaahpmffcafajaocjbd)

칸반보드를 사용하여 전체 소프트웨어 개발 상황을 한 눈에 확인할 수 있도록 합니다.

1. **이슈 생성하기**
   작업을 시작하기전에 앞서서 Github 이나, Zenhub 를 통해 Issue 를 생성합니다. Issue 에는 앞으로 해야할 작업들을 간단하게 적어 놓습니다.

2. **작업 Assign**
   어떠한 Issue 가 자신에게 Assign 되면, 작업을 시작할 때 Kanban Board 에서 `In Progress`로 Issue 를 옮깁니다.

3. **Branch 분기**
   `In Progress`로 Issue 로 옮긴 후, 자신의 개발 과정이 `master` Branch 에 영향을 받지 않도록 `DR-WEB#이슈번호` or `DR-BACK#이슈번호`로 Branch 를 분기한 후 작업합니다.

4. **Pull Request (PR)**
   해당 Issue 에 대한 개발이 완료되면 PR 을 생성합니다. PR 에는 다른 Reiewer 들이 전반적인 작업내용을 알기 쉽도록 개발 내용을 요약하여 작성하고, 해당 Issue 번호를 Mention 해줍니다.

PR 작성 양식

```
Related with #이슈번호

* 작업내용1
* 작업내용2
* 작업내용3
```

이렇게 PR 을 작성한 후 Reviwer 에 다른 팀원들을 추가합니다.

팀원들은 Review Request 를 받으면 최대한 빠른 시일 내에 Review 를 해주고 `Approve`혹은 `Deny`를 해줍니다.

최소 한 명 이상 `Approve`를 받았다면, 그 때 `master` branch 와 Merge 합니다.

> Merge 가 Conflict 날 경우에는 `origin/master` branch 를 기준으로 `rebase`를 한 다음 다시 PR 을 요청합니다.

5. **Close Issue**
   성공적으로 `Merge`가 되었다면, 관련된 Issue 를 Close 하고 다음 Issue 를 Assign 받아 다시 개발을 시작합니다.
