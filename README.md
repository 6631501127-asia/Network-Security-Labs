# Network System Security Labs #
โครงการนี้เป็นการรวบรวมใบงานและผลการทดลองในรายวิชา Network System Security โดยเน้นการจำลองและออกแบบระบบรักษาความปลอดภัยเครือข่ายด้วย Cisco ASAv Firewall บนโปรแกรม GNS3

โครงสร้างโปรเจกต์ (Project Structure)
1. Firewall Policy & NAT Configuration
การจัดการนโยบายความปลอดภัยและเทคนิคการแปลงที่อยู่เครือข่าย (NAT) เพื่อป้องกันโครงสร้างพื้นฐานภายใน
NAT Policy Implementation: การตั้งค่า Static และ Dynamic NAT เพื่อควบคุมการรับส่งข้อมูลระหว่างเครือข่ายภายในและภายนอกอย่างปลอดภัย
Security Documentation: รายงานผลการทดสอบระบบ NAT และนโยบายไฟร์วอลล์ฉบับสมบูรณ์ในรูปแบบไฟล์ PDF
Reference Files: NAT-Policy-FW_6631501127.pdf, FW-lab1_6631501127.txt

2. Security Zone Segmentation
การแบ่งแยกโซนความปลอดภัย (Perimeter Security) เพื่อควบคุมระดับสิทธิ์ในการเข้าถึงข้อมูลผ่านอินเทอร์เฟซต่างๆ:
Inside Interface (Gi0/1): Security Level 100 (IP: 10.0.0.1/24) — โซนเครือข่ายภายในที่มีความปลอดภัยสูงสุด
DMZ Interface (Gi0/2): Security Level 50 (IP: 172.16.0.1/24) — โซนสำหรับเซิร์ฟเวอร์ที่ต้องการการเข้าถึงจากภายนอกอย่างจำกัด
Outside Interface (Gi0/0): Security Level 0 — โซนเชื่อมต่ออินเทอร์เน็ตสาธารณะ (รับ IP ผ่าน DHCP)

เครื่องมือและเทคโนโลยีที่ใช้ (Tech Stack)
Firewall Appliance: Cisco ASAv (Adaptive Security Appliance Virtual)
Emulator: GNS3
Key Concepts: Security Levels, NAT/PAT, Access Control Lists (ACLs), DMZ Networking

การตรวจสอบและยืนยันผล (Verification)
เพื่อให้มั่นใจว่านโยบายความปลอดภัยทำงานได้ถูกต้องตามการออกแบบ ได้มีการทดสอบดังนี้:
Running Configuration: ตรวจสอบคำสั่งการตั้งค่าทั้งหมดผ่านไฟล์ show running.txt เพื่อยืนยันความถูกต้องของระบบ
Connectivity Testing: ตรวจสอบการเชื่อมต่อและการกำหนด IP Address จากฝั่ง Client ผ่าน Command Prompt
End-to-End Verification: บันทึกผลการทดสอบการสื่อสารข้ามโซน (Inside -> Outside, Outside -> DMZ) 
เพื่อยืนยันว่ากฎของไฟร์วอลล์ทำงานอย่างสมบูรณ์

ไฟล์ที่เกี่ยวข้องในโปรเจกต์นี้
NAT-Policy-FW_6631501127.pdf — รายงานสรุปผลการทดลอง
show running.txt — ไฟล์คอนฟิกูเรชันหลัก
Command Prompt.txt — หลักฐานการทดสอบการเชื่อมต่อจาก Client
