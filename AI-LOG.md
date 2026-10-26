# AI-LOG.md — CSC13008 IA#2

## [2026-10-27] — Chuẩn bị thư mục và quy trình làm bài
Tool: Codex.
Asked for: Hướng dẫn tổ chức thư mục, lưu starter bằng Git và chia bài thành các phần để thực hiện.
Kept: Giữ các file bài làm trong một thư mục chung để thuận tiện quản lý.
Changed: Dùng D:\Downloads\ia2-dynamic-html làm thư mục bài làm và quản lý bài trên GitHub, phù hợp với cách tôi đang tổ chức file.
Rejected: Không áp dụng phần hướng dẫn chạy các lệnh Git trong terminal; tôi sử dụng GitHub Desktop để quản lý bài.

## [2026-10-27] — A: HTML ngữ nghĩa
Tool: Codex.
Asked for: Đề xuất cách chuyển index.html sang HTML ngữ nghĩa, bao gồm card trong template, giữ nguyên id, class, data attribute, dữ liệu và giao diện; không sửa style.css hoặc check.js; giải thích lựa chọn và đưa code trong chat để tôi tự áp dụng.
Kept: Dùng header, nav, main và footer cho các vùng chính; một h1 cho Catalogue và h2 cho tên sản phẩm; ul cho danh sách và li cho từng card. Dùng form tìm kiếm, nối label với input bằng for="q"; Search là button type="submit", Add và Load more là button type="button". Thêm disabled cho Add của Tote bag, giữ class "button add disabled". Dùng p cho giá và tình trạng hàng; áp dụng li, h2, p và button tương ứng trong card-template. Dùng aria-label cho navigation và form tìm kiếm, role="search" cho form, role="status" cho vùng thông báo. Giữ div cho brand, vùng chứa Load more và status. Giữ nguyên id, class, data attribute và dữ liệu sản phẩm. Tôi tự áp dụng phương án Codex cung cấp.
Changed: Không có. Tôi áp dụng nguyên bản phương án và không yêu cầu điều chỉnh. Đã chạy selfCheck() trong Console, nhận "Session 4 self-check: 8/8 passed", đạt hàng 1 của Done means.
Rejected: Không có. Tôi không loại bỏ đề xuất nào trong phương án phần A.

## [2026-10-27] — B1: Thêm sản phẩm vào giỏ
Tool: Codex.
Asked for: Hoàn thành B1 bằng đúng một click listener trên catalogue, xác định Add bằng closest(), bỏ qua disabled và click ngoài Add, cập nhật cart theo data-id và tổng số lượng bằng textContent; giải thích thuật toán, so sánh với listener riêng từng nút và đưa code trong chat.
Kept: Dùng một click listener trên catalogue và event.target.closest('.add') để nhận diện Add, kể cả khi click vào phần tử con. Kiểm tra nút thuộc catalogue và không bị disabled. Tìm card bằng closest('.card'), đọc card.dataset.id và tăng số lượng bằng (cart[id] ?? 0) + 1. Gọi renderCart() sau mỗi lần thêm hợp lệ. Dùng Object.values(cart) và reduce() với giá trị ban đầu 0 để tính tổng số lượng, cập nhật cartCount bằng textContent. Giữ nguyên phần Load more. Tôi tự áp dụng code vào app.js.
Changed: Không có. Các ca kiểm tra B1 đều đạt nên tôi không yêu cầu điều chỉnh:
- Hàng 4: Add T-shirt hai lần được Cart (2); thử Add của Tote bag không làm tăng số lượng.
- Hàng 5: Tab đến Add của sản phẩm còn hàng rồi nhấn Enter, số lượng tăng đúng 1.
- Hàng 6: Load more rồi Add của Belt, số lượng tăng đúng 1.
- Hàng 10 trong phạm vi B1: Console không có lỗi đỏ.
- Kiểm tra bổ sung: click tên, giá hoặc khoảng trống trong card không làm tăng số lượng.
Rejected: Không có. Tôi không loại bỏ đề xuất nào trong phương án B1.

## [2026-10-27] — B2: Lọc sản phẩm khi nhập
Tool: Codex.
Asked for: Hoàn thành B2 bằng cách lọc tên với chuỗi đã trim và chuyển chữ thường, giữ nguyên nội dung gốc cho thông báo không có kết quả, lấy lại card mỗi lần lọc, dùng hidden, textContent và sự kiện input; giải thích các lựa chọn, đưa code trong chat và hướng dẫn kiểm tra trước/sau Load more.
Kept: Tách rawQuery để giữ nguyên nội dung nhập và query đã trim().toLowerCase() để so khớp. Gọi catalogue.querySelectorAll('.card') bên trong applyFilter() để lấy cả card mới. Đọc .name bằng textContent, chuyển sang chữ thường rồi kiểm tra bằng includes(). Gán card.hidden theo kết quả, đếm số card khớp và dùng cards.length làm tổng. Khi query rỗng, hiện lại tất cả card và để status trống; khi có kết quả, hiển thị "Showing n of total products"; khi không có kết quả, dùng rawQuery trong thông báo. Cập nhật bằng statusBox.textContent, không dùng innerHTML. Đăng ký searchInput.addEventListener('input', applyFilter). Giữ nguyên Load more và lời gọi applyFilter() có sẵn.
Changed: Không có. Kết quả kiểm tra đã ghi nhận:
- Hàng 8: nhập <img src=x onerror=alert(1)>, status hiển thị nguyên văn No products match "<img src=x onerror=alert(1)>". [Bổ sung quan sát thực tế về alert và ảnh lỗi.]
- Hàng 10 trong phạm vi B2: Console không có lỗi đỏ.

Các ca kiểm tra sau chưa được điền kết quả thực tế:
- Trước Load more, nhập scarf và SCARF: [kết quả thực tế; kỳ vọng chỉ hiện Scarf và "Showing 1 of 8 products"].
- Nhập "  SCARF  ": [kết quả thực tế; kỳ vọng vẫn tìm thấy Scarf].
- Xóa nội dung hoặc nhập toàn khoảng trắng: [kết quả thực tế; kỳ vọng hiện đủ 8 sản phẩm trước Load more và status trống].
- Nhập belt trước Load more, giữ từ khóa rồi bấm Load more: [kết quả thực tế; kỳ vọng ban đầu không có kết quả, sau đó Belt xuất hiện với "Showing 1 of 12 products"].
- Hàng 7 sau Load more, nhập scarf, SCARF rồi xóa: [kết quả thực tế; kỳ vọng mỗi từ khóa cho một kết quả với "Showing 1 of 12 products", xóa thì hiện đủ 12 card và status trống].
Rejected: Không có. Tôi không loại bỏ đề xuất nào trong phương án B2.

## [2026-10-27] — B3: Ngăn form tìm kiếm tải lại trang
Tool: Codex.
Asked for: Hoàn thành B3 bằng submit listener trên searchInput.form, gọi preventDefault() rồi applyFilter(), giải thích cách xử lý Enter và Search, so sánh với click hoặc keydown, đưa code trong chat và hướng dẫn kiểm tra URL, reload và số lượng giỏ.
Kept: Lấy form bằng searchInput.form, đăng ký một submit listener, gọi event.preventDefault() trước applyFilter(). Dùng cùng cách xử lý cho Enter trong ô tìm kiếm và bấm Search. Tôi tự áp dụng code vào vị trí TODO B3 trong app.js.
Changed: Không có. Các ca kiểm tra B3 đều đạt nên tôi không yêu cầu điều chỉnh:
- Hàng 9: thêm T-shirt hai lần được Cart (2), nhập cap rồi Enter. URL không thêm ?q=cap, trang không reload, giỏ vẫn Cart (2) và chỉ hiện Cap.
- Đổi từ khóa thành scarf rồi bấm Search: kết quả chuyển sang Scarf, URL và số lượng giỏ giữ nguyên.
- Đặt window.__b3ReloadProbe = 'before-submit' trong Console. Sau Enter và Search, biến vẫn có giá trị 'before-submit', xác nhận trang không tải lại.
- Hàng 10 trong phạm vi B3: Console không có lỗi đỏ.
Rejected: Không có. Tôi không loại bỏ đề xuất nào trong phương án B3.

## [2026-10-27] — B4: Tổng tiền giỏ hàng
Tool: Codex.
Asked for: Mở rộng renderCart() để tính tổng giá nhân số lượng từ data-price, chuyển giá bằng Number(), định dạng vi-VN và cập nhật cartTotal bằng textContent, bao gồm sản phẩm bị ẩn và Belt sau Load more; so sánh với đọc .price hoặc tạo bảng giá riêng và đưa code cùng các ca kiểm tra trong chat.
Kept: Giữ cách tính số lượng của B1 bằng Object.values(cart) và reduce() với giá trị ban đầu 0. Lấy toàn bộ card mỗi lần renderCart() chạy, gồm card bị ẩn và card thêm sau Load more. Đọc card.dataset.id, lấy số lượng bằng cart[id] ?? 0, chuyển card.dataset.price bằng Number() rồi cộng giá nhân số lượng. Định dạng bằng toLocaleString('vi-VN'), thêm tiền tố " · " và đơn vị " đ". Cập nhật cartTotal bằng textContent, giữ nguyên link Cart và các span. Tiếp tục dùng lời gọi renderCart() trong listener B1, không thêm listener cho B4 hoặc sửa Load more. Tôi tự áp dụng code vào app.js.
Changed: Không có. Các ca kiểm tra B4 đều đạt nên tôi không yêu cầu điều chỉnh:
- Giỏ rỗng: Cart (0) · 0 đ.
- Ba T-shirt: 180.000 × 3 = 540.000 đ; kết quả Cart (3) · 540.000 đ.
- Hai T-shirt và một Cap: 180.000 × 2 + 95.000 = 455.000 đ; kết quả Cart (3) · 455.000 đ.
- Một Hoodie và hai Socks: 420.000 + 75.000 × 2 = 570.000 đ; kết quả Cart (3) · 570.000 đ.
- Load more rồi thêm một Belt: 140.000 × 1 = 140.000 đ; kết quả Cart (1) · 140.000 đ.
- Sau Load more, thêm hai T-shirt và một Belt: 180.000 × 2 + 140.000 = 500.000 đ; kết quả Cart (3) · 500.000 đ.
- Thử Add của Tote bag khi giỏ rỗng: số lượng và tiền không tăng, vẫn Cart (0) · 0 đ.
- Thêm hai T-shirt và một Cap, sau đó tìm scarf: các sản phẩm trong giỏ bị ẩn nhưng vẫn hiển thị Cart (3) · 455.000 đ. Add Scarf để renderCart() chạy lại: 180.000 × 2 + 95.000 + 160.000 = 615.000 đ; kết quả Cart (4) · 615.000 đ. Xóa từ khóa không làm thay đổi số lượng hoặc tổng tiền.
- Hàng 10 trong phạm vi B4: Console không có lỗi đỏ.
Rejected: Không có. Tôi không loại bỏ đề xuất nào trong phương án B4.