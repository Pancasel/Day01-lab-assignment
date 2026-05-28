# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> *Khi tăng giá trị temperature từ 0.0 lên 1.5, câu trả lời chuyển từ rập khuôn, chuẩn xác sang đa dạng, sáng tạo, nhưng ở mức 1.5 mô hình bắt đầu mất kiểm soát và dễ sinh ra thông tin ảo (hallucination).*

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> *Đối với chatbot hỗ trợ khách hàng, mức temperature nên được đặt ở khoảng 0.0 đến 0.2. Điều này đảm bảo tính chính xác, nhất quán và tuân thủ nghiêm ngặt các chính sách của doanh nghiệp, giảm thiểu rủi ro AI cung cấp thông tin sai lệch.*

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> *Với tổng khối lượng 10.500.000 token mỗi ngày, dựa trên bảng giá hiện hành, chi phí sử dụng GPT-4o sẽ đắt hơn GPT-4o-mini khoảng 16 đến 17 lần tùy thuộc vào tỷ lệ token đầu vào/đầu ra.*

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> *GPT-4o xứng đáng hơn trong các tác vụ suy luận phức tạp như trích xuất dữ liệu (OCR) từ hợp đồng pháp lý hoặc review code tự động. Ngược lại, GPT-4o-mini tối ưu hơn cho các tác vụ cần tốc độ cao, logic đơn giản như phân loại khách hàng hoặc tóm tắt log chat.*

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> *Streaming cực kỳ quan trọng cho các ứng dụng tương tác thời gian thực như AI chatbot hoặc dịch thuật trực tiếp, giúp người dùng thấy từng từ hiện ra ngay lập tức để duy trì nhịp độ giao tiếp và giảm cảm giác chờ đợi. Ngược lại, non-streaming lại phù hợp hơn cho các công việc chạy ngầm (background jobs) như xử lý dữ liệu hàng loạt hoặc khi máy chủ cần nhận một chuỗi JSON hoàn chỉnh để kiểm tra logic trước khi hiển thị ra giao diện người dùng.*


## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 
