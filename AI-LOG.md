## A — Semantic HTML

### Tool

- Codex.

### Request

- Yêu cầu đề xuất cách chuyển các phần tử trong index.html sang
  HTML ngữ nghĩa, bao gồm card trong template.
- Giữ nguyên các id, class, data attribute và dữ liệu sản phẩm.
- Giữ giao diện; không sửa style.css hoặc check.js.
- Yêu cầu giải thích lựa chọn phần tử và đưa code trong chat
  để tôi tự áp dụng.

### Accepted

- Dùng header, nav, main và footer để xác định các vùng chính
  của trang.
- Dùng một h1 cho tiêu đề Catalogue và h2 cho tên sản phẩm.
- Dùng ul cho danh sách sản phẩm và li cho từng card.
- Dùng form cho tìm kiếm; kết nối label với input bằng for="q".
- Đổi Search thành button type="submit"; các nút Add và
  Load more thành button type="button".
- Thêm thuộc tính disabled cho Add của Tote bag, đồng thời
  giữ nguyên class "button add disabled".
- Dùng p cho thông tin giá và tình trạng hàng.
- Áp dụng cấu trúc li, h2, p và button tương ứng trong
  card-template để sản phẩm tải thêm có cùng cấu trúc.
- Dùng aria-label cho navigation và form tìm kiếm,
  role="search" cho form và role="status" cho vùng thông báo.
- Giữ div cho brand, vùng chứa Load more và vùng status;
  vùng status được bổ sung role để thể hiện chức năng.
- Giữ nguyên các id, class, data attribute và dữ liệu sản phẩm.
- Tôi tự áp dụng phương án Codex cung cấp.

### Changed

- Không có. Tôi áp dụng nguyên bản phương án Codex cung cấp,
  không yêu cầu điều chỉnh lại ở phần A.

### Rejected

- Không có. Tôi không loại bỏ đề xuất nào trong phương án
  Codex cung cấp cho phần A.

### Verification

- Chạy selfCheck() trong Console.
- Kết quả: "Session 4 self-check: 8/8 passed".
- Đạt hàng 1 trong bảng Done means.


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
- Dùng closest('.card') để tìm card chứa nút, sau đó đọc
  mã sản phẩm từ card.dataset.id.
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


## B2 — Filter as you type

### Tool

- Codex.

### Request

- Yêu cầu hoàn thành B2: lọc sản phẩm theo tên bằng chuỗi
  đã trim và chuyển chữ thường.
- Giữ riêng nội dung gốc để thông báo không có kết quả
  nhắc lại chính xác nội dung người dùng nhập.
- Lấy danh sách card hiện tại mỗi lần lọc để hỗ trợ Load more.
- Dùng hidden để ẩn/hiện card; cập nhật thông báo bằng
  statusBox.textContent và nghe sự kiện input.
- Yêu cầu giải thích lựa chọn so với keyup, change, regex,
  innerHTML và danh sách card lưu từ lúc tải trang.
- Yêu cầu nêu kiểm tra trước/sau Load more và chuỗi thử
  trong hàng 8 của Done means.
- Yêu cầu đưa code ngay trong chat, không sửa file.

### Accepted

- Tách rawQuery để giữ nguyên nội dung người dùng nhập
  và query đã trim().toLowerCase() để so khớp.
- Gọi catalogue.querySelectorAll('.card') bên trong
  applyFilter() để lấy cả các card vừa được Load more.
- Đọc tên sản phẩm từ .name bằng textContent và chuyển
  sang chữ thường trước khi so khớp.
- Dùng includes() để kiểm tra tên có chứa từ khóa hay không.
- Gán card.hidden theo kết quả so khớp.
- Đếm số card khớp và dùng cards.length làm tổng số sản phẩm.
- Khi từ khóa sau chuẩn hóa rỗng, hiện lại tất cả card
  và để status trống.
- Khi có kết quả, hiển thị "Showing n of total products".
- Khi không có kết quả, dùng rawQuery trong thông báo
  để giữ nguyên nội dung người dùng nhập.
- Ghi thông báo bằng statusBox.textContent, không dùng innerHTML.
- Đăng ký searchInput.addEventListener('input', applyFilter)
  để lọc khi nội dung ô nhập thay đổi.
- Giữ nguyên phần Load more và lời gọi applyFilter()
  đã được cung cấp trong đó.

### Changed

Không có

### Rejected

Không có

### Verification

- Trước Load more:
  nhập scarf và SCARF.
  Kỳ vọng: cả hai đều chỉ hiện Scarf,
  status là "Showing 1 of 8 products".
  Kết quả: [điền kết quả thực tế].

- Kiểm tra khoảng trắng:
  nhập "  SCARF  ".
  Kỳ vọng: vẫn tìm thấy Scarf.
  Kết quả: [điền kết quả thực tế].

- Kiểm tra từ khóa rỗng:
  xóa nội dung hoặc nhập toàn khoảng trắng.
  Kỳ vọng: hiện đủ 8 sản phẩm trước Load more,
  status trống.
  Kết quả: [điền kết quả thực tế].

- Kiểm tra lọc khi tải thêm:
  nhập belt trước Load more, sau đó giữ nguyên từ khóa
  và bấm Load more.
  Kỳ vọng: ban đầu không có kết quả; sau khi tải thêm,
  Belt xuất hiện với status "Showing 1 of 12 products".
  Kết quả: [điền kết quả thực tế].

- Hàng 7 trong bảng Done means, sau Load more:
  nhập scarf, SCARF, rồi xóa nội dung.
  Kỳ vọng: hai từ khóa đều cho một kết quả với status
  "Showing 1 of 12 products"; khi xóa thì hiện đủ 12 card
  và status trống.
  Kết quả: [điền kết quả thực tế].

- Hàng 8:
  nhập <img src=x onerror=alert(1)>.
  Kỳ vọng: không có alert hoặc ảnh lỗi;
  status hiển thị nguyên văn:
  No products match "<img src=x onerror=alert(1)>".
  Kết quả: No products match "<img src=x onerror=alert(1)>"

- Hàng 10 trong phạm vi kiểm tra B2:
  kiểm tra Console sau các thao tác.
  Kết quả: Không có lỗi đỏ

  ## B3 — Prevent search form reload

### Tool

- Codex.

### Request

- Yêu cầu hoàn thành B3 bằng submit listener trên searchInput.form.
- Gọi preventDefault() để ngăn gửi form mặc định, sau đó
  gọi applyFilter().
- Yêu cầu giải thích vì sao cách này xử lý cả Enter và
  nút Search; so sánh với chỉ nghe click hoặc chặn keydown.
- Yêu cầu hướng dẫn kiểm tra URL không thêm ?q=cap,
  trang không reload và số lượng giỏ được giữ nguyên.
- Yêu cầu đưa code trong chat, không sửa file.

### Accepted

- Dùng searchInput.form để lấy form chứa ô tìm kiếm.
- Đăng ký một submit listener trên form.
- Gọi event.preventDefault() trước applyFilter() để ngăn
  trình duyệt thực hiện việc gửi form mặc định.
- Gọi lại applyFilter() để cập nhật kết quả trên trang hiện tại.
- Xử lý chung thao tác Enter trong ô tìm kiếm và bấm Search.
- Tôi tự áp dụng code Codex đưa trong chat vào vị trí TODO B3
  trong app.js.

### Changed

- Không có. Tôi áp dụng nguyên bản phương án Codex cung cấp;
  các ca kiểm tra B3 đều đạt nên không yêu cầu điều chỉnh.

### Rejected

- Không có. Tôi không loại bỏ đề xuất nào trong phương án
  Codex cung cấp cho B3.

### Verification

- Đạt hàng 9 trong bảng Done means:
  thêm T-shirt hai lần để có Cart (2), nhập cap rồi nhấn Enter.
  URL không thêm ?q=cap, trang không reload, giỏ vẫn Cart (2)
  và kết quả lọc chỉ hiện Cap.

- Kiểm tra bổ sung với nút Search:
  đổi từ khóa thành scarf rồi bấm Search.
  Kết quả lọc chuyển sang Scarf; URL và số lượng giỏ giữ nguyên.

- Kiểm tra bổ sung việc reload:
  đặt window.__b3ReloadProbe = 'before-submit' trong Console.
  Sau khi nhấn Enter và bấm Search, đọc lại biến vẫn nhận
  'before-submit', xác nhận trang không bị tải lại.

- Đạt hàng 10 trong phạm vi kiểm tra B3:
  Console không có lỗi đỏ.

  ## B4 — Cart total

### Tool

- Codex.

### Request

- Yêu cầu mở rộng renderCart() để tính tổng tiền bằng
  giá sản phẩm nhân số lượng trong giỏ.
- Đọc giá từ data-price, chuyển chuỗi thành số bằng Number(),
  định dạng vi-VN và ghi vào cartTotal bằng textContent.
- Tổng phải tính cả sản phẩm đang bị ẩn khi tìm kiếm
  và Belt được thêm sau Load more.
- Yêu cầu so sánh với việc phân tích nội dung .price
  hoặc tạo thêm bảng giá riêng.
- Yêu cầu đưa code và các ca kiểm tra có phép tính cụ thể
  ngay trong chat, không sửa file.

### Accepted

- Giữ phần tính tổng số lượng của B1 bằng Object.values(cart)
  và reduce() với giá trị ban đầu 0.
- Lấy lại toàn bộ card trong catalogue mỗi lần renderCart()
  chạy, bao gồm card bị ẩn và card được thêm sau Load more.
- Đọc mã sản phẩm từ card.dataset.id.
- Lấy số lượng bằng cart[id] ?? 0.
- Đọc giá từ card.dataset.price và chuyển thành số
  bằng Number() trước khi tính toán.
- Cộng giá nhân số lượng của từng sản phẩm vào tổng tiền.
- Định dạng tổng bằng toLocaleString('vi-VN'),
  thêm tiền tố " · " và đơn vị " đ".
- Cập nhật cartTotal bằng textContent, giữ nguyên cấu trúc
  link Cart và các span hiện có.
- Tiếp tục dùng lời gọi renderCart() trong listener B1;
  không thêm listener cho B4 hoặc sửa phần Load more.
- Tôi tự áp dụng code Codex đưa trong chat vào app.js.

### Changed

- Không có. Tôi áp dụng phương án Codex cung cấp;
  các ca kiểm tra B4 đều đạt nên không yêu cầu điều chỉnh.

### Rejected

- Không có. Tôi không loại bỏ đề xuất nào trong phương án
  Codex cung cấp cho B4.

### Verification

- Giỏ rỗng:
  giao diện hiển thị Cart (0) · 0 đ.

- Thêm T-shirt ba lần:
  180.000 × 3 = 540.000 đ.
  Kết quả: Cart (3) · 540.000 đ.

- Thêm T-shirt hai lần và Cap một lần:
  180.000 × 2 + 95.000 = 455.000 đ.
  Kết quả: Cart (3) · 455.000 đ.

- Thêm Hoodie một lần và Socks hai lần:
  420.000 + 75.000 × 2 = 570.000 đ.
  Kết quả: Cart (3) · 570.000 đ.

- Bấm Load more rồi thêm Belt một lần:
  140.000 × 1 = 140.000 đ.
  Kết quả: Cart (1) · 140.000 đ.

- Sau Load more, thêm T-shirt hai lần và Belt một lần:
  180.000 × 2 + 140.000 = 500.000 đ.
  Kết quả: Cart (3) · 500.000 đ.

- Thử Add của Tote bag khi giỏ rỗng:
  số lượng và tổng tiền không tăng,
  vẫn là Cart (0) · 0 đ.

- Kiểm tra sản phẩm bị ẩn vẫn được tính:
  thêm T-shirt hai lần và Cap một lần,
  sau đó tìm scarf.
  T-shirt và Cap bị ẩn nhưng giỏ vẫn là Cart (3) · 455.000 đ.
  Tiếp tục Add Scarf để renderCart() chạy lại:
  180.000 × 2 + 95.000 + 160.000 = 615.000 đ.
  Kết quả: Cart (4) · 615.000 đ.
  Xóa từ khóa: số lượng và tổng tiền giữ nguyên.

- Đạt hàng 10 trong phạm vi kiểm tra B4:
  Console không có lỗi đỏ.