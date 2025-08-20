- Server: 

chạy file
```./openvpn-install.sh```
Chạy hết theo default
Khi nào đến mục tạo client thì giữ lại file.opvn

Sửa file ```/etc/openvpn/server/server.conf```
Xóa dòng hoặc đánh đấu # cho dòng 
```push "redirect-gateway def1 bypass-dhcp"```
==> giữ ip trong lan
Lưu ý, mạng trong lan ip trong giải (/25) 192.167.x.1 => 192.167.x.127

khởi đông lên bằng lẹnh
```systemctl status openvpn-server@server```

check kết nối client
```nano /etc/openvpn/server/ipp.txt```

Lưu ý: trong trường hợp public ip bị thay đổi thì làm lại từ đầu


- Client
chạy file 
```./openvpn-install.sh```
vẫn chạy hết theo default
Copy file.opvn (từ server) cho client vào thư mục ```/etc/openvpn/client``` => ghi đè vào file ```client.conf``` nếu đã có
khởi động bằng lệnh 
```sudo systemctl start openvpn-client@client```

