npm init
npm install typescript ts-node @types/node --save-dev
npm install --save-dev nodemon

สร้างไฟล์ tsconfig.json

{
  "compilerOptions": {
    "target": "ES2020",
    "module": "CommonJS",
    "strict": true,
    "esModuleInterop": true,
    "outDir": "dist"
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
}

สร้าง nodemon.json
{
  "watch": ["src"],
  "ext": "ts",
  "ignore": ["src/**/*.spec.ts"],
  "exec": "ts-node ./src/index.ts"
}

และกำหนด package.json
"scripts": {
    "dev": "nodemon",
    "build": "tsc --project ./"
  },