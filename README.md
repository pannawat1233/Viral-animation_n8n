AI Viral Animation Generator Workflow

Workflow นี้ใช้สำหรับสร้างวิดีโอคอนเทนต์แบบ Viral Animation อัตโนมัติจากรูปสินค้า โดยใช้ AI วิเคราะห์สินค้า → สร้าง Storyboard → Generate ภาพ → Generate วิดีโอ → บันทึกข้อมูลลง DataTable

Process หลักประกอบด้วย:

1 Schedule Trigger เริ่ม Workflow อัตโนมัติตามเวลาที่กำหนด

2 กำหนดค่า Product URL, Product ID และ System Prompt ผ่าน Edit Fields

3 ใช้ Google Gemini วิเคราะห์ภาพสินค้า เพื่อระบุว่าเป็นสินค้าอะไร ใช้ทำอะไร และเหมาะกับใคร

4 AI สร้าง Title, Short Description และ Top 3 Hashtags

5 Agent สร้าง Cinematic Storyboard แบบ 4 Scene (Video Prompt + Image Prompt)

6 Structured Output Parser แปลงผลลัพธ์ให้อยู่ใน JSON Schema

7 Loop ประมวลผลทีละ Scene

Generation Pipeline:

1 ส่ง Image Prompt ไปสร้างภาพผ่าน Text-to-Image API

2 ตรวจสอบสถานะงานจนภาพสร้างเสร็จ

3 ใช้ภาพ Reference ส่งไปสร้าง Video ผ่าน Veo Video API

4 ตรวจสอบสถานะจนวิดีโอสร้างเสร็จ

Final Output:

1 ได้วิดีโอแบบ 9:16 พร้อมบทพูดและ Story Animation

2 Short Description และ Top Hashtags สำหรับโพสต์โซเชียล

3 บันทึก Video URL และ Metadata ลง DataTable อัตโนมัติ

เหมาะสำหรับ:

1 TikTok / Reels / Shorts Automation

2 Product Marketing Content

3 AI Content Factory Pipeline

วิธีใช้งาน (Setup)

1 สร้าง API Key จาก Google Gemini แล้วนำไปใส่ใน Credential ของ Google Gemini ใน n8n

2 สมัครและนำ API Key ของ Phaya API มาใส่ใน HTTP Header Auth สำหรับ Image และ Video Generation

3 ตั้งค่า Product URL หรือข้อมูลสินค้าที่ต้องการ จากนั้นเปิดใช้งาน Workflow และ Run ตาม Schedule ได้ทันที

Credit: Workflow โดย BoomBigNose
<h1> N8N <h1>    
