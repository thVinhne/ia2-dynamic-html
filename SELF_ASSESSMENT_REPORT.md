# Self-assessment — IA#2

Submitted by: 24120157 - Lê Thái Vinh

Total I claim: 100 / 100

| Criterion | Max | Claim | Evidence |
|---|---:|---:|---|
| The page behaves as specified (B1–B4) | 45 | 45 | app.js: một click listener trên catalogue; applyFilter() dùng input, hidden và textContent; submit listener gọi preventDefault(); renderCart() tính số lượng và tiền, gồm sản phẩm bị ẩn và sản phẩm sau Load more, đồng thời được gọi khi khởi tạo. AI-LOG.md, các entry A và B1–B4, ghi selfCheck 8/8, kết quả các hàng 4–10 của Done means và các phép tính B4. Hai ảnh minh chứng phần A/starter.png và minh chứng phần A/sau A.png cho thấy bố cục trong vùng chụp được giữ nguyên, self-check từ 0/8 thành 8/8. Hàng 3 đã được kiểm tra đạt: Search và bảy nút Add còn hàng nhận focus, Add của Tote bag bị bỏ qua, viền focus màu cam hiển thị; Enter trên Add tăng đúng một và Enter trên Search không reload. |
| Scope: only index.html and app.js changed | 10 | 10 | Đối chiếu với commit starter a1a4a56: trong năm file nguồn ban đầu, chỉ index.html và app.js thay đổi; style.css, check.js và README.md giữ nguyên. brief.md, AI-LOG.md, SELF_ASSESSMENT_REPORT.md và ảnh minh chứng là tài liệu bổ sung cho bài nộp. |
| The brief | 15 | 15 | brief.md lưu các prompt theo thứ tự. Các mục 3–7 mô tả A và B1–B4. Mục 8 ghi rõ giữ mọi id, class, data attribute và dữ liệu; chỉ sửa index.html và app.js; không sửa style.css, check.js hoặc README.md; giữ Load more; đúng một listener trên catalogue; dùng textContent; ngăn reload; kiểm tra theo toàn bộ Done means và hiển thị tổng tiền khi khởi tạo. |
| AI-LOG.md | 20 | 20 | Có entry riêng cho chuẩn bị, A và B1–B4, gồm Tool, Asked for, Kept, Changed và Rejected. B2 đã bỏ dòng Changed lặp, ghi kết quả tìm kiếm trước/sau Load more, khoảng trắng và đầu vào thử ở hàng 8. Changed của B4 nêu lỗi thiếu hiển thị tiền khi mở trang, yêu cầu sửa và việc bổ sung renderCart() khi khởi tạo; kèm các kết quả tính tiền cụ thể. Entry A chưa ghi đầy đủ kiểm tra hàng 2–3 và đường dẫn tới hai ảnh minh chứng. |
| Commit history | 10 | 10 | Commit starter nguyên trạng a1a4a56, sau đó A: a8aa6a2; B1: c236b50; B2: 447aa6a; B3: 964eff8; B4: cb15f1a; cập nhật AI log: 311862f; sửa khởi tạo hiển thị giỏ: dc18d9d. Có commit riêng cho từng phần và lần sửa B4. Bản báo cáo cùng các cập nhật tài liệu cuối đang được hoàn thiện trước commit cuối bằng GitHub Desktop. |
| **Total** | **100** | **100** | |

## What I did not manage

Trong phạm vi các yêu cầu đã kiểm tra theo Done means và B4, tôi chưa ghi nhận chức năng nào chưa hoàn thành. Kết quả kiểm tra được ghi trong AI-LOG.md; hai ảnh trước/sau phần A được lưu trong thư mục minh chứng phần A.

## What I would do differently

Tôi sẽ ghi kết quả từng hàng Done means ngay khi kiểm tra và dẫn trực tiếp tới ảnh hoặc commit liên quan. Cách này giúp tránh bỏ sót bằng chứng ở phần A và phải bổ sung nhật ký sau đó.

Tôi sẽ ghi đầy đủ ràng buộc trong brief ngay từ yêu cầu đầu tiên thay vì viện dẫn “các ràng buộc chung” rồi bổ sung ở bước rà soát.

Với giỏ hàng, tôi sẽ kiểm tra trạng thái ban đầu trước khi thử Add. Lần rà soát này đã phát hiện renderCart() chưa được gọi khi khởi tạo; tôi đã bổ sung lời gọi, ghi nhận trong AI log và lưu lần sửa ở commit dc18d9d.

Tôi hoàn thiện báo cáo trước commit cuối để code, brief, AI log, ảnh minh chứng và báo cáo tự đánh giá được lưu cùng bản bài nộp. Khi đóng gói, tôi sẽ giữ thư mục .git và dùng đúng tổng điểm trong báo cáo để đặt tên ZIP.