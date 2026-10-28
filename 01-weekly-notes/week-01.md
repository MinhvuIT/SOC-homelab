#Tuần 1
##Đã làm
- Tạo repo SOC-homelab trên github
- Cài openssh-server rsyslog -y(tạo log để đăng nhập ssh) ,phân tích grep/awk
##Phân tích log
 - 9 lần đăng nhâp thất bại ,cùng 1 ip
 - 3 user bị thử:minhvu,fakeuser,admin
 - Lênh đếm ip:'sudo grep "sshd" var/log/auth.log |grep "Fail password" |awk '{print $(NF-3)} | sort|uniq -c |sort -rn'
##Sự cố gặp
- **Triệu chứng**: báo trên ubuntu 404,update "Realease file is not valid yet"
- **Chuẩn đoán**:Sai giờ trên unbuntu (lệch 130 ngày)
- **Cách sửa**:đặt lại giờ, bật NTP rồi cài lại ssh
  ##Học được
  - Cấu hình để thực hành lab sudo install openssh rsyslog -y
  - Cách đọc log và tư duy của 1 SOC analys
