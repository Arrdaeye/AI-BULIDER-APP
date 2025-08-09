#https:https://github.com/Arrdaeye/AI-BULIDER-APP.git
#ssh:git@github.com:Arrdaeye/AI-BULIDER-APP.git
Cli:gh repo clone Arrdaeye/AI-BULIDER-APP


## การสร้างและรันไฟล์ `server.mjs` (Node.js HTTP Server)

โค้ดที่คุณให้มาเป็นตัวอย่างของ HTTP Server ง่ายๆ ที่สร้างด้วย Node.js

**ขั้นตอนการสร้างไฟล์:**

1.  **เปิด Text Editor:** เปิดโปรแกรม Text Editor ที่คุณถนัด เช่น VS Code, Sublime Text, Notepad (บน Windows), TextEdit (บน macOS)
2.  **คัดลอกโค้ด:** คัดลอกโค้ด Javascript ด้านล่างนี้:
    ```javascript
    import { createServer } from 'node:http';

    const server = createServer((req, res) => {
      res.writeHead(200, { 'Content-Type': 'text/plain' });
      res.end('Hello World!\n');
    });

    // starts a simple http server locally on port 3000
    server.listen(3000, '127.0.0.1', () => {
      console.log('Listening on 127.0.0.1:3000');
    });

    // run with `node server.mjs`
    ```
3.  **บันทึกไฟล์:**
    * ไปที่เมนู `File` (ไฟล์) แล้วเลือก `Save As...` (บันทึกเป็น...)
    * ตั้งชื่อไฟล์ว่า `server.mjs`
    * **สำคัญ:** เลือก `Save as type` (ชนิดของไฟล์) เป็น `All Files (*.*)` เพื่อให้แน่ใจว่าไฟล์ถูกบันทึกเป็นนามสกุล `.mjs`
    * เลือกตำแหน่งที่ต้องการบันทึกไฟล์ (เช่น Desktop หรือ Folder ที่คุณสร้างไว้) แล้วกด `Save` (บันทึก)

**ขั้นตอนการรันไฟล์:**

1.  **เปิด Command Prompt หรือ Terminal:**
    * **Windows:** กดปุ่ม `Windows` บนคีย์บอร์ด พิมพ์ `cmd` แล้วกด `Enter`
    * **macOS:** ไปที่ `Applications` (แอปพลิเคชัน) -> `Utilities` (ยูทิลิตี้) -> เปิด `Terminal`
    * **Linux:** เปิด Terminal (โดยปกติจะอยู่ที่ `Ctrl` + `Alt` + `T`)
2.  **เปลี่ยนไปยัง Directory ที่เก็บไฟล์:** ใช้คำสั่ง `cd` (change directory) เพื่อไปยัง Folder ที่คุณบันทึกไฟล์ `server.mjs` ไว้
    * **ตัวอย่าง:** ถ้าคุณบันทึกไฟล์ไว้ที่ Desktop
        * **Windows:** `cd Desktop`
        * **macOS/Linux:** `cd ~/Desktop`
    * **ตัวอย่าง:** ถ้าคุณบันทึกไฟล์ไว้ใน Folder ชื่อ `my-node-app` ใน Documents
        * **Windows:** `cd Documents\my-node-app`
        * **macOS/Linux:** `cd ~/Documents/my-node-app`
3.  **รันคำสั่ง Node.js:** เมื่อคุณอยู่ใน Directory ที่ถูกต้องแล้ว ให้รันคำสั่งนี้:
    ```bash
    node server.mjs
    ```
4.  **ตรวจสอบผลลัพธ์:**
    * ถ้าไม่มีข้อผิดพลาดปรากฏใน Command Prompt หรือ Terminal คุณจะเห็นข้อความ `Listening on 127.0.0.1:3000` แสดงขึ้นมา นั่นหมายความว่า Server ของคุณกำลังทำงานอยู่
    * เปิด Web Browser (เช่น Chrome, Firefox, Safari) แล้วพิมพ์ `http://127.0.0.1:3000` ในช่อง URL แล้วกด `Enter`
    * คุณควรจะเห็นข้อความ `Hello World!` แสดงบนหน้าเว็บ

**คำอธิบายโค้ด:**

* `import { createServer } from 'node:http';`: บรรทัดนี้เป็นการนำเข้าฟังก์ชัน `createServer` จาก Module `http` ของ Node.js ซึ่งใช้สำหรับสร้าง Web Server
* `const server = createServer((req, res) => { ... });`: บรรทัดนี้สร้าง HTTP Server ใหม่ โดยมีฟังก์ชัน Callback ที่จะทำงานเมื่อมี Request เข้ามายัง Server
    * `req`: ตัวแปรที่เก็บข้อมูล Request ที่เข้ามา (เช่น URL, Headers)
    * `res`: ตัวแปรที่ใช้สำหรับส่ง Response กลับไปยัง Client (Web Browser)
    * `res.writeHead(200, { 'Content-Type': 'text/plain' });`: กำหนด HTTP Header ให้ Response โดยมี Status Code เป็น `200` (OK) และบอกว่า Content ที่จะส่งกลับไปเป็น Text ธรรมดา (`text/plain`)
    * `res.end('Hello World!\n');`: ส่งข้อความ `'Hello World!\n'` กลับไปยัง Client และปิดการเชื่อมต่อ
* `server.listen(3000, '127.0.0.1', () => { ... });`: สั่งให้ Server เริ่มทำงานและรอรับ Request ที่ Port `3000` บน IP Address `127.0.0.1` (localhost หรือเครื่องของเราเอง)
    * ฟังก์ชัน Callback ที่อยู่ภายใน `server.listen()` จะทำงานเมื่อ Server เริ่มทำงานเรียบร้อยแล้ว และจะแสดงข้อความ `Listening on 127.0.0.1:3000` ใน Console

**หมายเหตุ:**

* `server.mjs` เป็นการใช้รูปแบบ ECMAScript Modules (ES Modules) ซึ่งเป็นมาตรฐานใหม่ของ Javascript ใน Node.js ถ้าคุณใช้ไฟล์นามสกุล `.js` แบบเดิม อาจจะต้องใช้ `require` แทน `import`
* ในการหยุด Server ที่กำลังทำงานอยู่ ให้กลับไปที่ Command Prompt หรือ Terminal ที่คุณรันคำสั่ง `node server.mjs` แล้วกด `Ctrl` + `C`

ลองทำตามขั้นตอนดูนะเพื่อน! ถ้าติดตรงไหนถามมาได้เลย! 😊
