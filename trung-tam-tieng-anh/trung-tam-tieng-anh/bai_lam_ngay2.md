# BÀI LÀM – ÔN TẬP NGÀY 2

- **Họ tên:** Trần Thị Lý
- **Lớp:** HN-KS26_CNTT2
- **Link repository:**
- **Hệ điều hành (Windows/macOS):** Windows

## Bài 1. Lọc log thủ công

### Lệnh đã chạy

```shell
# Lệnh đọc file: C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> gc .\access.log
# Lệnh lọc nội dung: C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> Select-String "ERROR" .\access.log
# Lệnh tạo file error_report.txt: C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> ni error_report.txt
# Lệnh ghi kết quả vào file error_report.txt : C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> Get-Content .\access.log | Select-String "ERROR" > .\error_report.txt
# Lệnh đọc 2 dòng lỗi đầu tiên : C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> Get-Content .\error_report.txt -Head 2

```

### 2 dòng lỗi đầu tiên trong error_report.txt

```text
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)

```

## Bài 2. Đếm bằng pipeline

### Lệnh

```shell
# Lệnh đếm số dòng chứa WARNING trong logs/access.log : C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> Get-Content .\access.log | Select-String "WARNING" | Measure-Object
# Lệnh đếm số dòng chứa ERROR trong logs/payment.log : C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> Get-Content .\payment.log | Select-String "ERROR" | Measure-Object

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
WARNING trong access.log: Count    : 4
ERROR trong payment.log: Count    : 3
```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
# Lệnh chạy script:  C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> .\auto_warning.ps1

```

### Nội dung file logs/warning_report.txt

```text
=== CANH BAO THANH TOAN ===

2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi


```

## Bài 4. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
# Lệnh tạo file logs/tong_hop_ngay2.txt :  C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh> ni tong_hop_ngay2.txt
# Lệnh ghi dòng đầu tiên : C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> Set-Content .\tong_hop_ngay2.txt "=== TONG HOP ACCESS LOG ==="
# Lệnh thêm các dòng chứa ERROR trong logs/access.log :  C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> Get-Content .\access.log | Select-String "ERROR" >> .\tong_hop_ngay2.txt
# Lệnh thêm số dòng chứa WARNING trong logs/payment.log : C:\Users\fpt yen thanh\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh\logs> (gc .\payment.log | Select-String "WARNING" | Measure-Object).Count >> .\tong_hop_ngay2.txt


```

### Nội dung file logs/tong_hop_ngay2.txt

```text
=== TONG HOP ACCESS LOG ===

 
 2 0 2 5 - 1 0 - 1 8   0 8 : 1 7 : 5 9   [ E R R O R ]   K h o n g   t i m   t h a y   t r a n g   / l i c h - t h i   ( 4 0 4 ) 
 
 2 0 2 5 - 1 0 - 1 8   0 8 : 2 5 : 5 5   [ E R R O R ]   H e t   t h o i   g i a n   c h o   ( t i m e o u t ) 
 
 2 0 2 5 - 1 0 - 1 8   0 8 : 3 3 : 5 1   [ E R R O R ]   K e t   n o i   m a y   c h u   d u   l i e u   t h a t   b a i 
 
 2 0 2 5 - 1 0 - 1 8   0 8 : 3 7 : 1 9   [ E R R O R ]   K e t   n o i   m a y   c h u   d u   l i e u   t h a t   b a i 
 
 2 0 2 5 - 1 0 - 1 8   0 8 : 4 9 : 4 3   [ E R R O R ]   H e t   t h o i   g i a n   c h o   ( t i m e o u t ) 
 
 2 0 2 5 - 1 0 - 1 8   0 8 : 5 3 : 1 1   [ E R R O R ]   H e t   t h o i   g i a n   c h o   ( t i m e o u t ) 
 
  
 
 
 
 
 
 5 
 
 
 

```

## Bài 5. Câu hỏi ngắn

- **a)** 
    + Lệnh ... > file là lệnh ghi đè, thay thế hoàn toàn nội dung cũ của file bằng nội dung mới. 
    + Lệnh ... >> file là lệnh ghi nối tiếp: giữ nguyên nội dung cũ và chèn thêm dữ liệu mới vào cuối file. 
- **b)** Ở Bài 4, nếu lệnh thứ 2(nối các dòng ERROR) dùng > thay cho >>, nội dung file tong_hop_ngay2 sẽ thay đổi: dòng đầu tiên "=== TONG HOP ACCESS LOG ===" sẽ mất và file sẽ bắt đầu bằng danh sách các dòng ERROR trong logs/access.log  
- **c)** Trong script nên dùng đường dẫn tương đối logs/payment.log thay vì đường dẫn tuyệt đối cd trên máy mình vì: để đảm bảo có thể chạy trên các máy tính khác, nếu dùng đường dẫn tuyệt đối, script sẽ bị lỗi khi chạy ở máy khác do không tìm thấy đường dẫn đó

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
