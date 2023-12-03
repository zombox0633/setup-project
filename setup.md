ก่อนสร้าง project
1. ในเครืองเราไม่เกี่ยวกับและลงแค่ครั้งเดียว project  https://github.com/antfu/ni
2. ลง fnm ในเครืองเราไม่เกี่ยวกับและลงแค่ครั้งเดียว  project คือ Fast Node Manager  https://github.com/Schniz/fnm


1. สร้าง .nvmrc ใส่ version คือต้องการใช้งาน
2. กำหนด extensions.json และ settings.json ใน project
3. สร้าง .prettierrc หรือใช้ prettier.config.cjs
4. "format":"prettier . --write" ใน package.json และ "check-format": "prettier . --check"  https://prettier.io/docs/en/cli   
5. ลง eslintrc.cjs แต่ถ้าใช้ vite มันมีให้อยู่แล้ว
6. ทำให้ eslint อยู่กับ prettier ได้โดยลง npm install --save-dev eslint-config-prettier   https://github.com/prettier/eslint-config-prettier
7. https://airbnb.io/javascript/react/