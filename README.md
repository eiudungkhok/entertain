# 🎄 NOEL_V2 - Interactive 3D Holiday Magic

Một trải nghiệm web 3D tương tác mang chủ đề lễ hội, kết hợp hình ảnh rực rỡ với công nghệ nhận diện cử chỉ tay thông minh. Dự án này cho phép người dùng điều khiển một hệ thống hạt (particle system) sinh động bằng webcam và đưa những bức ảnh kỷ niệm của riêng họ vào không gian 3D ảo diệu.

---

## ✨ Tính Năng Nổi Bật

* **Hệ Thống Hạt 3D (3D Particle System)**: Tạo ra một môi trường động với 1500 hạt trang trí và 2500 hạt bụi lấp lánh. Các hạt bao gồm hộp quà màu vàng và xanh, quả cầu đỏ và vàng, cùng kẹo gậy (candy canes).
* **Điều Khiển Bằng Cử Chỉ (Gesture Controls)**: Tích hợp thư viện MediaPipe để theo dõi và nhận diện chuyển động tay qua webcam theo thời gian thực.
* **Biến Đổi Đội Hình (Dynamic Formations)**: Các hạt có thể tự động xếp thành hình cây thông Noel xoay tròn, phân tán thành một đám mây 3D, hoặc phóng to tập trung vào một bức ảnh cụ thể.
* **Tích Hợp Ảnh Cá Nhân (Custom Photo Uploads)**: Người dùng có thể tải hình ảnh lên từ thiết bị. Ảnh sẽ được đóng khung vàng champagne và chèn trực tiếp vào không gian 3D.
* **Hiệu Ứng Hình Ảnh (Post-Processing)**: Sử dụng `UnrealBloomPass` của Three.js để tạo hiệu ứng phát sáng mờ ảo, mang lại cảm giác huyền bí và rực rỡ.

---

## 🎮 Hướng Dẫn Điều Khiển

Ứng dụng hỗ trợ cả tương tác vật lý qua bàn phím/chuột và tương tác qua cử chỉ tay (nếu cấp quyền sử dụng Webcam).

| Hành Động / Cử Chỉ | Kết Quả |
| :--- | :--- |
| **Nắm tay lại (Fist)** | Các hạt tập hợp lại tạo thành hình Cây thông Noel. |
| **Mở rộng bàn tay (Open Hand)** | Các hạt phân tán ra thành một khối cầu 3D không gian. |
| **Chụm ngón tay (Pinch)** | Kích hoạt chế độ "Focus", phóng to và xoay quanh một bức ảnh ngẫu nhiên đã tải lên. |
| **Di chuyển tay (X/Y)** | Xoay toàn bộ khung cảnh 3D theo hướng tay của bạn. |
| **Nút "Thêm ảnh"** | Chọn và tải các hình ảnh (hỗ trợ chọn nhiều ảnh) vào môi trường 3D. |
| **Nhấn phím 'H'** | Ẩn/hiện các nút điều khiển trên màn hình (UI) để có góc nhìn toàn cảnh. |

---

## 🛠️ Công Nghệ Sử Dụng

Dự án được xây dựng hoàn toàn trên nền tảng Web với các công nghệ và thư viện hiện đại:

* **HTML5 / CSS3**: Xây dựng cấu trúc UI tối giản và hiệu ứng tải trang (loading spinner).
* **JavaScript (ES6 Modules)**: Xử lý logic và tích hợp các module.
* **Three.js (v0.160.0)**: Lõi xử lý đồ họa 3D, camera, ánh sáng và post-processing.
* **MediaPipe Tasks Vision (v0.10.3)**: Mô hình học máy `HandLandmarker` dùng để nhận diện và theo dõi các điểm neo trên bàn tay.

---

## 🚀 Hướng Dẫn Cài Đặt & Chạy Dự Án

Do dự án sử dụng **ES Modules** (`type="module"`) và yêu cầu quyền truy cập **Webcam**, bạn không thể chạy trực tiếp bằng cách click đúp vào file `index.html`. Thay vào đó, bạn cần chạy qua một local server.

**Các bước thực hiện:**

1.  Tải toàn bộ mã nguồn hoặc tệp `index.html` về máy.
2.  Khởi tạo một Local Web Server. Bạn có thể sử dụng một trong các cách sau:
    * **VS Code**: Cài đặt extension **Live Server**, click chuột phải vào file `index.html` và chọn *Open with Live Server*.
    * **Python**: Mở terminal tại thư mục chứa code và chạy lệnh: `python -m http.server 8000`
    * **Node.js**: Sử dụng package `http-server` (chạy lệnh `npx http-server`).
3.  Mở trình duyệt và truy cập vào địa chỉ localhost (ví dụ: `http://localhost:8000`).
4.  Cấp quyền truy cập Camera khi trình duyệt yêu cầu để trải nghiệm tính năng nhận diện cử chỉ.

---

## 🎨 Tùy Chỉnh (Dành Cho Nhà Phát Triển)

Bạn có thể dễ dàng thay đổi các thông số cấu hình mặc định trong khối `CONFIG` của mã nguồn:

* `CONFIG.colors`: Chỉnh sửa bảng màu của nền, hạt vàng, hạt xanh và điểm nhấn đỏ.
* `CONFIG.particles.count`: Tăng giảm số lượng vật thể trang trí (mặc định: 1500).
* `CONFIG.particles.dustCount`: Thay đổi mật độ bụi lấp lánh (mặc định: 2500).
* `CONFIG.particles.treeHeight / treeRadius`: Điều chỉnh kích thước của cây thông Noel.
