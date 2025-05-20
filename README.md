📘 README: ระบบ OKRs (Version 1.0)
📌 วัตถุประสงค์
ระบบ OKRs นี้ถูกออกแบบมาเพื่อให้พนักงานสามารถ

เพิ่ม/แก้ไข Objectives และ Key Results

อ้างอิง Objective/KR จากผู้บังคับบัญชา

กำหนดประเภท KR, หน่วย, ระยะเวลา, และ Sweet Spot

ตรวจสอบและบันทึก Log ทุกการกระทำ

🧩 ส่วนประกอบหลักของระบบ
✅ แท็บ Add/Edit OKR
ส่วน	คำอธิบาย
ชื่อบุคคล (ตนเอง)	แสดงชื่อผู้ใช้งานที่เลือกจาก list
ชื่อบุคคล (ผู้บังคับบัญชา)	แสดงชื่อผู้บังคับบัญชาของผู้ใช้งาน
lstMyObjectives	รายการ Objective ของตนเอง
lstObjectivesManager	รายการ Objective ของผู้บังคับบัญชา
lstMyKRs	รายการ Key Result ของตนเอง
lstKRsManager	รายการ Key Result ของผู้บังคับบัญชา
txtObjectiveTitle, txtObjectiveDesc	ช่องกรอกข้อมูล Objective
txtKRTitle, cmbKRType, txtInitValue, txtTargetValue, cmbKRUnit, txtSweetSpot, cmbKRDuration	ช่องกรอกข้อมูล Key Result
ปุ่มต่างๆ	เพิ่ม/แก้ไข/ลบ Objective หรือ Key Result ตามสิทธิ์
Tooltips	Checkbox ใช้แสดง preview tooltip mouse-over list

⚙️ แท็บ Setting
สำหรับผู้ดูแลระบบหรือ Admin ปรับค่าต่างๆ:

ประเภทการวัดผล (KR Type): เพิ่ม/ลบผ่าน txtNewKRType, lstKRTypeSetting

หน่วยการวัด (Unit): เพิ่ม/ลบผ่าน txtNewUnit, lstUnitSetting

ระยะเวลาติดตามผล: เช่น ทุกไตรมาส, ทุกเดือน

Sweet Spot: กำหนดจุดประเมินค่าเหมาะสม (default = 0.70)

📄 Sheet ที่ระบบใช้
Sheet	หน้าที่
Objectives	เก็บข้อมูล O ของพนักงาน
KeyResults	เก็บข้อมูล KR ของแต่ละ Objective
Employees	รายชื่อพนักงานและสายบังคับบัญชา
Setting	ประเภท KR, หน่วย, ระยะเวลา และค่า sweet spot
Log	Log การกระทำของผู้ใช้ เช่น เพิ่ม/ลบ/แก้ไข

🔐 สิทธิ์การใช้งาน
ดูข้อมูลของผู้บังคับบัญชา: ได้เฉพาะในรูปแบบ read-only (SetControlsReadOnly(True))

เพิ่ม/ลบ/แก้ไข: ทำได้เฉพาะ Objective/KR ของตนเอง

การ Log ทุก action: ใช้ฟังก์ชัน LogAction พร้อมระบุรายละเอียดชัดเจน

🏁 ขั้นตอนการใช้งานเบื้องต้น
ผู้ใช้เลือกชื่อจาก list (Live search)

ระบบโหลด Objective/KR ของตนเองและผู้บังคับบัญชา

สามารถเพิ่ม Objective ใหม่ได้

เพิ่ม KR ภายใต้ Objective

ตั้งค่า KRType, Unit, Duration ได้จาก Setting

ทุก action มีการบันทึก Log เพื่อ audit

🧾 การติดตั้ง (เบื้องต้น)
เปิดไฟล์ Excel ที่มี Macro (.xlsm)

เปิดใช้งาน Macro

ตรวจสอบให้มี sheet:

Objectives, KeyResults, Employees, Setting, Log

แนะนำให้ป้องกัน (protect) Sheet สำหรับ Setting และ Log

🛠 รายการอัปเดตใน Version 1.0
เพิ่ม Objective/KR ได้

ดึง Objective/KR จากผู้บังคับบัญชา

กำหนด sweet spot และระยะเวลาได้

ระบบบันทึก log ทุกการกระทำ

แยกสิทธิ์ read-only ตามตำแหน่งในลำดับบังคับบัญชา

⚠️ ข้อควรระวัง
ห้ามเปลี่ยนชื่อชีตที่ระบบใช้งาน

ไม่ควรลบข้อมูลแถวใน Setting, Objectives, KeyResults, Employees โดยตรง

Format ตัวเลข เช่น Init/Target ควรใช้ format “#,##0”
