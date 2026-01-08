# Lab 2: FP-Growth - Phân Tích Giỏ Hàng (Market Basket Analysis)

**Môn học:** Khai phá dữ liệu (Data Mining)  
**Nhóm:** 9  
**Giảng viên:** ThS. Lê Thị Thùy Trang  

---

## 📌 Giới thiệu dự án
Dự án này là phần mở rộng của Lab 1 (Apriori). Mục tiêu chính là triển khai thuật toán **FP-Growth (Frequent Pattern Growth)** để khai phá luật kết hợp từ dữ liệu giao dịch bán lẻ.

Trong bài Lab này, chúng tôi tập trung vào việc:
1. [cite_start]Triển khai thuật toán **FP-Growth** để khắc phục nhược điểm về hiệu năng của Apriori trên tập dữ liệu lớn[cite: 70, 77].
2. [cite_start]So sánh hiệu năng (thời gian thực thi) giữa **Apriori** và **FP-Growth** với các ngưỡng `min_support` khác nhau[cite: 32].
3. [cite_start]Trực quan hóa các luật kết hợp mạnh và đưa ra đề xuất kinh doanh[cite: 131].

## 👥 Thành viên nhóm
| STT | Họ và Tên | Mã Sinh Viên | Vai trò |
|-----|-----------|--------------|---------|
| 1   | [Tên bạn] | [Mã SV]      | ...     |
| 2   | ...       | ...          | ...     |
| 3   | ...       | ...          | ...     |

---

## 📂 Cấu trúc dự án
[cite_start]Dự án được tổ chức theo cấu trúc module hóa để dễ dàng tái sử dụng và mở rộng[cite: 20]:

```bash
NHOM_9-DATA_MINING/
├── data/
│   ├── raw/                    # Dữ liệu thô (online_retail.csv)
│   └── processed/              # Dữ liệu đã xử lý (basket_bool.parquet, rules...)
├── notebooks/
│   ├── basket_preparation.ipynb        # Chuẩn bị dữ liệu giỏ hàng (từ Lab 1)
│   ├── apriori_modelling.ipynb         # Mô hình Apriori (Lab 1)
│   ├── fp_growth_modelling.ipynb       # Mô hình FP-Growth (MỚI - Lab 2) [cite: 31]
│   └── compare_apriori_fpgrowth.ipynb  # So sánh Apriori vs FP-Growth (MỚI - Lab 2) [cite: 32]
├── src/
│   ├── apriori_library.py      # Thư viện chính (Đã cập nhật class FPGrowthMiner) [cite: 23]
│   └── ...
├── requirements.txt            # Các thư viện cần thiết [cite: 58]
└── README.md                   # Tài liệu hướng dẫn
