# tsconfig와 절대 경로

https://www.typescriptlang.org/tsconfig/

vite는 자동으로 3개의 tsconfig 파일을 생성하는데 커스텀은 보통 `tsconfig.app.json`에서 처리하게 된다.

## 절대 경로 설정하기

참조 경로를 비교적 단순하게 작성할 수 있도록 경로에 별칭을 붙여주는 방법이다.

1. `tsconfig.app.json`에 다음과 같이 추가한다

   ```json
   {
     "compilerOptions": {
       "baseUrl": "root 경로",
       "paths": {
         "alias": ["실제/경로"]
       }
     }
   }
   ```

2. 패키지를 추가한다.

   ```bash
   yarn add -D vite-tsconfig-paths
   ```

3. vite 설정을 수정한다.

   ```ts
   // vite.config.ts
   import { defineConfig } from 'vite';
   import react from '@vitejs/plugin-react';
   import tsconfigPaths from 'vite-tsconfig-paths';

   export default defineConfig({
     plugins: [react(), tsconfigPaths()],
     cacheDir: './.vite',
   });
   ```
