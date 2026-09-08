# HƯỚNG DẪN ĐẨY LÊN GITHUB & CÁCH VIẾT VÀO CV GHI ĐIỂM TUYỆT ĐỐI

---

## PHẦN 1: HƯỚNG DẪN TẠO VÀ ĐẨY LÊN GITHUB

### Cách 1: Tải lên trực tiếp bằng Web GitHub (Khuyên dùng - Nhanh nhất, không cần cài Git)

1. **Đăng nhập vào GitHub**:
   - Truy cập [https://github.com](https://github.com) và đăng nhập vào tài khoản của bạn.
2. **Tạo Repository mới**:
   - Bấm vào biểu tượng dấu **`+`** ở góc trên cùng bên phải -> Chọn **New repository**.
   - **Repository name**: Đặt tên dự án, ví dụ:
     - `shopee-ecommerce-manual-testing-portfolio`
   - **Description**: 
     - `Comprehensive Manual Testing Portfolio covering Shopee Order & Checkout journey (IEEE 829 Test Plan, 79 Test Cases, RTM, Jira-style Defect Reports, and Execution Summary).`
   - Chọn chế độ: **Public** (Để nhà tuyển dụng click vào xem được ngay).
   - **LƯU Ý**: Bỏ chọn (không tích) các ô: *"Add a README file"*, *"Add .gitignore"*, *"Choose a license"*.
   - Bấm nút xanh **Create repository**.
3. **Tải toàn bộ file lên**:
   - Ở trang vừa tạo, bấm vào dòng chữ: **`uploading an existing file`**.
   - Mở thư mục máy tính của bạn: `d:\PREPARE\TESTER\shopee-order-manual-testing-fresher-portfolio`
   - Chọn tất cả các file và thư mục con (`docs`, `test-scenarios`, `test-cases`, `bug-reports`, `test-reports`, `README.md`, `.gitignore`) rồi kéo thả vào khung upload trên trình duyệt.
   - Ở ô **Commit changes** phía dưới:
     - Nhập: `Initial commit: Shopee manual testing portfolio`
   - Bấm nút **Commit changes**.
4. **Xong!** 
   - Trang GitHub của bạn sẽ tự động hiển thị trang chủ `README.md` với đầy đủ huy hiệu, bảng biểu, sơ đồ cực kỳ chuyên nghiệp.

---

### Cách 2: Dùng lệnh Git (Nếu máy đã cài Git)

Mở PowerShell hoặc Git Bash tại thư mục dự án và chạy:

```bash
cd "d:\PREPARE\TESTER\shopee-order-manual-testing-fresher-portfolio"
git init
git add .
git commit -m "feat: complete professional manual testing portfolio for Shopee checkout flow"
git branch -M main
git remote add origin https://github.com/<TÊN_GITHUB_CỦA_BẠN>/shopee-ecommerce-manual-testing-portfolio.git
git push -u origin main
```

---

## PHẦN 2: MẪU ĐIỀN VÀO CV GHI ĐIỂM VỚI NHÀ TUYỂN DỤNG

### Mẫu Tiếng Việt:
```text
DỰ ÁN: KIỂM THỬ THỦ CÔNG HỆ THỐNG ĐẶT HÀNG & THANH TOÁN (SHOPEE E-COMMERCE)
Vai trò: Manual QA / Fresher Tester | GitHub: https://github.com/<username>/<repo-name>
- Phân tích nghiệp vụ và thiết kế bộ kiểm thử toàn diện cho quy trình Đặt hàng & Thanh toán (Checkout) trên nền tảng Shopee theo quy trình STLC và tiêu chuẩn IEEE 829.
- Xây dựng Test Plan, Ma trận truy vết yêu cầu (RTM đạt 100% test coverage) và thiết kế 79 Test Cases chi tiết bao phủ 10 phân hệ: Giỏ hàng, Địa chỉ giao hàng, Xác thực CCCD đơn quốc tế, Đơn vị vận chuyển, Áp dụng Voucher đa tầng, Shopee Xu, SPayLater, Đặt hàng đa Shop và Xuất hóa đơn VAT.
- Ứng dụng thành thạo các kỹ thuật thiết kế kiểm thử hộp đen chuẩn ISTQB: Phân vùng tương đương (EP), Phân tích giá trị biên (BVA) và Bảng quyết định (Decision Table).
- Thực thi kiểm thử (Pass rate: 94.94%), phát hiện và lập 3 Bug Report chi tiết chuẩn Jira (gồm 2 lỗi Major về logic tính toán và validation), mô tả đầy đủ Steps to Reproduce, Severity, Priority, API payload và nguyên nhân gốc.
- Hoàn thiện Báo cáo kết quả kiểm thử (Test Execution Summary Report) đánh giá rủi ro và khuyến nghị bàn giao chất lượng (Sign-off recommendation).
Kỹ năng: Manual Testing, Test Case Design (EP, BVA, Decision Table), Test Plan (IEEE 829), Bug Reporting (Jira), RTM, Excel, GitHub, E-Commerce domain.
```
