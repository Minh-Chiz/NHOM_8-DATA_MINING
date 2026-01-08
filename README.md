# Lab 1: 🛒 Market Basket Analysis - Khai phá dữ liệu bán lẻ Online
**Môn học:** Khai phá dữ liệu (Data Mining)  
**Nhóm:** 8  
**Giảng viên:** ThS. Lê Thị Thùy Trang  


## 1. Giới thiệu dự án
Dự án này áp dụng kỹ thuật **Khai phá luật kết hợp (Association Rule Mining)** với thuật toán **Apriori** trên tập dữ liệu "Online Retail".
Mục tiêu là tìm ra thói quen mua sắm của khách hàng (khách thường mua sản phẩm A sẽ mua kèm sản phẩm B), từ đó đưa ra các chiến lược kinh doanh thông minh như bán chéo (cross-selling), sắp xếp kệ hàng và tạo combo khuyến mãi.

**Công nghệ sử dụng:**
- Python 3.11
- Thư viện: Pandas, Mlxtend (Apriori), Matplotlib/Seaborn.
- Quy trình: Data Cleaning -> Basket Preparation -> Apriori Modeling.

## 👥 Thành viên nhóm
| STT | Họ và Tên | Mã Sinh Viên | Vai trò |
|---|---|---|---|
| 1 | Vũ Ngọc Bảo | 1771020079 | Trưởng nhóm, Code chính |
| 2 | Nguyễn Đức Mạnh | 1771020456 | Phân tích EDA, Viết báo cáo |
| 3 | Hoàng Minh Chí | 1771020096 | Chạy mô hình |
| 4 | Trần Tiến Quang | 1771020569 | Viết báo cáo |

---

## 2. Kết quả phân tích (Insights)

Sau khi chạy mô hình với ngưỡng `min_support=0.01` (1%) và `min_lift=1.2`, chúng tôi đã tìm ra được **[Điền số lượng]** luật kết hợp chất lượng. Dưới đây là 5 insight nổi bật nhất:

### Insight 1: Bộ đôi "bất khả ly thân" (Lift cao nhất)
- **Luật:** Khách mua `[Tên sản phẩm A]` thường mua kèm `[Tên sản phẩm B]`.
- **Số liệu:** Confidence = [Ví dụ: 80%], Lift = [Ví dụ: 15.2].
- **Ý nghĩa:** Mối quan hệ cực mạnh. Hầu như ai mua cái này đều mua cái kia.
- **👉 Hành động:** Đặt hai sản phẩm này cạnh nhau trên kệ hoặc web. Không cần giảm giá cũng bán được cả hai.

### Insight 2: Sản phẩm chủ lực (Support cao)
- **Luật:** Các sản phẩm như `[Tên sản phẩm C]` xuất hiện trong [Ví dụ: 10%] tổng số đơn hàng.
- **Ý nghĩa:** Đây là sản phẩm "quốc dân", ai cũng cần.
- **👉 Hành động:** Đặt sản phẩm này ở trang chủ hoặc lối đi chính để thu hút traffic (khách tham quan).

### Insight 3: Combo quà tặng (Category Insight)
- **Phát hiện:** Các sản phẩm thuộc nhóm `[Ví dụ: Đồ trang trí / Túi xách]` thường được mua cùng nhau theo set.
- **👉 Hành động:** Đóng gói thành set quà tặng (Gift Box) để tăng giá trị đơn hàng trung bình (AOV).

### Insight 4: Cơ hội bán chéo (Confidence cao)
- **Luật:** Nếu khách đã bỏ `[Sản phẩm X]` vào giỏ, có [Ví dụ: 60%] khả năng họ sẽ mua thêm `[Sản phẩm Y]`.
- **👉 Hành động:** Khi khách xem sản phẩm X, hệ thống tự động gợi ý: "Bạn có muốn mua thêm Y với giá ưu đãi 5%?"

### Insight 5: Luật ngách (Niche)
- **Phát hiện:** Tuy `[Sản phẩm Z]` ít người mua (Support thấp), nhưng hễ mua là sẽ mua số lượng lớn hoặc mua kèm `[Sản phẩm W]` với Lift rất cao.
- **👉 Hành động:** Gửi email marketing riêng cho nhóm khách hàng VIP chuyên mua dòng sản phẩm này.

---

## 3. Kết luận & Đề xuất
Dựa trên dữ liệu, cửa hàng nên tập trung vào chiến lược:
1. **Tối ưu hiển thị:** Đưa các cặp sản phẩm có Lift > 2 về gần nhau.
2. **Kích cầu:** Tạo combo khuyến mãi cho các sản phẩm có Confidence cao nhưng Support còn thấp.
3. **Cá nhân hóa:** Gợi ý sản phẩm liên quan ngay tại bước thanh toán.

---

## 4. Hướng dẫn chạy dự án
Để tái lập kết quả phân tích này:

1. **Cài đặt môi trường:**
   ```bash
   conda create -n shopping_env python=3.11
   conda activate shopping_env
   pip install -r requirements.txt
