# Reflection — Lab 19

**Tên:** Phạm Khắc Tú
**Cohort:** A20-K4
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

_Answer here._
 Trên golden set 50 queries, Hybrid đạt kết quả trung bình cao nhất với 78,6%, so với 77,8% của BM25 và 73,2% của Semantic. Ở nhóm exact, BM25 và Hybrid cùng đạt 96,7% vì truy vấn chứa các thuật ngữ xuất hiện trực tiếp trong tài liệu. Ở nhóm mixed, Hybrid thắng rõ rệt với 100% nhờ RRF kết hợp bằng chứng từ khóa và ngữ nghĩa. Riêng nhóm paraphrase, BM25 đạt 33,3%, Hybrid 32,0% và Semantic 24,0%. Semantic không dẫn đầu như kỳ vọng vì mô hình BGE-small của lộ trình Lite chủ yếu được huấn luyện bằng tiếng Anh nên xử lý câu diễn đạt lại bằng tiếng Việt còn yếu. Tôi sẽ dùng pure BM25 khi truy vấn chứa mã, tên biến hoặc thuật ngữ chính xác và cần độ trễ thấp. Pure vector phù hợp khi hệ thống dùng mô hình đa ngữ mạnh và truy vấn chủ yếu là diễn đạt lại.
---

## Điều ngạc nhiên nhất khi làm lab này

_(Optional, 1–2 câu)_
 Điều làm tôi ngạc nhiên nhất là Hybrid Search chỉ thắng với khoảng cách nhỏ trên toàn bộ golden set, còn chất lượng Semantic Search tiếng Việt lại phụ thuộc rất mạnh vào mô hình embedding. Ngoài ra, một ngưỡng semantic cache tưởng như hợp lý như 0,75 vẫn có thể tạo ra tới 36% câu trả lời sai.
---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
