1. 
Tóm tắt đề bài, những yêu cầu của đồ án
Phần A, B cần làm gì, liệt kê ra thành bảng trong đoạn chat, không tạo file

2. 
Hướng dẫn tôi hoàn thành bài lab, từng bước cụ thể, từ kĩ thuật đến tổ chức file,... Tuy nhiên:
- Nếu có code: Chưa được chỉnh sửa trên file của tôi, Đưa hướng giải trước
- Không được tạo file, trả lời ngay trong đoạn chat
- Nếu có nhiều cách lựa chọn trả lời cho 1 vấn đề, sau khi chọn cách trả lời nào đó rồi, phải đưa ra lý do chọn câu trả lời đó, liệt kê các cách khác và lý do tại sao lại chọn câu trả lời đó thay vì những câu trả lời khác, có sự so sánh
- Hiện tại tôi có tạo 1 repo riêng cho pj này rồi và chưa up gì lên, tôi sử dụng github desktop, tôi muốn clone repo về máy và commit trên file đó

3. 
Áp dụng các ràng buộc chung của bài. Hãy phân tích index.html và đề xuất bảng chuyển từ phần tử hiện tại sang HTML ngữ nghĩa, bao gồm card trong template. Giữ mọi id, class và data attribute; giữ giao diện. Giải thích lựa chọn ul/li, h1/h2, form/label, button và disabled; so sánh với các cách khác. Nêu những div nên giữ lại. Đưa checklist đạt selfCheck 8/8 và kiểm tra bàn phím. viết code thay thế trong đoạn chat

4. 
Áp dụng các ràng buộc chung. Hãy đề xuất hướng hoàn thành TODO B1 trong app.js: đúng một click listener trên catalogue, xác định nút Add bằng closest, bỏ qua nút disabled và click ngoài Add, cập nhật cart theo data-id, render tổng số lượng bằng textContent. Giải thích cách xử lý số lượng chưa tồn tại và vì sao cách này hoạt động với Belt sau Load more. So sánh với listener riêng từng nút. Viết code thay thế ngay trong đoạn chat, không sửa file

5.
Áp dụng các ràng buộc chung. Hãy đề xuất hướng hoàn thành B2: lọc theo tên bằng chuỗi đã trim và chuyển chữ thường; giữ riêng nội dung gốc để thông báo không có kết quả nhắc lại chính xác. Lấy card hiện tại mỗi lần chạy để hỗ trợ Load more, dùng hidden, cập nhật duy nhất statusBox.textContent và nghe sự kiện input. Giải thích lựa chọn so với keyup, change, regex, innerHTML và danh sách card lưu từ lúc tải trang. Nêu kiểm tra trước/sau Load more và chuỗi thử trong hàng 8 của Done means. Viết code trong đoạn chat, không sửa file

6.
Áp dụng các ràng buộc chung. Hãy đề xuất cách hoàn thành B3 bằng submit listener trên searchInput.form, gọi preventDefault rồi applyFilter. Giải thích vì sao cách này xử lý cả Enter và nút Search; so sánh với chỉ nghe click hoặc chặn keydown. Nêu cách kiểm tra URL không thêm ?q=cap, trang không reload và số lượng giỏ vẫn giữ nguyên. Chỉ đưa hướng giải trong chat, chưa viết code thay thế hoặc sửa file.

7. 
Áp dụng các ràng buộc chung. Hãy đề xuất cách mở rộng renderCart để tính tổng giá nhân số lượng từ data-price, chuyển chuỗi bằng Number, định dạng vi-VN và ghi vào cartTotal bằng textContent. Tổng phải tính cả sản phẩm bị ẩn khi lọc và Belt sau Load more. So sánh với phân tích chữ trong .price hoặc tạo thêm bảng giá riêng. Đưa các ca kiểm tra có phép tính cụ thể. Chưa viết code thay thế hoặc sửa file.

8.
Rà soát bản cuối của IA#2 theo toàn bộ bảng Done means trong README. Giữ nguyên mọi id, class, data attribute và dữ liệu sản phẩm. Trong mã nguồn, chỉ index.html và app.js được phép thay đổi; không sửa style.css, check.js hoặc README.md. Giữ nguyên phần Load more được cung cấp. B1 phải có đúng một click listener trên catalogue; dữ liệu người dùng phải được hiển thị bằng textContent; tìm kiếm phải hỗ trợ sản phẩm sau Load more; Enter và Search không reload trang. B4 phải tính đúng tổng tiền, kể cả sản phẩm đang bị ẩn, và hiển thị tổng tiền khi khởi tạo. Chỉ báo cáo phát hiện và hướng sửa trong chat, không tạo hoặc sửa file; phân biệt kiểm tra bằng đọc code với kiểm tra đã chạy trong trình duyệt.