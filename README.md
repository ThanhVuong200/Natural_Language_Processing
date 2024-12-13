Mục Tiêu
Cài đặt và huấn luyện mô hình Skip-gram để học các embedding vector từ một tập dữ liệu văn bản tiếng Việt. Mô hình sẽ được xây dựng từ đầu bằng Python mà không sử dụng các thư viện có sẵn.
Yêu cầu kỹ thuật
-	Ngôn ngữ lập trình: Python
-	Các thư viện sử dụng: NumPy, Pandas, NLTK (chỉ để tiền xử lý văn bản), matplotlib (để vẽ đồ thị).

Các nội dung thực hiện
 1. Tiền xử lý dữ liệu
- Thu thập dữ liệu: Sinh viên có thể tự chọn một tập dữ liệu văn bản tiếng Việt hoặc sử dụng một tập dữ liệu mẫu được cung cấp trong đề bài.
- Các bước tiền xử lý bắt buộc:
	- Chuyển đổi chữ thường.
- Loại bỏ dấu câu, ký tự đặc biệt.
- Tách từ (sinh viên có thể sử dụng các công cụ tách từ tiếng Việt như pyvi hoặc vncorenlp...).
- Tạo từ điền từ vựng (vocabulary) từ tập dữ liệu.
 2. Thiết kế mô hình Skip-gram
- Sinh viên phải triển khai từ đầu mô hình Skip-gram như sau:
- Lớp nhúng (embedding layer):
- Vector nhúng với kích thước được định nghĩa trước (ví dụ: 100 hoặc 300).
- Ma trận nhúng có kích thước [|V|] x d], trong đó |V| là kích thước từ vựng và d là kích thước của vector nhúng.
- Lớp đầu ra:
-Ma trận trọng số đầu ra có kích thước `[d x [|V|]`.
- Áp dụng softmax để tính xác suất của các từ trong ngữ cảnh.
- Hàm mất mát: sử dụng hàm cross-entropy để tính mất mát giữa từ trung tâm và các từ trong ngữ cảnh.
 3. Huấn luyện mô hình
- Huấn luyện mô hình trên tập dữ liệu văn bản tiếng Việt với các tham số:
-	Batch size: tự chọn. (Nếu dùng batch size = 1 thì huấn luyện theo từng mẫu dữ liệu.)
-	Epochs: ít nhất 10 epochs.
-	Learning rate: tự chọn
 4. Đánh giá embedding vector
-	Phương pháp đánh giá: sử dụng tương đồng từ vựng (word similarity):
-	Chọn một bộ từ đôi (ví dụ: từ đồng nghĩa, từ trái nghĩa) để kiểm tra tính tương đồng của các vector embedding.
-	Tính toán cosine similarity giữa các cặp từ này.
-	Đánh giá tính hợp lý của vector embedding dựa trên tính chính xác của cosine similarity với kỳ vọng thực tế (ví dụ: từ đồng nghĩa có cosine similarity cao hơn so với từ không liên quan).
