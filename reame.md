# Tóm Tắt Toàn Bộ Kiến Trúc & Quy Trình Đồng Bộ Dữ Liệu (Hybrid Workflow)

## 1. Báo Cáo Phân Tích I/O & Xử Lý `node_modules`
* **Luồng dữ liệu (`Ctrl + S`):** Lưu file vào **SSD Local** ──► **File Watcher** phát hiện thay đổi ──► **Exclusion Filter** lọc bỏ `node_modules` ──► Upload phần code hợp lệ lên Cloud qua HTTPS ──► Hiển thị **Tích xanh**.
* **Giải pháp bẫy `node_modules`:** Cấu hình chặn đồng bộ (Exclude) thư mục `node_modules` để tránh treo hệ thống do hàng vạn file nhỏ. Quản lý mã nguồn chính qua Git (`.gitignore`), tái tạo môi trường bằng lệnh `npm install`.

---

## 2. Giao Tiếp Doanh Nghiệp (Enterprise Workspace vs. App Chat Cá Nhân)
* **Vấn đề trên Zalo:** Trôi tin nhắn, hỗn loạn thông tin, không quản lý được Task và gây ra hiện tượng phân mảnh phiên bản file (**"23 phiên bản file"**).
* **Giải pháp Lark / Slack:** Phân chia Channel/Thread chuyên biệt; tích hợp Task, lịch họp, Live Docs và tìm kiếm nâng cao giúp tiết kiệm thời gian và tối ưu hóa hiệu suất làm việc nhóm.

---

## 3. Quy Trình Hybrid Workflow & Khôi Phục Dữ Liệu
* **Mô hình Hybrid Workflow:**
  ```text
  [ 1. Local SSD ] (Thao tác cực nhanh, làm việc offline)
         │ (Ctrl + S)
         ▼
  [ 2. Auto Sync Agent ] (Tiến trình đồng bộ ngầm)
         │
         ▼
  [ 3. Cloud Storage ] (Đồng bộ đa thiết bị, lưu vết Version History)