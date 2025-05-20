
📘 OKRs System – Excel + VBA (Version 1.0.0)
=================================================

ระบบติดตามและประเมินผล OKRs ภายในองค์กร พัฒนาโดยใช้ Excel + VBA พร้อม UserForm ที่ใช้งานง่าย แยกสิทธิ์การเข้าถึงตามลำดับบังคับบัญชา

🔖 Version History
| Version | Release Date | Summary | Developer | Note |
|---------|--------------|---------|-----------|------|
| 1.0.0   | 2025-05-20    | เปิดตัวระบบติดตาม OKRs บน Excel ด้วย VBA พร้อม UserForm ที่ใช้งานง่าย รองรับการเพิ่ม ลบ แก้ไข Objectives และ Key Results พร้อมระบบ Log อย่างละเอียด ระบบนี้รองรับการตั้งค่า KR Type, หน่วย, ระยะเวลา และ sweet spot จากส่วนกลาง พร้อมสิทธิ์แบบ read-only สำหรับข้อมูลของผู้บังคับบัญชา เหมาะสำหรับการทดลองใช้ภายในองค์กรขนาดเล็กถึงกลาง | x | เวอร์ชันทดสอบภายใน |

👤 ส่วนที่ 1: สำหรับผู้ใช้งานทั่วไป
--------------------------------------

✅ สิ่งที่ทำได้
- สร้าง / แก้ไข / ลบ Objective ของตนเอง
- สร้าง / แก้ไข / ลบ Key Result ภายใต้ Objective ของตนเอง
- ดู Objective และ Key Result ของผู้บังคับบัญชา (แบบอ่านอย่างเดียว)
- กำหนดประเภท KR, หน่วย, ระยะเวลา (เลือกจากที่องค์กรตั้งไว้)
- ตรวจสอบ sweet spot สำหรับการประเมินผล
- กดบันทึกเพื่อสำรองข้อมูล

🧭 วิธีเริ่มต้นใช้งาน
1. เปิดไฟล์ Excel (.xlsm) แล้ว อนุญาตให้ใช้ Macro
2. ระบบจะโหลดฟอร์มอัตโนมัติ หรือกดปุ่ม `Launch OKR System`
3. พิมพ์ชื่อของคุณในช่อง `ค้นหาชื่อ`
4. ระบบจะโหลด Objectives และ KRs ของคุณ รวมถึงของหัวหน้า
5. เลือกหรือสร้าง Objective ใหม่ แล้วเพิ่ม Key Result ได้ตามต้องการ
6. ใช้ปุ่มต่างๆ เช่น เพิ่ม/แก้ไข/ลบ
7. หากต้องการบันทึกเวอร์ชันใหม่ ให้กด `บันทึกสำเนาไฟล์`

📌 คำแนะนำและข้อควรระวัง
- ใช้ค่าที่องค์กรกำหนดไว้ เช่น KR Type, Unit, Duration
- อย่าลบ/เปลี่ยนชื่อ Sheet ใดๆ
- การเปลี่ยนแปลงทุกครั้งจะถูกบันทึกใน Log อัตโนมัติ
- ระบบมีสิทธิ์จำกัด ผู้ใช้ไม่สามารถแก้ไข KR ของหัวหน้าได้

💼 ส่วนที่ 2: สำหรับผู้พัฒนา / ฝ่าย IT
-----------------------------------------

🛠 โครงสร้างไฟล์ & Sheet ที่ใช้
| Sheet | หน้าที่ |
|-------|----------|
| Objectives | เก็บ Objective ของพนักงาน |
| KeyResults | เก็บ KR ผูกกับ Objective |
| Employees | รายชื่อพนักงาน พร้อม Manager ID |
| Setting | ค่าเริ่มต้น เช่น KR Type, Unit, Duration, Sweet Spot |
| Log | Log การกระทำ เช่น ADD, EDIT, DELETE |
| Dashboard (แนะนำ) | สำหรับสรุปผล OKRs |

🧩 Control Overview (UserForm1)
| Control | ใช้ทำอะไร |
|---------|------------|
| lstEmployees | ค้นหา/เลือกพนักงาน |
| lstMyObjectives / lstObjectivesManager | รายการ Objectives |
| lstMyKRs / lstKRsManager | รายการ Key Results |
| txtObjectiveTitle / txtKRTitle | ช่องกรอกข้อมูล |
| cmbKRType, cmbKRUnit, cmbKRDuration | ComboBox ค่าที่ตั้งจาก Setting |
| txtInitValue, txtTargetValue, txtSweetSpot | ค่าตัวเลขที่ใช้ประเมิน |
| ปุ่ม Add/Edit/Delete | ดำเนินการกับข้อมูล (มี Log ทุกครั้ง) |
| lbVersion | แสดงเวอร์ชันจาก Setting!B1 |

🧾 ฟังก์ชันสำคัญ (Module1)
- LogAction: บันทึกกิจกรรมลง sheet Log
- SetControlsReadOnly(True/False): ควบคุมสิทธิ์แก้ไข

🧪 Version Control
- เก็บไว้ที่ Setting!B1 เช่น "1.0.0"
- แสดงผ่าน github

💾 Format ชื่อไฟล์เมื่อบันทึก
OKR_v1.0.0_20250520_104530.xlsx
