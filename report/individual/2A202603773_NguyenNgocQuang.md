# Báo cáo cá nhân — Day 01: Lọc tin nhắn rác bằng ML, DL, Embedding và LLM

- **MSSV:** 2A202603773
- **Họ và tên:** Nguyễn Ngọc Quang
- **SEED** (in ở ô đầu notebook): 3060

## 1. Bằng chứng

| Tệp | Có? |
| --- | --- |
| [`day01_lab.ipynb`](day01_lab.ipynb) — notebook đã chạy, còn output | ☑ |
| [`lab1_report.json`](lab1_report.json) — do ô "Báo cáo cuối" sinh ra | ☑ |
| [`hand_calc.jpg`](hand_calc.jpg) — ảnh tính tay có các bước | ☐ |

## 2. Kết quả chính

| Cách tiếp cận | F1 test | F1 SUB 40 | p95 ms/tin | USD/1k tin |
| --- | ---: | ---: | ---: | ---: |
| 1. BoW + LogReg (tự code) | 0.868 | 0.889 | 0.30 | 0.000 |
| 2. BoW + MLP (deep learning) | 0.941 | 0.974 | 4.36 | 0.000 |
| 3a. Encoder (MiniLM) + kNN | 0.895 | 0.974 | 126.47 | 0.000 |
| 3b. Encoder (MiniLM) + LogReg | 0.929 | 0.950 | 40.68 | 0.000 |
| 3c. Encoder (MiniLM) + MLP head | 0.928 | 0.974 | 38.83 | 0.000 |

## 3. Dự đoán và thực tế

*Chọn 3 dự đoán `predict(...)` lệch nhiều nhất so với kết quả. Mỗi cái: bạn đoán gì, ra gì, vì sao lệch.*

## 4. Phân tích 50 case khó

*Model nào tụt nhiều nhất, ở nhóm case nào? Nêu 2 case cụ thể và cơ chế khiến model sai.*

## 5. Thử thách cá nhân

**Đề #1 (SEED 3060 % 6 = 0):** Đổi ngưỡng quyết định 0.5 → 0.2 và → 0.8 cho mô hình Phần 1. Báo precision/recall/F1 từng ngưỡng. Một ngân hàng sợ chặn nhầm tin OTP thì nên chọn ngưỡng nào? Vì sao?

*Cách làm, kết quả, giải thích.*

## 6. Phương án cho sản phẩm thật

*Với yêu cầu p95 < 50 ms/tin cho 10 triệu SMS/ngày: chọn phương án nào, dẫn số liệu nào, chấp nhận đánh đổi gì.*

## 7. AI log và điều đã học

**AI log**

- Tôi hỏi AI bài nộp đã đủ chưa, AI liệt kê 4 file cần có trong `report/individual/` và các phần còn thiếu, tôi tự chạy lại notebook trên Colab.
- Tôi hỏi AI có để trống `predict("tradeoff")` và `predict("hard_eval")` được không, AI giải thích `"..."` sẽ làm notebook báo lỗi và dừng, nên tôi ghi `"not sure"` vì chưa có dự đoán rõ ràng.
- Tôi hỏi AI vì sao chạy lại vẫn lỗi ở `tradeoff`, AI chỉ ra tôi chạy ô `predict` trước khi sửa chữ, nên tôi chạy lại ô đó rồi chạy các ô phía dưới.

**Điều đã học:** Notebook bắt phải ghi dự đoán trước khi chạy thí nghiệm, để so được mình nghĩ gì với kết quả thật. Lần sau tôi sẽ đoán thử dù chưa chắc, vì đoán sai cũng giúp mình hiểu bài hơn.
