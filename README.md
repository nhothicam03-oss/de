# Anime 2D Animation Studio

Ứng dụng web HTML/CSS/JavaScript thuần, chạy cục bộ trên trình duyệt.

## Chạy ứng dụng
Do trình duyệt hạn chế đọc thư mục và ES Modules khi mở `file://`, nên khuyến nghị chạy static server:

```bash
python -m http.server 8000
```

Mở `http://localhost:8000`.

## Nhập thư viện PNG
- Nhấn nút `+` ở mục Thư viện.
- Chọn thư mục nhân vật có các thư mục tag, ví dụ `head`, `eyeL`, `eyeR`, `lip`, `body`, `hair_front`.
- Ảnh được nhập vào bộ nhớ phiên hiện tại.
- Chọn asset để thêm vào nhân vật đang chọn.
- Chỉnh offset, scale, rotation trong Inspector.

Tên thư mục tag được lấy từ thư mục cha của file ảnh. Ví dụ:
`characters/An/eyeL/open.png` → tag `eyeL`.

## Chức năng hiện có
- Giao diện workspace Nhân vật / Animation / Kịch bản AI / Dựng phim.
- Nhập ảnh theo thư mục và tag.
- Tạo nhân vật, thêm layer, chỉnh transform, ẩn/hiện layer.
- Preview Canvas 2D, nền sân khấu và đường sàn.
- Clip preset, timeline sự kiện cơ bản, playback.
- Parser offline tiếng Việt theo từ khóa, xuất kế hoạch JSON.
- Tạo nhiều scene cơ bản.
- Xuất project JSON.
- Ghi preview WebM bằng MediaRecorder nếu trình duyệt hỗ trợ.

## Giới hạn kỹ thuật cần biết
Đây là bản ứng dụng nền có thể chạy và thử quy trình asset → nhân vật → timeline → JSON → preview. Nó chưa phải hệ thống hoạt hình thương mại hoàn chỉnh: rig hiện là cấu trúc skeleton logic khởi tạo, chưa có skinning/deformation mesh đầy đủ, IK hai xương thực thi, curve editor, mixer/blending chính xác, audio mixing và lip-sync đồng bộ waveform. Parser offline là bộ luật/keyword, không phải mô hình hiểu ngôn ngữ tự nhiên tổng quát. Xuất WebM ghi lại preview theo thời gian thực, không phải renderer offline frame-accurate. Những phần này cần được triển khai và kiểm thử thêm trước khi dùng sản xuất phim dài.

## Lưu ý dữ liệu
`Lưu dự án` hiện xuất metadata JSON. Các ảnh gốc cần được nhập lại khi mở dự án mới; phiên bản này chưa đóng gói toàn bộ asset nhị phân vào project archive.
