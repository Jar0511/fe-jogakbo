# ESLint + Prettier 설정하기

## 방법

https://eslint.org/docs/latest/use/configure/configuration-files
https://prettier.io/docs/en/

1. vscode인 경우 [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) 확장 프로그램 설치
2. 앞서 vite로 `react-ts` 탬플릿 프로젝트 생성을 했다면 eslint는 이미 설치된 상태이므로 prettier만 추가로 설치하면 된다

   ```bash
   yarn add -D prettier
   ```

   이후, 이미 존재하는 eslint 설정 파일(eslint.config.js)을 커스터마이징해서 구성하면 된다

   > [본 프로젝트](../eslint.config.mjs)는 이전에 사용하던 eslint 설정 파일을 마이그레이션 cli를 사용해서 가져왔다.
   >
   > https://eslint.org/docs/latest/use/configure/migration-guide
   >
   > ```bash
   > npx @eslint/migrate-config .eslintrc.cjs
   > ```

3. 설정이 완료된 후, vscode의 우측 아래에서 1) prettier 단어 왼쪽에 이중 체크 아이콘이 표시되고, 2) language mode 버튼 좌측 `{ }` 아이콘에서 적용 중인 eslint 및 prettier 상태를 확인할 수 있다

## 플러그인

- eslint와 prettier간 충돌 방지

  ```bash
  yarn add -D eslint-plugin-prettier eslint-config-prettier
  ```

- eslint와 prettier의 typescript 지원
  ```bash
  yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-import-resolver-typescript
  ```
- react 환경

  ```bash
  yarn add -D eslint-plugin-react eslint-plugin-jsx-a11y
  ```

- airbnb 설정

  ```bash
    yarn add -D eslint-config-airbnb eslint-config-airbnb-base
  ```

- import 위계 규칙
  ```bash
  yarn add -D eslint-plugin-import
  ```
