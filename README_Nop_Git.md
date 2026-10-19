# HƯỚNG DẪN NỘP BÀI MVC5 LÊN GITHUB

## Trong Visual Studio
1. Giải nén toàn bộ ZIP, mở `MyStoreMVC5.sln` (**File > Open > Project/Solution**).
2. Cài workload ASP.NET nếu Visual Studio báo thiếu; restore NuGet; build.
3. Tạo `MyStore` bằng SQL trong `Database/01_Create_MyStore.sql` qua SSMS.
4. Làm bước **Database First** như README trong thư mục `MyStoreMVC5` (cần SQL thật trên máy).
5. Trên menu **Git > Create Git Repository**, chọn GitHub (đăng nhập nếu được hỏi).
6. Vào **Git Changes**, xem các file (loại trừ file cấu hình chứa mật khẩu), viết commit `Lab Web BE - MVC5 Project Setup`, chọn **Commit All**, sau đó **Push**.

## Dùng Git CLI (nếu Git UI không có)
Tại thư mục chứa `.sln`:
```
git init
git add .
git commit -m "Lab Web BE - MVC5 Project Setup"
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```
Thay USERNAME/REPOSITORY bằng repository của chị, không dùng ví dụ làm đường dẫn thật.

**LƯU Ý:** GitHub chỉ lưu và hiển thị code. Đẩy SQL script lên GitHub **không tự tạo database** trên máy giảng viên. Không đẩy chuỗi kết nối thực hoặc mật khẩu.
