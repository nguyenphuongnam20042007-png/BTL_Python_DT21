# ⚡ PHÂN TÍCH CẢM XÚC TIẾNG VIỆT 

**Đề tài DT21 | Nhóm 6 | Lập trình Python**

---

## ❓ Vấn đề

Hàng triệu bình luận được tạo ra mỗi ngày trên mạng xã hội, Tiki, Shopee... nhưng **không ai có thời gian đọc hết**. Cần một công cụ tự động để phân loại: **tích cực (👍)** hay **tiêu cực (👎)** hay **trung tính (😐)**

---

## ✅ Giải pháp

| Phương pháp | Cách thức | Chính xác | Ưu điểm | Nhược điểm |
|----------|---------|---------|--------|----------|
| **Từ điển** | Đếm từ tích cực/tiêu cực | **40.96%** | Dễ hiểu | Không xử lý ngữ cảnh |
| **Học máy** | TF-IDF + Logistic Regression | **79.45%** ⭐ | Chính xác | Như hộp đen |

**Kết luận:** Máy học tốt hơn 38.5% 🚀

---

## 📊 Dữ liệu

- **Nguồn 1:** UIT-VSFC (CSV) - 8.144 bình luận về môn học
- **Nguồn 2:** Dữ liệu tự biên soạn (JSON) - 5 bình luận bổ sung
- **Xử lý:** Loại NaN (24 dòng), duplicates (12 dòng), ngoại lai tiếng Anh (315 dòng) ⚠️
- **Kết quả:** 7.834 bản ghi sạch ✅

---

## 🏗️ Kiến trúc

```
4 Lớp (Classes):
1. DocDuLieu              → Đọc CSV + JSON, gộp dữ liệu
2. TienXuLyVanBan        → Tách từ, loại stopword
3. PhanTichTuDien        → Từ điển (40.96%)
4. MoHinhHocMayCamXuc    → ML (79.45%)
```

---

## 🔬 5 Câu hỏi phân tích được trả lời

| # | Câu hỏi | Trả lời | Biểu đồ |
|---|--------|--------|--------|
| 1 | Top 5 từ xuất hiện nhiều? | giảng_viên, sinh_viên, môn, học, tốt | Bar |
| 2 | % tích cực ở từng chủ đề? | Khá đồng đều (~25% mỗi cái) | Pie |
| 3 | Chủ đề nào có % tiêu cực cao? | **Cơ sở vật chất (36.3%)** | Grouped Bar |
| 4 | Bình luận tiêu cực dài hơn? | **Có** (con người khi chê hay trình bày chi tiết) | Boxplot |
| 5 | Từ đặc trưng của mỗi cảm xúc? | Positive: "tận_tâm", Negative: "khó_hiểu" | WordCloud |

---

## 📈 Kết quả chính

### Phương pháp từ điển
```
Accuracy: 40.96%
Precision: negative (0.82) > positive (0.49) > neutral (0.32)
Recall:    neutral (0.64) > positive (0.43) > negative (0.19)
```
👉 *Kết luận: Phương pháp "thận trọng" - chỉ gán negative khi rất chắc chắn*

### Phương pháp học máy  
```
Accuracy: 79.45% ⭐⭐⭐
Negative: F1 = 0.94 (xuất sắc!)
Positive: F1 = 0.75 (tốt)
Neutral:  F1 = 0.68 (khó phân biệt)
```
👉 *Kết luận: ML hiệu quả hơn từ điển tới **38.5 điểm phần trăm***

---

## 🛠️ Cách chạy

```bash
# 1. Cài đặt
pip install -r requirements.txt

# 2. Mở notebook
jupyter notebook notebook/1_tai_du_lieu.ipynb

# 3. Chọn Kernel → Restart & Run All
```

**Thời gian:** ~3-5 phút chạy hết

---

## 📁 Cấu trúc thư mục

```
├── data/
│   ├── uit_vsfc.csv          (8.144 bản ghi)
│   └── du_lieu_them.json     (5 bản ghi)
├── notebook/
│   └── 1_tai_du_lieu.ipynb   (Code chính)
├── README.md                 (File này)
└── requirements.txt          (Thư viện)
```

---

## 🔑 Điểm nổi bật

✅ **Phát hiện dữ liệu ngoại lai:** 315 dòng tiếng Anh lẫn trong CSV (3.9%) - Chất lượng dữ liệu tốt!

✅ **2 Phương pháp so sánh:** Không chỉ làm, mà còn so sánh được khi nào dùng cái nào

✅ **4 Lớp OOP:** Tuân thủ nguyên tắc lập trình sạch - dễ bảo trì, mở rộng

✅ **5 Loại biểu đồ:** Bar, Pie, Grouped Bar, Boxplot, WordCloud - Trực quan hóa đẹp

✅ **2 Nguồn dữ liệu:** CSV + JSON - Xử lý đa định dạng

---

## ⚠️ Hạn chế & Cải thiện

| Hạn chế | Cách sửa |
|--------|---------|
| Từ điển chỉ 62 từ | Dùng VietSentiWordNet hoặc mở rộng |
| Không xử lý phủ định ("không tốt") | Thêm kiểm tra từ phủ định |
| Chỉ 1 thuật toán ML | Thử SVM, Naive Bayes, XGBoost, LSTM |
| Không cross-validation | Thêm k-fold CV để kiểm chứng ổn định |

---

## 📚 Thư viện dùng

```python
pandas          # Xử lý dữ liệu
numpy           # Tính toán số học
underthesea     # Tách từ tiếng Việt ⭐
scikit-learn    # Máy học (TF-IDF, LogReg)
matplotlib      # Biểu đồ
seaborn         # Biểu đồ đẹp
wordcloud       # Đám mây từ
jupyter         # Notebook
```

---

## 🎓 Kỹ năng sử dụng

- ✅ **Xử lý dữ liệu:** pandas, numpy
- ✅ **NLP tiếng Việt:** underthesea
- ✅ **Máy học:** scikit-learn (TF-IDF, Logistic Regression)
- ✅ **Trực quan hóa:** matplotlib, seaborn, wordcloud
- ✅ **Lập trình OOP:** Classes, methods, docstrings
- ✅ **Git & Jupyter Notebook:** Workflow chuyên nghiệp

---

## 🚀 Hướng phát triển

1. **Ngắn hạn:** Mở rộng từ điển, xử lý phủ định, cross-validation
2. **Trung hạn:** Thử nhiều thuật toán (SVM, XGBoost), scrape dữ liệu real-world
3. **Dài hạn:** Deep learning (LSTM, PhoBERT), web app, phân tích khía cạnh

---

## 📝 Kết luận

Dự án này **hoàn thành đầy đủ các yêu cầu** của đề DT21:
- ✅ Đọc 2+ nguồn dữ liệu
- ✅ Tiền xử lý chi tiết
- ✅ 2 phương pháp phân tích
- ✅ 5 câu hỏi + 5 biểu đồ
- ✅ So sánh & kết luận
- ✅ Mã nguồn OOP sạch
- ✅ Tài liệu đầy đủ

---

## 👥 Nhóm 6

| Người | MSSV | Công việc |
|------|------|---------|
| Nguyễn Phương Nam | 3120225094 | Nhóm trưởng |
| Đào Nhật Minh | 3120225091 | Thành viên |
| Thái Thị Hoàng Trinh | - | Thành viên |

**Giáo viên:** Nguyễn Hoàng Hải

