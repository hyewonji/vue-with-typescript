## Vue 프로제그에 타입스크립트를 점진적으로 적용하는 방법

1. Vue + Typescript 프로젝트 생성 (라이브러리, css 등이 덜 깨진다)
2. 기존 서비스 코드와 라이브러리를 새 프로젝트에 이동
3. 기본적인 빌드 에러 해결
4. 타입스크립트 혜택을 볼 수 있는 주요 파일들 위주로 .js -> .ts로 변환하며 적용

팁 : 타입 체킹 정도는 덜 엄격한 방식에서 점점 엄격한 방식으로 적용하는 것을 추천

## Step by Step

1. **tsconfig.json**

```
  "strict": false,
  "noImplicitAny": false,
  "allowJs": true,
```
위와같이 변경해서 타입 체킹 레벨을 낮추고 빌드 에러를 해결한다.

2. **App.vue**
  ```
    "noImplicitAny": true,
  ```
  1단계에서 빌드에러를 해결했다면, tsconfig.json 파일을 위와같이 수정한다.
  또한, <script/> 내부의 코드를 `<script/> typescript.vue`로 옮겨준다.

3. .js -> .ts
  `src/main.js`, `src/routes/index.js`, `src/views/CreateListView.js` 파일을 .ts 확장자로 변경해준 후,
  발생하는 에러를 수정한다.( 필요한 타입을 정의해준다. )
