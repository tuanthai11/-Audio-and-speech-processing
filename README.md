# CSE457 - Xử lý Âm thanh và Tiếng nói | Lab 3
## Nhận dạng tiếng nói nâng cao với Gaussian HMM
Tran Tuan Thai - 2151264686

Dự án này cài đặt pipeline nhận dạng từ lệnh tiếng Việt tách rời (*Isolated Word Recognition*) sử dụng **Gaussian Hidden Markov Model (HMM)**. Pipeline bao gồm các bước từ trích xuất đặc trưng động 39 chiều (MFCC + $\Delta$ + $\Delta^2$), huấn luyện whole-word HMM bằng thuật toán Baum-Welch (EM), căn chỉnh đường trạng thái bằng Viterbi, đánh giá hiệu năng với Confusion Matrix, so sánh với thuật toán DTW baseline và mở rộng re-ranking bằng Bigram Language Model.

---

## 1. Cấu trúc thư mục dự án

```text
.
├── dataset/
│   ├── train/
│   │   ├── mo/          # 6 file WAV huấn luyện cho từ "mở"
│   │   ├── dong/        # 6 file WAV huấn luyện cho từ "đóng"
│   │   ├── len/         # 6 file WAV huấn luyện cho từ "lên"
│   │   ├── xuong/       # 6 file WAV huấn luyện cho từ "xuống"
│   │   └── dung/        # 6 file WAV huấn luyện cho từ "dừng"
│   └── test/
│       ├── mo/          # 2 file WAV kiểm thử cho từ "mở"
│       ├── dong/        # 2 file WAV kiểm thử cho từ "đóng"
│       ├── len/         # 2 file WAV kiểm thử cho từ "lên"
│       ├── xuong/       # 2 file WAV kiểm thử cho từ "xuống"
│       └── dung/        # 2 file WAV kiểm thử cho từ "dừng"
├── Lab03.ipynb          # Notebook thực thi toàn bộ bài Lab
├── Lab03.py             # Script Python chạy pipeline độc lập
├── lexicon.txt          # Từ điển phát âm mẫu
├── requirements.txt     # Danh sách thư viện phụ thuộc
└── README.md            # Tài liệu hướng dẫn dự án
