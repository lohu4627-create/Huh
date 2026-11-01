# Tạo APK bằng điện thoại, không cần Android Studio

1. Tạo tài khoản GitHub nếu chưa có.
2. Tạo repository mới trên github.com.
3. Tải lên toàn bộ nội dung trong thư mục RadiaNano (bao gồm thư mục `.github/workflows`).
4. Mở tab **Actions** của repository.
5. Chọn workflow **Build RadiaNano APK** rồi bấm **Run workflow** (hoặc đợi build tự chạy sau khi push).
6. Khi chạy xong, mở lần chạy mới nhất, kéo xuống **Artifacts**, tải `RadiaNano-debug-apk`.
7. Giải nén artifact; bên trong có `app-debug.apk`. Mở APK trên điện thoại để cài. Có thể cần cho phép cài ứng dụng từ nguồn này.

Lưu ý:
- Đây là APK debug tự build, không phải bản phát hành đã ký để đăng Play Store.
- Không cần cài Android Studio; GitHub Actions build trên máy chủ.
- Dự án hiện đọc USB Serial ở 9600 baud, chưa phải giao thức độc quyền của RadiaCode.
- Chưa có firmware photodiode hoàn chỉnh; ứng dụng chỉ hiển thị dữ liệu Arduino gửi theo định dạng trong README.
