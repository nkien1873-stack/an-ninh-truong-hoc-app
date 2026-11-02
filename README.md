# An ninh trường học: app Flutter (frontend)

Đề tài môn Lập trình di động, nhóm **CodeAndChill** (HUTECH). Đây là phần **app Android viết bằng Flutter**.
App không truy cập cơ sở dữ liệu; mọi dữ liệu đi qua web API của phần backend.

| Phần | Kho mã |
|---|---|
| App Flutter (kho này) | https://github.com/nkien1873-stack/an-ninh-truong-hoc-app |
| Backend web API (Dart Frog, MongoDB Atlas) | https://github.com/nkien1873-stack/an-ninh-truong-hoc-backend |
| Web API đã triển khai | https://an-ninh-truong-hoc-api.onrender.com |
| Mã nguồn đầy đủ (app + backend trong một kho) | https://github.com/nkien1873-stack/an-ninh-truong-hoc |

## Chức năng

- **Người báo**: đăng ký bằng email, MSSV và mã OTP gửi qua email; nút KHẨN CẤP 2 chạm kèm GPS; báo cáo chi tiết
  (loại, mức độ, khu vực, ảnh, ẩn danh); theo dõi trạng thái; gọi và nhắn bảo vệ khi bảo vệ đã nhận; tự huỷ báo cáo
  khi bảo vệ chưa xử lý; "Đi cùng tôi" tự báo động khi quá giờ.
- **Bảo vệ**: hàng đợi sự cố có bộ lọc, bản đồ sự cố, tiếp nhận và cập nhật trạng thái, từ chối kèm đánh dấu tin giả,
  bật/tắt "Đang trực".
- **Quản trị**: thống kê, phân công, quản lý tài khoản (số lần cảnh báo, mở khoá đăng nhập), cấu hình trường,
  cảnh báo toàn trường.

## Cấu trúc

```
lib/core/              theme, router theo vai trò, API client, thông báo đẩy, vị trí, ảnh, widget dùng chung
lib/features/          auth · reports · staff · admin · settings · campus · safety
packages/campus_core/  logic dùng chung với backend: vai trò, phân quyền, máy trạng thái, kiểm tra dữ liệu
test/                  unit test và widget test
tool/screenshots/      chụp ảnh các màn để rà soát giao diện
```

`packages/campus_core` là bản sao của package dùng chung trong kho backend, để kho này tự build được một mình.

## Chạy app

1. Cài Flutter 3.47 và Android Studio (Android 7.0, API 24 trở lên).
2. `flutter pub get`
3. Chạy từ Android Studio, hoặc `flutter run`. App mặc định gọi web API đã triển khai ở trên, không cần chạy backend trên máy.
4. Kiểm thử: `flutter test`

Tài liệu khác: [`HUONG-DAN-THANH-VIEN.md`](HUONG-DAN-THANH-VIEN.md), [`DESIGN.md`](DESIGN.md), [`PRODUCT.md`](PRODUCT.md),
báo cáo [`Bao_cao_CodeAndChill.docx`](Bao_cao_CodeAndChill.docx).
