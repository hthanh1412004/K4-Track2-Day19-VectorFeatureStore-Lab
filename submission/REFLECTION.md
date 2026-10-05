# Reflection — Lab 19

**Tên:** Nguyễn Hữu Thành
**Cohort:** A20-K4
**Path đã chạy:** lite

Kết quả trung bình cho thấy hybrid đạt 78,6%, cao hơn BM25 77,8% và vector
73,2%. Ở nhóm `exact`, BM25 và hybrid cùng đạt 96,7% vì từ khóa kỹ thuật xuất
hiện trực tiếp trong tài liệu. Với `mixed`, hybrid đạt 100%, cao nhất trong ba
cách tìm kiếm. Riêng `paraphrase`, BM25 đạt 33,3%, còn vector chỉ đạt 24,0%.
Theo em nguyên nhân là model bge-small mặc định thiên về tiếng Anh nên chưa
biểu diễn tốt câu tiếng Việt được diễn đạt lại. Đây cũng cho thấy vector search
không phải lúc nào cũng tự động tốt hơn BM25.

Em sẽ không dùng hybrid khi dữ liệu chủ yếu là mã sản phẩm, ID hoặc từ khóa cần
khớp chính xác, vì BM25 đơn giản và nhanh hơn. Nếu người dùng thường hỏi bằng
ngôn ngữ tự nhiên và có model đa ngữ tốt, pure vector có thể phù hợp hơn.
Hybrid hữu ích khi hệ thống có nhiều kiểu query, nhưng phải duy trì hai index
và tốn thêm chi phí truy vấn.
