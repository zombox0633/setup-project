ก่อนสร้าง project
1. ตรวจสอบ version node.js ในเครื่องและใช้เพราะ version node.js ที่เป็นเลขคู่
2. ลง chocolatey ก่อนลงแบบ admin ก็จะใช้งานข้อ 3 ได้
3. ในเครืองเราไม่เกี่ยวกับและลงแค่ครั้งเดียว project  https://github.com/antfu/ni
4. ลง fnm ในเครืองเราไม่เกี่ยวกับและลงแค่ครั้งเดียว  project คือ Fast Node Manager  https://github.com/Schniz/fnm (ยังไมเข้าใจการทำงาน)


## สร้าง .nvmrc ใส่ version คือต้องการใช้งาน
  คือการกำหนด version node.js ที่จะใช้งานผู้ที่เอา project นี้ให้ผู้จะใช้เข้าใจว่าต้องการให้ต้องใช้งาน node.JS version อะไร
  และ ทำการเพิ่ม

  "engines": {
    "node": ">=20.10.0"
  },

  ใน package.json วิธีนี้ไม่จำเป็นจะเปลี่ยนเวอร์ชั่น Node.js ที่รันในเครื่องของคุณ แต่จะเป็นการแสดงข้อกำหนดเวอร์ชั่นเพื่อให้ผู้ใช้งานรู้ว่าต้องใช้เวอร์ชั่นไหน (เพิ่มตัวใดตัวหนึ่งหรือทั้งสองก็ได้)

## กำหนด extensions.json และ settings.json ใน project
คือการกำหนดเงือนไขในการระบบ extensions และ settings ที่ต้องใช้หรือที่ผู้สร้างคิดว่าต้องใช้ใน project

  1. การกำหนด extensions.json ใน project ทำดังนี้ เข้าไปที่ Extensions (Ctrl + Shift + X) -> เลือก Extensions ที่ต้องการใช้งาน project -> กด ฟันเฟือง(Manage) -> และกด add to workspace recommedations
   
  2. การกำหนด settings.json ใน project ทำดังนี้ เข้าไปที่ Manage -> แล้วเข้าไปที่ workspace -> เลือก open settings (json) ที่เป็นรูปกระดาษด้านบนขวาเมื่อกดและจะทำให้เกิดไฟล์ settings.json มันคือการทำให้เครื่องที่ clone project จะทำการ settings vscode ตามเจ้าของ project แต่จะเปลี่ยนเฉพาะ project นี้เท่านั้น

## กำหนด prettier หรือรูปแบบการจัดเรียง code
   1. สร้าง .prettierrc หรือสร้าง prettier.config.cjs ก็ได้

   2. กำหนดการจัดรูปแบบในไฟล์
   
   3. กำหนดคำสั่งใน package.json 
      "format":"prettier . --write" คือการจัดรูปแบบตามที่กำหนดใน prettier และ
       "check-format": "prettier . --check" ตรวจสอบเงือนไข format ของ prettier
       
       ในส่วน scripts ตาม https://prettier.io/docs/en/cli   

## ลง eslintrc.cjs
  คือเงือนไขในการเขียน code ใน project แต่ถ้าใช้ vite มันมีให้อยู่แล้ว

  1. การใช้ eslintrc ในการตั้งค่าแบบ airbnb (https://airbnb.io/javascript/react/) หรือจำกำการ custom เองก็ขึ้นอยู่กับเงื่อนไขของทีมหรือเจ้าของ project
  2. กำหนดคำสั่งใน package.json  "lint": "eslint . --ext ts,tsx --report-unused-disable-directives --max-warnings 0" ทำการแจ้งเตือนและตรวจสอบ


## ทำให้ eslint อยู่กับ prettier ได้โดยลง npm install --save-dev eslint-config-prettier
  https://github.com/prettier/eslint-config-prettier

## การตั้งค่าให้เมื่อ commit code ทำการเช็คเงือนไขและทำตาม scripts ที่ตั้งค่าไว้ใน husky ***
1. ทำการ git init ,add , commit เสร็จแล้วทำตาม  https://typicode.github.io/husky/getting-started.html 
