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
