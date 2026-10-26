 ## A
### Verification
- Chạy selfCheck() trong Console.
- Kết quả: "Session 4 self-check: 8/8 passed".
- Đạt hàng 1 trong bảng Done means.
### Accepted
- Chấp nhận dùng header, nav, main và footer để xác định
  các vùng chính của trang.
- Dùng một h1 cho tiêu đề Catalogue và h2 cho tên sản phẩm.
- Dùng ul cho danh sách sản phẩm và li cho từng card.
- Dùng form cho tìm kiếm; kết nối label với input bằng for="q".
- Đổi Search thành button type="submit"; các nút Add và
  Load more thành button type="button".
- Thêm thuộc tính disabled cho Add của Tote bag,
  đồng thời giữ nguyên class "button add disabled".
- Dùng p cho thông tin giá và tình trạng hàng.
- Áp dụng cấu trúc li, h2, p và button tương ứng trong
  card-template để sản phẩm tải thêm có cùng cấu trúc.
- Chấp nhận aria-label cho navigation và form tìm kiếm,
  role="search" cho form, role="status" cho vùng thông báo.
- Giữ div cho brand, vùng chứa Load more và vùng status;
  vùng status được bổ sung role để thể hiện chức năng.
- Giữ nguyên các id, class, data attribute và dữ liệu sản phẩm.

### Changed
- Không có. Tôi áp dụng nguyên bản phương án Codex cung cấp,
  không yêu cầu điều chỉnh lại ở phần A.

### Rejected
- Không có. Tôi không loại bỏ đề xuất nào trong phương án
  Codex cung cấp cho phần A.


  ## B1 — Add to cart

### Tool
- Codex.

### Request
- Yêu cầu hoàn thành TODO B1 trong app.js bằng đúng một
  click listener trên catalogue.
- Xác định nút Add bằng closest(), bỏ qua nút disabled
  và các click ngoài Add.
- Cập nhật cart theo data-id; hiển thị tổng số lượng
  bằng textContent.
- Yêu cầu giải thích thuật toán, so sánh với listener riêng
  trên từng nút và đưa code ngay trong chat, không sửa file.

### Accepted
- Dùng một click listener trên catalogue để xử lý thao tác Add.
- Dùng event.target.closest('.add') để nhận diện nút Add,
  kể cả khi click vào phần tử con bên trong nút.
- Kiểm tra nút thuộc catalogue và bỏ qua nút disabled.
- Dùng closest('.card') để tìm card chứa nút,
  sau đó đọc mã sản phẩm từ card.dataset.id.
- Dùng (cart[id] ?? 0) + 1 để tăng số lượng;
  sản phẩm chưa có trong giỏ được tính từ 0.
- Gọi renderCart() sau mỗi lần thêm sản phẩm hợp lệ.
- Dùng Object.values(cart) và reduce() với giá trị ban đầu 0
  để tính tổng số lượng món trong giỏ.
- Cập nhật cartCount bằng textContent.
- Giữ nguyên phần Load more được cung cấp.
- Tôi tự áp dụng code Codex đưa trong chat vào app.js.

### Changed
- Không có. Tôi áp dụng phương án Codex cung cấp;
  các ca kiểm tra B1 đều đạt nên không yêu cầu điều chỉnh.

### Rejected
- Không có. Tôi không loại bỏ đề xuất nào trong phương án
  Codex cung cấp cho B1.

### Verification
- Đạt hàng 4 trong bảng Done means:
  Add T-shirt hai lần → Cart (2);
  thử Add của Tote bag → số lượng không đổi.
- Đạt hàng 5:
  dùng Tab đến nút Add của sản phẩm còn hàng,
  nhấn Enter → số lượng tăng đúng 1.
- Đạt hàng 6:
  bấm Load more, sau đó Add của Belt
  → số lượng tăng đúng 1.
- Đạt hàng 10 trong phạm vi kiểm tra B1:
  Console không có lỗi đỏ.
- Kiểm tra bổ sung:
  click tên, giá hoặc khoảng trống trong card
  → số lượng giỏ không đổi.

