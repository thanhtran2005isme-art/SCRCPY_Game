# Liên Quân: skill aim bằng chuột (prototype)

## Mục tiêu
- Giữ Q/E/R: chạm giữ nút kỹ năng tương ứng.
- Rê chuột: di chuyển ngón tay ảo để thay đổi hướng ngắm.
- Thả phím: nhấc ngón tay ảo lên để kết thúc thao tác.
- Bản thử nghiệm không dùng mouseMoveMap cùng lúc để tránh xung đột với ngón tay ngắm.

## Áp dụng trên Windows
Từ thư mục gốc clone C:\Users\Admin\Videos\QtScrcpy:

1. Lấy nhánh thử nghiệm từ repo của bạn:
   git fetch origin
   git switch --track origin/feature/lienquan-skill-aim
2. Đồng bộ submodule:
   git submodule update --init --recursive
3. Áp dụng patch vào chính thư mục submodule:
   cd /d C:\Users\Admin\Videos\QtScrcpy\QtScrcpy\QtScrcpyCore
   git apply --check ..\..\patches\lienquan_skill_aim.patch
   git apply ..\..\patches\lienquan_skill_aim.patch
   git diff --check
4. Chép keymap/aov_lienquan_skill_aim.json vào thư mục keymap của QtScrcpy.
5. Biên dịch lại QtScrcpy bằng phiên bản Qt/MSVC tương thích.

Các tọa độ kỹ năng trong JSON đang là giá trị ước lượng, cần thay bằng tọa độ pos thực tế trên giao diện Liên Quân. aimSpeedX/Y là độ nhạy ban đầu để thử.

Đây là prototype chưa được build hoặc kiểm thử trên thiết bị thật. Nếu có input bị giữ, thả toàn bộ phím và đổi về normal hoặc restart dịch vụ.
