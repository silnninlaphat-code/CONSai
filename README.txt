CONS — เว็บ + AI จริง (Google Gemini)  ·  วิธีขึ้นเว็บ
======================================================

โครงไฟล์
  index.html        = หน้าเว็บแอป (ช่องแชต AI เรียก /api/chat)
  api/chat.js       = หลังบ้าน เรียก Google Gemini (เก็บคีย์ปลอดภัย)
  package.json      = ไฟล์โปรเจกต์

──────────────────────────────────────
ขั้น 1) เอาคีย์ Gemini (ฟรี)
  - ไปที่  https://aistudio.google.com
  - กด "Get API key" → Create API key → คัดลอกคีย์เก็บไว้

ขั้น 2) ขึ้น Vercel
  วิธี A (ไม่ต้องใช้ terminal) — แนะนำ
    1. แตกไฟล์ zip นี้
    2. ไป github.com → New repository → Upload files → ลากทุกไฟล์/โฟลเดอร์เข้าไป → Commit
    3. ไป vercel.com → Add New… → Project → Import โปรเจกต์ GitHub อันนี้ → Deploy
  วิธี B (terminal)
    1. ติดตั้ง:  npm i -g vercel
    2. แตก zip แล้ว:  cd cons-web
    3. รัน:  vercel   (ตอบตามคำถาม จะได้ลิงก์)

ขั้น 3) ใส่คีย์ใน Vercel
  - Vercel → โปรเจกต์ → Settings → Environment Variables
  - เพิ่ม:  Name = GOOGLE_API_KEY   Value = (คีย์จาก AI Studio)
  - กด Save แล้ว Redeploy  (เมนู Deployments → ปุ่ม … → Redeploy)

ขั้น 4) ลองใช้
  - เปิดลิงก์เว็บ → พิมพ์ในช่อง "ถาม AI ผู้ช่วย" ด้านล่าง → Gemini ตอบจริง

──────────────────────────────────────
ข้อควรระวัง
  • /api/chat เปิดสาธารณะ (ยังไม่มีระบบล็อกอิน) ใครรู้ลิงก์ก็ยิงใช้ได้
    → ตั้ง quota/งบใน Google Cloud และอย่าปล่อยลิงก์กว้าง จนกว่าจะใส่ระบบสมาชิก (ขั้นต่อไป)
  • Free tier มีลิมิตจำนวนครั้งต่อนาที ถ้าเกินจะ error ชั่วคราว
  • AI อื่น (เจนภาพ/วิดีโอ/เรนเดอร์/SketchUp) ยังเป็นการจำลอง
    → อยากเจนภาพจริงด้วย Google ใช้ Imagen/Veo ได้ บอกมาเดี๋ยวต่อให้
