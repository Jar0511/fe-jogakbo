# Yarn Berry로 이전하기

https://yarnpkg.com/migration/guide

> yarn berry는 node 18+부터 사용 가능

1.  ```bash
    corepack enable
    ```
2.  프로젝트 위치에서 실행
    ```bash
    yarn set version berry
    ```
3.  (프로젝트 생성 후 `yarn install`을 수행했다면 `.yarnrc`파일을 제거하고) `.yarnrc.yml`파일 생성하기
4.  **typescript, eslint, prettier**를 사용할 경우 sdk 설치를 해줘야 정상적으로 작동한다. 해당 패키지 관련 설치 및 설정을 마친 후 아래와 같이 프로젝트에 추가할 수 있다.
    https://yarnpkg.com/getting-started/editor-sdks
    ```bash
    # vscode를 사용하는 경우
    yarn dlx @yarnpkg/sdks vscode
    ```

### PnP와 vite 임시 폴더

---

https://vite.dev/config/

[본 프로젝트](../.yarnrc.yml)에서는 pnp 방식을 택하고 있으므로 `node_modules` 폴더를 사용하지 않는다. 따라서 vite가 서버를 구동할 때 사용하는 기본 경로를 수정했다.

```ts
// vite.config.ts
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

// https://vite.dev/config/
export default defineConfig({
  plugins: [react()],
  cacheDir: './.vite',
});
```

깃에 올라가지 않도록 `gitignore` 파일에도 추가해준다.

```bash
# .gitignore
.vite
```
