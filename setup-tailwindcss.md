## tailwindcss

npm install -D tailwindcss
npx tailwindcss init
และ  content: ["./index.css", "./src/**/*.{js,ts,jsx,tsx}"] ใน tailwind.config

ใส่ใน index.css
@tailwind base;
@tailwind components;
@tailwind utilities;

npm i -D postcss
npm i -D autoprefixer

และสร้างไฟล์ postcss.config.cjs

module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};

แก้ไข eslintrc ใน env:[ เพิ่ม node: true]

### ถ้าไม่ขึ้นปิดเปิด vscode ใหม่

npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p