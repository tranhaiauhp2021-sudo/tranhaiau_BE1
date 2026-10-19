# MyStore MVC5 - Starter Project

**Phạm vi:** project khởi tạo ASP.NET MVC5 (.NET Framework 4.8), trang Home khách hàng, Area Admin, bố cục Razor, cấu hình route xử lý hai HomeController. **Chưa có** model EDMX (cần tạo tại Visual Studio kết nối SQL Server), CRUD, đăng nhập, checkout hay tính năng sản phẩm.

## Yêu cầu máy
- Windows + Visual Studio 2022 có workload **ASP.NET and web development**, .NET Framework 4.8 targeting pack.
- SQL Server Express/Developer + SQL Server Management Studio (SSMS).
- Internet để Visual Studio tự tải các gói NuGet (MVC 5.2.9, EF 6.5.1).

## Các bước theo slide
1. Mở SSMS, kết nối `TENMAY\SQLEXPRESS` (Express) hoặc `localhost` (Developer, nếu cấu hình như vậy).
2. Mở file `../Database/01_Create_MyStore.sql` và nhấn **Execute**. Script tạo database `MyStore` và 6 bảng: User, Customer, Category, Product, Order, OrderDetail. Chỉ chạy **1 lần** trên database trống.
3. Mở `../MyStoreMVC5.sln` bằng Visual Studio. Bật **Restore NuGet packages**, Build Solution; nếu Visual Studio yêu cầu, cài workload ASP.NET và .NET Framework 4.8.
4. Test **/Home/Index** (khách hàng) và **/Admin/Home/Index** (Admin).
5. Vào project > `Models` (tạo folder này nếu chưa có) > **Add > New Item > Data > ADO.NET Entity Data Model** > đặt `MyStoreModel` > **EF Designer from database** > kết nối `MyStore` > chọn các bảng > Finish. Nếu mục EDMX vắng, kiểm tra EF6 Tools hoặc cài extension hỗ trợ.
6. Khi tạo EDMX, có thể Visual Studio cần chuyển từ PackageReference sang `packages.config` hoặc dùng project **ASP.NET Web Application (.NET Framework) > MVC** chuẩn do IDE tạo, sau đó sao chép các file Controllers, Views, Areas và RouteConfig trong bộ này. Đây là phương án dự phòng, không phải bước đã thực hiện.
7. **Không commit** mật khẩu, chuỗi kết nối thật, file `.mdf` cá nhân hay thư mục build.

## Git trong Visual Studio
`Git > Create Git Repository` (GitHub), chọn đúng thư mục chứa `.sln`, xem file thay đổi, `Commit All`, rồi `Push`. Hoặc dùng lệnh Git từ thư mục gốc (xem README ở gốc ZIP).

### Chú ý kỹ thuật
- Bài slide yêu cầu EF6 **Database First**, nên không có lý do dựng mô hình EDMX giả khi chưa kết nối SQL Server trên máy chị.
- Script nguồn đặt kiểu cột `ProductDecription` (thiếu chữ s); giữ đúng file gốc để EF ánh xạ nhất quán.
- SQL file không tự ép database owner thành `sa` vì thay đổi quyền có thể không phù hợp máy của chị.
- **Chưa kiểm thử build thật** do môi trường tạo file không có Visual Studio/MSBuild/.NET Framework.
