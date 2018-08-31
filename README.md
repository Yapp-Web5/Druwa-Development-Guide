# Druwa-Development-Guide

Druwa developement Guide

## 개발환경 셋팅하기

본 가이드는 MacOS 를 기준으로 작성되었습니다. Windows 도 비슷할 것이라 예상합니다.

- Editor: Visual Studio Code (https://code.visualstudio.com/) 현재까지 `TypeScript`에 대한 지원이 가장 좋습니다.
- MongoDB GUI - Robo 3T (https://robomongo.org/download)

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
Download - https://www.sourcetreeapp.com/

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
