# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên: Nguyễn Quốc Khánh
- MSSV: 2A202603238
- Email: 26ai.khanhnq3@vinuni.edu.vn
- Lớp:L2B
- Link repo bài làm: https://github.com/kanzh24/K5-L2B-DAY02-NguyenQuocKhanh-2A202603238-ObjectDetection.git
- Link Colab đã chạy: https://colab.research.google.com/drive/11deLZOpk6IHk7xWwmX2Ol5RRe-TM5Tic?usp=sharing

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train: 50
- Kết quả checker và lỗi đã xử lý: ĐẠT cấu trúc: 50/50 file nhãn hợp lệ
- Danh sách ít nhất 10 ảnh đã rà bằng mắt: drive_001, drive_002, drive_003, drive_004, drive_005, drive_006, drive_007, drive_008, drive_009, drive_010
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa: Không có
- Commit khóa nhãn ban đầu: update 50 files trained labels

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP |468 | |
| FP |727 | |
| FN |185 | |
| Precision |0.3916 | |
| Recall |0.7167 | |
| F1 |0.5065 | |
| mean_iou_of_matches |0.7939 | |
| passed |false | |
--> Do id của gold_train_labels bị lấy với id trong repo nên không pass(Trong gold thì 1 = van, 2 = truck, 3 = bus, còn readme của repo là 1=truck, 2=bus, 3=van). Anh Lab Coach kêu không cần sửa.
Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch:
+ Runtime: Google Collab
+ GPU/CPU: T4 GPU
+ Ultralytics: 8.4.208
+ Torch: 2.14.1
- Các tham số thay đổi so với notebook nếu có và lý do: Không thay đổi 
- Đường dẫn best checkpoint trong phiên chạy: 

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision |0.40708387969106213 |
| Recall |0.23397128184805985 |
| mAP50 |0.2737343198820419 |
| mAP50–95 |0.2018250052348706 |

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa?
-> Lớp bus (0). Ảnh minh hoa: drive_052, drive_053
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box?
-> Kiểm tra Chất lượng localization của box và chất lượng nhãn
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?
-> Mô hình nhận diện sai car, bus với xe van ở hình drive_051 và drive_053. 
4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì?
-> Vì 10 ảnh eval chỉ có giá trị khi mô hình chưa từng thấy chúng. Đưa vào train thì metric bị thổi phồng (data leakage), không còn biết mô hình có tổng quát hóa thật hay chỉ học thuộc. 
Vai trò của note book: 
+ Đo mAP50 / mAP50–95 trên dữ liệu chưa thấy.
+ Vẽ box dự đoán để kiểm tra lỗi bằng mắt.
+ Phát hiện overfitting (train loss giảm nhưng eval không cải thiện).
## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
|Gold QC và rework |F1=0.5065 (passed = fail)  |Hỏi lại Lab Coach  |Giữ nguyên do id của gold_train_labels bị lấy với id trong repo nên không pass|

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.
- Claude ở phần hỗ trợ trả lời câu hỏi phần 5. Kết quả YOLO.
