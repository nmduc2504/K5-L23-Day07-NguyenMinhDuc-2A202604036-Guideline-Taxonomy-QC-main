# Guideline gán nhãn — v0 (bản khởi đầu)

- Phiên bản: v0
- Loại nhãn: bounding box (hộp chữ nhật) trên ảnh đường phố
- Công cụ: CVAT, xuất COCO 1.0

---

## 1. Mục tiêu

Nhãn dùng để huấn luyện mô hình phát hiện **người và phương tiện** trên ảnh đường phố
(ví dụ cho camera giao thông hoặc xe tự lái).

## 2. Lớp và thuộc tính

### Lớp (mỗi vật thuộc đúng một lớp)

| Lớp | Định nghĩa |
|---|---|
| `car` | Ô tô con. |
| `truck` | Xe tải. |
| `van` | Xe thùng kín cỡ nhỏ. |
| `three_wheeler` | Các xe 3 bánh. |
| `motorcycle` | Xe máy, mô tô. |
| `bicycle` | Xe đạp. |
| `cyclo` | Xe xích lô. |
| `person` | Người. |
| `ignore_region` | Vùng không cần gán từng vật. |

### Thuộc tính

| Thuộc tính | Giá trị | Ý nghĩa |
|---|---|---|
| `occluded_level` | `0`, `1`, `2`, `3` | Mức bị che: 0 là thấy rõ, 1 là bị che ít, 2 là bị che nhiều, 3 là không rõ. |
| `truncated` | `no`, `yes` | Vật bị cắt ở mép ảnh. |
| `can_review` | tick / không | Tick khi bạn không chắc, để người khác xem lại. |

## 3. Quy tắc vẽ box

1. Gán box cho mọi người và phương tiện trong ảnh.
2. Box ôm sát vật.
3. Chọn đúng lớp và thuộc tính.

## 4. Ca khó

1. Có nhiều vật thể hình dạng xe cộ, người có thể được xem là mô hình của vật thể nhưng không chắc chắc vì nó đang ở trên đường.
2. Vài ảnh bị mờ, lòa gây khó khăn cho việc gán nhãn.
3. Nhiều loại xe 3 bánh khó phân biệt để gán nhãn.

## 5. QC và phiên bản

- Mọi thay đổi làm đổi nhãn đều tăng phiên bản guideline.
- Ca mơ hồ: tick `can_review`.