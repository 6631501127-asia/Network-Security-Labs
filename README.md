# Network System Security Labs

รวมใบงานและผลการทดลองวิชา Network System Security การจำลองเครือข่ายความปลอดภัยด้วย Cisco ASAv บน GNS3

## โครงสร้างภายในโฟลเดอร์
- `NAT-Policy-FW_6631501127.pdf` : รายงานฉบับเต็มและการทดสอบระบบ NAT
- `show running.txt` / `FW-lab1_6631501127.txt` : Running Configuration ของ Cisco ASA Firewall
- `Command Prompt.txt` : ผลการตรวจสอบ IP และการเชื่อมต่อจากเครื่อง Client

## การจัดโซนความปลอดภัย (Security Levels)
- **Outside Interface** (GigabitEthernet0/0) -> Security Level 0 (รับ IP ผ่าน DHCP)
- **Inside Interface** (GigabitEthernet0/1) -> Security Level 100 (IP: 10.0.0.1/24)
- **DMZ Interface** (GigabitEthernet0/2) -> Security Level 50 (IP: 172.16.0.1/24)

