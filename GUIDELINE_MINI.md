# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` |Các phương tiện cơ giới đường bộ có 4 bánh (hoặc hơn) chuyên chở người hoặc hành hóa với sức chứa nhỏ.|xe con, sedan, SUV, taxi, xe bán tải |
| `truck` |Các phương tiện cơ giới đường bộ được thiết kế và chuyên dụng chủ yếu để vận chuyển hàng hóa, vật liệu hoặc kéo theo rơ-moóc, có kích thước và trọng tải lớn hơn xe con thông thường. |xe tải chở hàng, xe đầu kéo |
| `bus` |phương tiện cơ giới đường bộ được thiết kế chuyên dụng để vận chuyển số lượng lớn hành khách (thường từ 10 chỗ ngồi trở lên), có khoang hành khách kéo dài và kích thước lớn hơn đáng kể so với car |xe buýt, minibus chở khách |
| `van` |Các phương tiện cơ giới đường bộ có thiết kế dạng hình hộp chữ nhật (box-shaped), kết hợp giữa khả năng chở người (từ 6 đến 16 chỗ) hoặc chở hàng hóa cỡ vừa. Xe có nắp capo ngắn, phần trần cao và phẳng kéo dài từ khoang lái đến hết đuôi xe. |xe van, minivan chở hàng hoặc chở người |


## Quy tắc chung

- Box bám sát vật thể nghĩa là: Box ôm sát phần thân xe nhìn thấy được, không lấy thêm mặt đường, trời hay xe bên cạnh.
- Vật thể bị che khuất: Vật thể bị che một phần vẫn gán box quanh phần nhìn thấy được nếu nhận diện được lớp.
- Vật thể bị cắt bởi rìa ảnh: Box chạm đúng rìa ảnh khi vật thể bị cắt khung; không đoán phần nằm ngoài ảnh.
- Vật thể rất nhỏ/mơ hồ: Không tự đoán. Ghi xuống ca mơ hồ
## Ghi lại quyết định cho ít nhất ba ca mơ hồ.

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_001` |Xe 11 bị che khuẩt bởi xe car 10 |Xe 11 là xe van |Hình dạng có phần đầu trên xe và chiều dài giống xe van |
| `drive_002` |Xe 61 đến xe 65 rất nhỏ |Xe 61 đến 65 đánh car |Hình dạng xe giống xe car |
| `drive_004` |Xe 120,xe 121 bị cắt bởi rìa ảnh |Xe 120,xe 121 đánh xe car |Hình dạng đầu và đít xe giống xe car|