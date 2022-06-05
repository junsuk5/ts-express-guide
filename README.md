# typescript + express 환경

```bash
npm init --yes
npm install express
```

ts 의존성 추가
```bash
npm i -D typescript @types/express @types/node
```

tsconfig.json 작성 및 수정
```base
npx tsc --init

{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"

    // rest options remain same
  }
}
```


```bash
npm install -D concurrently nodemon
```

스크립트 추가
```json
{
  "scripts": {
    "build": "npx tsc",
    "start": "node dist/index.js",
    "dev": "concurrently \"npx tsc --watch\" \"nodemon -q dist/index.js\""
  }
}
```

npm run dev 로 실행