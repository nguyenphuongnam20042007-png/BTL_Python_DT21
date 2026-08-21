# 📖 HƯỚNG DẪN CÀI ĐẶT & CHẠY CHƯƠNG TRÌNH

**Phân tích cảm xúc bình luận tiếng Việt - Đề tài DT21**

---

## 📋 MỤC LỤC

1. [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
2. [Cài đặt Python 3.13.19](#bước-1-cài-đặt-python-31319)
3. [Tải & Setup Project](#bước-2-tải--setup-project)
4. [Chạy chương trình](#bước-3-chạy-chương-trình)
5. [Troubleshooting](#troubleshooting)

---

## ✅ YÊU CẦU HỆ THỐNG

- **Python:** 3.13.19 trở lên
- **RAM:** 2GB trở lên
- **Ổ cứng:** 500MB trống
- **OS:** Windows, macOS, hoặc Linux

---

## 🐍 BƯỚC 1: CÀI ĐẶT PYTHON 3.13.19

### 1.1 Tải Python

**Truy cập:** https://www.python.org/downloads/

Tìm và tải **Python 3.13.19** (hoặc 3.13 mới nhất)

### 1.2 Cài đặt

#### 🪟 Windows:
```
1. Chạy file .exe
2. ⚠️ QUAN TRỌNG: Tick ☑️ "Add python.exe to PATH"
3. Click "Install Now"
4. Chờ hoàn thành
```

#### 🍎 macOS:
```
1. Chạy file .pkg
2. Làm theo hướng dẫn trên màn hình
3. Nhập password khi cần
```

#### 🐧 Linux (Ubuntu/Debian):
```bash
sudo apt update
sudo apt install python3.13 python3.13-venv
```

### 1.3 Kiểm tra cài đặt

Mở Terminal/Command Prompt và chạy:

```bash
python --version
```

✅ Kết quả phải là: `Python 3.13.19` (hoặc 3.13.x)

---

## 📁 BƯỚC 2: TẢI & SETUP PROJECT

### 2.1 Tải Project

**Cách A - Nếu có Git:**
```bash
git clone <link_repo>
cd project_folder
```

**Cách B - Download ZIP:**
1. Download file ZIP từ GitHub
2. Giải nén vào thư mục bất kỳ
3. Mở Terminal, cd vào thư mục đó

### 2.2 Tạo Virtual Environment

Virtual environment giúp cài thư viện riêng, tránh xung đột.

#### Windows:
```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS/Linux:
```bash
python3 -m venv venv
source venv/bin/activate
```

✅ **Nếu thành công**, bạn sẽ thấy `(venv)` ở đầu dòng lệnh:
```
(venv) C:\Users\...\project>    # Windows
(venv) user@computer:~/project$ # macOS/Linux
```

### 2.3 Cài đặt thư viện

```bash
pip install -r requirements.txt
```

**Chờ 5 phút** để cài tất cả các thư viện cần thiết

✅ Hoàn thành khi thấy: `Successfully installed ...`

---

## ▶️ BƯỚC 3: CHẠY CHƯƠNG TRÌNH

Chọn **1 trong 2 cách** dưới đây:

---

## 🔹 **CÁCH 1: JUPYTER NOTEBOOK (Dễ nhất)**

### Cài đặt thêm Jupyter (nếu chưa có)
```bash
pip install jupyter notebook
```

### Chạy Jupyter
```bash
jupyter notebook
```

✅ Browser tự mở, bạn sẽ thấy danh sách file/folder

### Chạy code
1. Click vào folder `notebook/`
2. Click vào file `1_tai_du_lieu.ipynb`
3. Notebook mở ra
4. Nhấn **Kernel** → **Restart & Run All**
5. Chờ 3-5 phút cho code chạy xong

### Xem kết quả
- 📊 **Biểu đồ** hiển thị tự động
- 📈 **Độ chính xác:** Accuracy = 79.45%
- 📝 **Phân tích:** Chi tiết từng câu hỏi
- 📋 **Thống kê:** Số liệu được ghi rõ

---

## 🔹 **CÁCH 2: VS CODE (Chuyên nghiệp)**

### Bước 1: Cài VS Code
Tải từ: https://code.visualstudio.com/

### Bước 2: Cài Extension Python
1. Mở VS Code
2. Click **Extensions** (biểu tượng 4 khối ở thanh bên trái)
3. Tìm **"Python"** (của Microsoft)
4. Click **Install**

### Bước 3: Cài Extension Jupyter (nếu muốn chạy .ipynb)
1. Tìm **"Jupyter"** (của Microsoft)
2. Click **Install**

### Bước 4: Mở Project trong VS Code
1. **File** → **Open Folder**
2. Chọn folder project của bạn
3. Click **Select Folder**

### Bước 5: Kích hoạt Virtual Environment

Nhấn **Ctrl + `** (backtick) để mở Terminal:

#### Windows:
```bash
venv\Scripts\activate
```

#### macOS/Linux:
```bash
source venv/bin/activate
```

✅ Nếu thành công, thấy `(venv)` ở đầu dòng

### Bước 6: Chọn Python Interpreter

1. Nhấn **Ctrl + Shift + P** (hoặc **Cmd + Shift + P** trên Mac)
2. Gõ: `Python: Select Interpreter`
3. Chọn **"./venv/bin/python"**

### Bước 7: Chạy code

#### Cách 7.1: Chạy file Python thường (.py)
- Mở file `.py` bất kỳ
- Click nút **▶️ (Play)** ở góc trên phải
- hoặc nhấn **F5**

#### Cách 7.2: Chạy Jupyter Notebook (.ipynb)
- Mở file `1_tai_du_lieu.ipynb`
- Click **▶️** trước mỗi cell hoặc **Run All**

#### Cách 7.3: Chạy qua Terminal
```bash
# Python file
python script.py

# Jupyter notebook
jupyter notebook
```

---

## ✅ KIỂM TRA CÀI ĐẶT THÀNH CÔNG

Nếu bạn thấy một trong những dấu hiệu này → **Mọi thứ OK!** ✅

- ✅ Jupyter hiển thị danh sách file/folder
- ✅ File `.ipynb` mở được trong VS Code
- ✅ Code chạy không có lỗi đỏ
- ✅ Hiển thị biểu đồ (bar, pie, boxplot, v.v.)
- ✅ Thấy: `Accuracy: 79.45%`

---

## 📊 CẤU TRÚC THƯMỤC (BẮT BUỘC)

Đảm bảo cấu trúc như thế này:

```
project_folder/
│
├── data/
│   ├── uit_vsfc.csv              ✅ File CSV (8.144 dòng)
│   └── du_lieu_them.json         ✅ File JSON (5 dòng)
│
├── notebook/
│   └── 1_tai_du_lieu.ipynb      ✅ File code chính
│
├── venv/                         (Tạo auto)
├── README.md
├── requirements.txt              ✅ Danh sách thư viện
└── .gitignore (tùy chọn)
```

⚠️ **QUAN TRỌNG:** Folder `data/` phải ở cùng cấp với folder `notebook/`

---

## 🆘 TROUBLESHOOTING

### ❌ Lỗi: "Python not found" hoặc "Command not found"

**Nguyên nhân:** Python chưa được thêm vào PATH

**Giải pháp:**
1. Tải lại Python 3.13.19
2. **Khi cài đặt, TICK ☑️ "Add python to PATH"**
3. Restart máy
4. Thử lại `python --version`

---

### ❌ Lỗi: "No module named 'pandas'" hoặc "No module named 'underthesea'"

**Nguyên nhân:** Virtual environment chưa được kích hoạt

**Giải pháp:**

```bash
# Kích hoạt venv trước
source venv/bin/activate      # macOS/Linux
venv\Scripts\activate          # Windows

# Rồi cài lại
pip install -r requirements.txt
```

---

### ❌ Lỗi: "requirements.txt not found"

**Nguyên nhân:** Không ở trong folder project

**Giải pháp:**
```bash
# Kiểm tra bạn ở folder nào
pwd          # macOS/Linux
cd           # Windows

# Vào folder project chứa requirements.txt
cd /đường/dẫn/đến/project

# Rồi cài
pip install -r requirements.txt
```

---

### ❌ Lỗi: "Jupyter not found"

**Giải pháp:**
```bash
pip install jupyter notebook
jupyter notebook
```

---

### ❌ Lỗi: ".ipynb không mở được trên VS Code"

**Giải pháp:**
1. Cài Extension Jupyter (xem Bước 2 CÁCH 2)
2. Nhấn **Ctrl + Shift + P** → "Reload Window"
3. Mở lại file `.ipynb`

---

### ❌ Lỗi: "File not found" hoặc dữ liệu không tải được

**Nguyên nhân:** Cấu trúc thư mục sai

**Giải pháp:**
```
Đảm bảo:
- Folder "data/" có file uit_vsfc.csv
- Folder "data/" có file du_lieu_them.json
- Folder "data/" ở cùng cấp với folder "notebook/"
```

---

## 📝 QUY TRÌNH NHANH (Lần sau)

Sau lần đầu cài đặt, lần sau chỉ cần:

```bash
# 1. Mở Terminal, cd vào project
cd /đường/dẫn/đến/project

# 2. Kích hoạt venv
source venv/bin/activate      # macOS/Linux
venv\Scripts\activate          # Windows

# 3. Chạy code
jupyter notebook               # Jupyter
# hoặc
code .                        # VS Code
```

**Tổng cộng:** 30 giây thay vì 20 phút! ⚡

---

## 🎯 TÓBM TẮT

| Bước | Lệnh | Thời gian |
|------|------|---------|
| 1. Cài Python | Tải & cài | 10 phút |
| 2. Tạo venv | `python -m venv venv` | 2 phút |
| 3. Cài thư viện | `pip install -r requirements.txt` | 5 phút |
| 4. Chạy code | `jupyter notebook` | 30 giây |
| **TỔNG** | - | **~20 phút** |

---

## 💡 MẸO

1. **Để kích hoạt venv nhanh hơn**, tạo file `.bat` (Windows) hoặc `.sh` (Mac/Linux):
   ```bash
   source venv/bin/activate && jupyter notebook
   ```

2. **Nếu lỗi pip**, thử:
   ```bash
   pip install --upgrade pip
   ```

3. **Nếu slow**, đóng browser rồi mở lại Jupyter

---

## 📞 CẦN GIÚP?

Kiểm tra trong thứ tự này:
1. ✅ Python cài đúng? `python --version` → 3.13.19
2. ✅ Virtual environment kích hoạt? Thấy `(venv)` chưa?
3. ✅ Thư viện cài đầy đủ? `pip list` → có pandas, numpy, ...
4. ✅ Cấu trúc thư mục đúng? Có folder `data/` không?
5. ✅ Restart VS Code / Browser

---

## 📚 TÀI LIỆU KHÁC

- `README_CHUYEN_NGHIEP.md` - Thông tin chi tiết về dự án
- `README_TLDR.md` - Tóm tắt dự án
- `HUONG_DAN_CHAY_TREN_VS_CODE.md` - Chi tiết hơn cho VS Code

---

**Chúc bạn cài đặt & chạy chương trình thành công! 🚀**
