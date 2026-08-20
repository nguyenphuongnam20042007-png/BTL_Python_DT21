# DT21 — Phân tích cảm xúc bình luận tiếng Việt

Bài tập lớn cuối kỳ - Đề tài DT21 (mức Nâng cao)

## 1. Giới thiệu

Notebook thực hiện phân tích cảm xúc (tích cực / tiêu cực / trung tính) trên các bình luận,
phản hồi tiếng Việt, sử dụng đồng thời 2 hướng tiếp cận:

- **Từ điển (lexicon-based):** đếm từ tích cực/tiêu cực để tính điểm cảm xúc cho từng câu.
- **Học máy (nâng cao):** TF-IDF + Logistic Regression, có đánh giá độ chính xác.

## 2. Cấu trúc thư mục

```
.
├── README.md
├── requirements.txt
├── data/
│   ├── uit_vsfc.csv          # Nguồn 1 — bộ dữ liệu phản hồi sinh viên UIT-VSFC (CSV)
│   └── du_lieu_them.json     # Nguồn 2 — dữ liệu bổ sung do nhóm thu thập (JSON)
└── notebook/
    └── 1_tai_du_lieu.ipynb   # Notebook chính: đọc dữ liệu, tiền xử lý, phân tích, trực quan hóa
```

## 3. Mô tả dữ liệu

### 3.1. `data/uit_vsfc.csv`
Bộ dữ liệu công khai UIT-VSFC — phản hồi của sinh viên về môn học. Các trường dữ liệu:

| Cột | Kiểu dữ liệu | Mô tả |
|---|---|---|
| `sentence` | text | Nội dung câu phản hồi/bình luận (tiếng Việt) |
| `sentiment` | text | Nhãn cảm xúc: `positive` / `negative` / `neutral` |
| `topic` | text | Chủ đề: `lecturer`, `curriculum`, `facility`, `others` |

### 3.2. `data/du_lieu_them.json`
Dữ liệu bổ sung do nhóm thu thập/biên soạn thêm, cùng cấu trúc 3 trường như trên
(`sentence`, `sentiment`, `topic`) để có thể gộp trực tiếp với nguồn 1.

> Lưu ý: nhãn `topic` giữa 2 nguồn không hoàn toàn giống nhau về tên gọi (ví dụ `teacher` ở JSON
> tương ứng với `lecturer` ở CSV) — notebook đã tự động chuẩn hóa 2 nhãn này về cùng một giá trị
> trong bước tiền xử lý.

## 4. Yêu cầu môi trường

- Python **3.9 trở lên**
- Các thư viện liệt kê trong `requirements.txt`, gồm 4 nhóm chính:

| Nhóm | Thư viện | Mục đích |
|---|---|---|
| Xử lý dữ liệu | `pandas`, `numpy` | Đọc CSV/JSON, làm sạch, biến đổi dữ liệu |
| NLP tiếng Việt | `underthesea` | Tách từ tiếng Việt |
| Trực quan hóa | `matplotlib`, `seaborn`, `wordcloud` | Vẽ biểu đồ và đám mây từ |
| Học máy | `scikit-learn`, `scipy` | TF-IDF, Logistic Regression, đánh giá mô hình |
| Notebook | `jupyter`, `notebook` | Mở và chạy file `.ipynb` |

Toàn bộ version trong `requirements.txt` đã được **cài đặt và kiểm thử thực tế trong một môi
trường sạch** (không phải xuất từ `pip freeze` của máy cá nhân) — nhóm đã xác nhận notebook chạy
thành công 100% (0 lỗi) khi cài đặt chỉ bằng đúng file này trên một virtual environment mới, đảm
bảo khả năng tái lập trên máy khác.

## 5. Hướng dẫn cài đặt và chạy

### Bước 1 — Tạo môi trường ảo (khuyến khích, không bắt buộc)

```bash
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
```

### Bước 2 — Cài đặt thư viện

```bash
pip install -r requirements.txt
```

### Bước 3 — Mở và chạy notebook

```bash
jupyter notebook notebook/1_tai_du_lieu.ipynb
```

Sau khi notebook mở ra, chọn **Kernel → Restart & Run All** để chạy tuần tự toàn bộ từ đầu đến
cuối. Notebook đã được kiểm thử chạy thành công theo đúng cách này trước khi nộp.

> **Lưu ý về đường dẫn:** notebook đọc dữ liệu bằng đường dẫn tương đối `../data/...` (tính từ vị
> trí notebook trong thư mục `notebook/`). Nếu bạn di chuyển notebook sang vị trí khác, hãy giữ
> nguyên cấu trúc `data/` nằm cùng cấp với thư mục `notebook/`, hoặc đặt trực tiếp 2 file dữ liệu
> vào cùng thư mục với notebook — hàm `tim_duong_dan()` trong notebook sẽ tự dò tìm cả hai vị trí.

## 6. Nội dung chính trong notebook

1. Đọc dữ liệu từ 2 nguồn/định dạng khác nhau (CSV + JSON), gộp và chuẩn hóa nhãn.
2. Tiền xử lý: loại dữ liệu thiếu, trùng lặp, dữ liệu ngoại lai (câu không phải tiếng Việt),
   tách từ bằng `underthesea`, loại từ dừng.
3. Phân tích cảm xúc theo phương pháp từ điển (lexicon-based).
4. Trả lời 5 câu hỏi phân tích, kèm 5 loại biểu đồ trực quan hóa (bar, pie, grouped bar,
   boxplot, wordcloud) và diễn giải ý nghĩa từng biểu đồ.
5. Phân tích cảm xúc bằng mô hình học máy (TF-IDF + Logistic Regression) — nội dung nâng cao.
6. So sánh kết quả 2 phương pháp và kết luận.

 |STT|       Họ và tên          |    MSSV    | Nhiệm vụ đảm nhận | Đánh giá |                                                
 | 1 | **Nguyễn Phương Nam**    | 3120225094 | Đọc/gộp dữ liệu, Mô hình Học máy, Quản lý GitHub. | 100% |                    
 | 2 | **Đào Nhật Minh**        | 3120225091 | Tiền xử lý ngôn ngữ, Trực quan hóa , Hoàn thiện README. | 100% |              
 | 3 | **Thái Thị Hoàng Trinh** | 3120225163 | Lập trình Từ điển; Tổng hợp số liệu và viết báo cáo Word. | 100% |             

