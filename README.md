# สรุปขั้นตอนการพัฒนาเว็บไซต์ (Web Development Steps)

เอกสารนี้สรุปขั้นตอนหลักในการสร้างเว็บไซต์ พร้อมตัวอย่างโค้ดเบื้องต้นเพื่อให้เห็นภาพรวม

## 1. Planning & Design (วางแผนและออกแบบ)
ก่อนเริ่มเขียนโค้ด ต้องรู้ว่าทำเว็บอะไร เพื่อใคร และหน้าตาเป็นอย่างไร
- **Requirement Gathering**: รวบรวมความต้องการ
- **Sitemap**: ผังหน้าเว็บไซต์
- **Wireframe/Mockup**: แบบร่างหน้าจอ (UI Design)

---

## 2. Frontend Development (ส่วนหน้าบ้าน)
ส่วนที่ผู้ใช้มองเห็นและใช้งานโดยตรง
- **HTML**: โครงสร้างหน้าเว็บ
- **CSS**: ความสวยงามและจัดวาง (Layout)
- **JavaScript**: การทำงานโต้ตอบ (Logic)

### ตัวอย่างโค้ด Frontend

**index.html** (โครงสร้าง)
```html
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <title>เว็บไซต์ของฉัน</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>ยินดีต้อนรับ</h1>
        <button id="clickMeBtn">คลิกฉันสิ</button>
        <p id="message"></p>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

**style.css** (ตกแต่ง)
```css
body {
    font-family: sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    background: white;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    text-align: center;
}

button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
```

**script.js** (การทำงาน)
```javascript
const button = document.getElementById('clickMeBtn');
const message = document.getElementById('message');

button.addEventListener('click', () => {
    message.textContent = "สวัสดี! นี่คือข้อความจาก JavaScript";
    alert("คุณคลิกปุ่มแล้ว!");
});
```

---

## 3. Backend Development (ส่วนหลังบ้าน)
ส่วนประมวลผลข้อมูล เชือมต่อฐานข้อมูล และ API
- **Language**: Node.js, Python, PHP, Java
- **Database**: SQL (MySQL, PostgreSQL) หรือ NoSQL (MongoDB)

### ตัวอย่างโค้ด Backend (Node.js + Express)

**server.js**
```javascript
const express = require('express');
const app = express();
const port = 3000;

// สร้าง API ง่ายๆ
app.get('/', (req, res) => {
    res.send('Hello World! นี่คือ Backend Server');
});

app.get('/api/data', (req, res) => {
    res.json({ 
        id: 1, 
        name: "ตัวอย่างข้อมูล", 
        status: "success" 
    });
});

app.listen(port, () => {
    console.log(`Server กำลังรันที่ http://localhost:${port}`);
});
```

---

## 4. Testing (ทดสอบ)
ตรวจสอบความถูกต้องของระบบ
- **Unit Testing**: ทดสอบฟังก์ชั่นย่อยๆ
- **Integration Testing**: ทดสอบการทำงานร่วมกันของระบบ
- **User Acceptance Testing (UAT)**: ให้ผู้ใช้ทดสอบจริง

---

## 5. Deployment (นำขึ้นออนไลน์)
นำโค้ดไปวางบน Server เพื่อให้คนอื่นเข้าถึงได้
- **Hosting/Cloud**: Vercel, Netlify (สำหรับ Frontend), AWS, DigitalOcean, Heroku (สำหรับ Backend)
- **Domain Name**: จดชื่อโดเมน (เช่น .com, .net)

---

## 6. Maintenance (ดูแลรักษา)
- อัปเดตแพทช์ความปลอดภัย
- แก้ไข Bugs ที่เกิดขึ้น
- เพิ่มฟีเจอร์ใหม่ๆ ตามความต้องการ
