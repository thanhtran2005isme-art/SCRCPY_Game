# Liên Quân: skill aim bằng chuột (prototype)

Nhánh thử nghiệm này chứa patch cho QtScrcpyCore và JSON minh họa. Mục tiêu:

- Giữ phím Q / E / R: chạm giữ nút kỹ năng 1 / 2 / chiêu cuối.
- Rê chuột: di chuyển cùng ngón tay ảo để điều chỉnh hướng.
- Thả phím: nhả cảm ứng để kết thúc thao tác.
- Chỉ bắt/ẩn chuột trong lúc giữ kỹ năng nếu JSON không có mouseMoveMap, tránh kéo nhầm joystick khi không ngắm.

## Cài local (Windows CMD)

1. Sao lưu source trước. Từ repo clone, vào thư mục submodule:
   C:\Users\Admin\Videos\QtScrcpy\QtScrcpy\QtScrcpyCore
2. Áp dụng file patch từ thư mục bạn đã tải:
   git apply C:\path\to\lienquan_skill_aim.patch
3. Kiểm tra thay đổi:
   git diff --check
4. Chép aov_lienquan_skill_aim.json vào C:\Users\Admin\Videos\QtScrcpy\keymap.
5. Rebuild QtScrcpy v4.2.1 bằng bộ Qt/MSVC tương ứng. Bản EXE tải sẵn sẽ không có thay đổi C++ này.

Các tọa độ kỹ năng trong JSON đang là tọa độ ước lượng; hãy lấy log pos thực tế của từng nút để chỉnh lại trước khi chơi. aimSpeedX và aimSpeedY là tỉ lệ nhạy khởi đầu (1.5), cần tinh chỉnh theo cảm giác.

## Lưu ý

Đây là prototype chưa được biên dịch hoặc thử nghiệm trên điện thoại trong môi trường này. Ngắm bằng cảm ứng liên tục phụ thuộc vào cách game xử lý thao tác kéo. Nếu input bị kẹt, thả mọi phím, chuyển về normal, hoặc khởi động lại server điện thoại. Patch sửa thư viện con QtScrcpyCore, nên cần rebuild app và commit thay đổi trong submodule/fork của bạn nếu muốn chia sẻ mã nguồn đã sửa.
