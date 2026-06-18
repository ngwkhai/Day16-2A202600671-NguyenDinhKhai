# Báo cáo ngắn CPU LightGBM

1. Bài benchmark được chạy trên CPU instance `t3.large` với bộ dữ liệu Credit Card Fraud Detection gồm 284,807 giao dịch.
2. Thời gian tải dữ liệu là 2.43 giây, cho thấy dataset có thể được xử lý nhanh trên bộ nhớ CPU.
3. Thời gian huấn luyện LightGBM là 18.76 giây, đủ nhanh cho một bài toán tabular ML quy mô vừa.
4. Mô hình đạt AUC-ROC 0.9451, thể hiện khả năng phân biệt giao dịch gian lận và bình thường khá tốt.
5. Accuracy đạt 0.9995, nhưng do dữ liệu mất cân bằng nên F1-score 0.8617, precision 0.9000 và recall 0.8265 là các chỉ số quan trọng hơn.
6. Tốc độ inference rất nhanh: 1 dòng mất khoảng 1.92 ms, còn 1000 dòng mất 27.85 ms.
7. Với throughput xấp xỉ 35,910 dòng/giây cho batch 1000 dòng, CPU đáp ứng tốt bài toán LightGBM này.
8. Lý do dùng CPU thay GPU là tài khoản/lab không thuận lợi cho quota GPU, trong khi LightGBM là mô hình gradient boosting cho dữ liệu bảng và không cần GPU để đạt kết quả tốt.
