รันคำสั่งด้านล่างเพื่อดูว่า SSH key มีอยู่ในเครื่องหรือไม่
ls -al ~/.ssh
หากไม่พบไฟล์ id_rsa.pub หรือ id_ecdsa.pub จะต้องสร้าง SSH key ใหม่
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

เมื่อรันคำสั่ง จะมีข้อความถามว่าต้องการบันทึกไฟล์ key ไว้ที่ไหน:

bash
คัดลอกโค้ด
Enter file in which to save the key (/home/you/.ssh/id_rsa):
กด Enter เพื่อใช้ตำแหน่งค่าเริ่มต้น หรือใส่ตำแหน่งไฟล์ที่คุณต้องการเอง

จากนั้นจะถามว่าจะใส่ passphrase หรือไม่ (เป็นเหมือนรหัสผ่านเพิ่มเติมที่ต้องใส่เมื่อใช้ SSH key นี้):

bash
คัดลอกโค้ด
Enter passphrase (empty for no passphrase):
ถ้าไม่ต้องการรหัสผ่าน กด Enter ได้เลย

เมื่อเสร็จแล้ว SSH key คู่จะถูกสร้าง และคุณสามารถดู public key ได้โดยใช้คำสั่ง:

bash
คัดลอกโค้ด
cat ~/.ssh/id_rsa.pub
จากนั้นคุณสามารถคัดลอก public key ไปเพิ่มใน GitHub

ทดสอบการเชื่อมต่อกับ GitHub ผ่าน SSH
ssh -T git@github.com
