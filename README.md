# HG Trend — để trợ lý AI lấy số liệu bán hàng giúp bạn

Bạn nhắn việc cho trợ lý AI như bình thường. Trợ lý dùng HG Trend để lấy dữ liệu công khai đang có trên mạng rồi trả lời bằng tiếng Việt: món bạn định bán
có ai tìm, ai đang bán, giá bao nhiêu; đối thủ đang đăng gì, chạy quảng cáo gì; khách khen chê gì; giá sỉ bên Trung Quốc.

Bộ cài này chỉ gồm chữ, không cài phần mềm nào chạy trên máy bạn. Trong đó có địa chỉ kết nối tới `hgtrend.com` và 6 kỹ năng. Kỹ năng là tệp hướng dẫn bằng
tiếng Việt, dặn trợ lý dùng công cụ nào cho việc nào, nói giá, và không nói quá con số lấy được.

## Hỏi được gì

| Bạn nhắn | Kỹ năng lo việc này | Giá ước tính cho một lần hỏi như câu mẫu |
|---|---|---|
| «Tôi định bán quạt cầm tay mini, xem có ai tìm và ai bán chưa» | Xem món định bán | khoảng 270–1.040 đ |
| «Đồ gia dụng nhỏ đang có món nào bán chạy trên TikTok Shop?» | Tìm hàng hot | khoảng 270–1.430 đ |
| «Thương hiệu này đang đăng gì trên TikTok, Facebook, và đang chạy quảng cáo gì trên Facebook, Google? [tên hoặc link kênh]» | Soi đối thủ | khoảng 100–820 đ |
| «Khách nói gì dưới video này? [link]» | Khách khen chê | khoảng 20–300 đ |
| «Tìm nguồn sỉ quạt cầm tay trên 1688» | Nguồn hàng 1688 | khoảng 770 đ. Xem chi tiết một mẫu 1688: thêm khoảng 770 đ. Tìm cả trên Taobao, Tmall: thêm khoảng 1.200 đ |
| Việc lẻ khác, ví dụ chép lời một video TikTok hoặc YouTube | Kỹ năng chung «hgtrend» tìm trong hơn 500 công cụ | giá ước tính từng công cụ ghi ở trang chủ hgtrend.com |

Một lần hỏi có thể chạy hơn một công cụ, nên số tiền thật có thể cao hơn dòng ghi ở bảng; xem điều 3 và 4 ở mục «6 điều phải biết» bên dưới.

**Chưa có:** số liệu riêng của Shopee, Lazada, Tiki, Sendo, Zalo · doanh thu hay số đơn của đối thủ · tìm hàng 1688, Taobao bằng ảnh · tính phí vận chuyển.
Kỹ năng dặn trợ lý nói thẳng là chưa có khi bạn hỏi tới các việc này.

## Cài trong app Claude (máy tính)

Làm một lần, không phải mở Terminal.

1. Mở **Settings → Customize → Plugins**.
2. Bấm **+ Add** ở góc phải, chọn **Add marketplace**, nhập `hgtrend/hgtrend`.
3. Tìm gói **Hgtrend** (by HG Studio) trong danh sách và cài.
4. Đóng Settings, mở một phiên trò chuyện, gõ `/mcp` vào ô nhắn rồi bấm Enter. Trong hộp «MCP servers», ở dòng **hgtrend — Provided by the Hgtrend plugin**, bấm **Connect**.
5. Trình duyệt mở trang của hgtrend.com: đăng nhập HG Studio bằng tài khoản Google, rồi bấm «Cho phép».
6. Tài khoản phải có token thì mới chạy được. Token là điểm trả trước, mỗi lần chạy công cụ trừ một ít; chưa có thì đọc «6 điều phải biết» bên dưới rồi mua ở
   `https://hgstudio.work/bang-gia`.
7. Quay lại app và nhắn việc.

## Cách khác: cài bằng Terminal (dành cho người dùng Claude Code dòng lệnh; đã cài trong app thì bỏ qua)

```
claude plugin marketplace add hgtrend/hgtrend
claude plugin install hgtrend@hgtrend
```

Mở Claude Code, gõ `/mcp`, chọn dòng `hgtrend` đang ghi «needs authentication», bấm Enter; trình duyệt mở trang của hgtrend.com để đăng nhập và bấm «Cho phép».
Gói cài ở đây cũng hiện sẵn trong app Claude trên cùng máy, nhưng app là một kết nối riêng: trong app vẫn phải gõ `/mcp` rồi bấm **Connect** ở dòng hgtrend.

Cập nhật bản mới: chạy `claude plugin marketplace update hgtrend` rồi `claude plugin update hgtrend@hgtrend`, sau đó mở lại Claude Code hoặc app Claude.
Gỡ gói: `claude plugin uninstall hgtrend@hgtrend`.

## Dùng Claude.ai trên web, ChatGPT, Cursor

Các trợ lý này nối thẳng tới địa chỉ `https://hgtrend.com/mcp`, không cài bộ này. Cách nối từng loại ghi ở trang «Cách dùng»: `https://hgtrend.com/cach-dung`.

**Phải biết trước khi dùng cách này:** trợ lý có công cụ nhưng KHÔNG có 6 kỹ năng, nên không có lời dặn nào ghi trong trang này: không hỏi trước khi vượt 2.000 đ,
không nói giá ở dòng đầu, không được dặn nói «chưa có», không được dặn nêu số món đã tính. Trợ lý tự chọn công cụ, số token tiêu có thể khác bảng ở trên.

## 6 điều phải biết trước khi mua token

1. **1 token = 10 đồng.** Tài khoản và token dùng chung với HG Studio; đăng nhập bằng Google ở `https://hgstudio.work`, mua gói ở `https://hgstudio.work/bang-gia`.
2. **Token có hạn dùng:** 30 hoặc 60 ngày, ghi ở từng gói.
3. **Giá ghi ở đây và ở trang chủ là giá ước tính**, đã gồm mọi khoản, không cộng thêm thuế hay phí. Số token trừ thật nằm trong kết quả công cụ trả về cho trợ lý
   và ở trang Tài khoản (`https://hgstudio.work/tai-khoan`). Lần chạy báo lỗi không bị trừ token.
4. **Ngưỡng 2.000 đ là lời dặn cho trợ lý, không phải khoá của máy chủ.** Kỹ năng dặn: tổng tiền một yêu cầu không quá 2.000 đ thì chạy luôn và nói ngay dòng
   đầu là đã chạy gì, tốn bao nhiêu; hơn 2.000 đ thì nêu tổng tiền và hỏi bạn trước. Trợ lý AI có thể làm khác lời dặn.
5. **Số liệu có giới hạn:** dữ liệu công khai lấy từ nền tảng nguồn lúc chạy; nền tảng nguồn chặn hoặc thay đổi thì công cụ có thể tạm không chạy được. Số món,
   số shop và giá là của trang kết quả đầu, không phải của cả sàn. Lời «nên» hay «chưa nên» của trợ lý là nhận định; quyết định nhập hàng là của bạn.
6. **Đọc trước khi trả tiền:** giá và thanh toán ở mục 3, hoàn tiền ở mục 4, điều kiện và giới hạn ở mục 13 của Điều khoản (`https://hgstudio.work/dieu-khoan`).
   Cách dùng đầy đủ, cách thu hồi quyền của trợ lý: `https://hgtrend.com/cach-dung`.

## Liên hệ

- Người bán và hỗ trợ: **HỘ KINH DOANH HG STUDIO** · Chủ hộ: Nguyễn Văn Hòa · Mã số hộ kinh doanh (MST) 066094000655, đăng ký lần đầu 26/10/2026 tại Phòng Kinh tế, Hạ tầng
  và Đô thị — UBND phường Thủ Đức · 95/1 Đường Võ Văn Ngân, Khu Phố 5, Phường Thủ Đức, Thành phố Hồ Chí Minh · Điện thoại 0963220365 · Email hotro@hgstudio.work

## Giấy phép

Phần chữ hướng dẫn trong bộ cài này phát hành theo giấy phép MIT (tệp `LICENSE`). Dịch vụ HG Trend dùng theo Điều khoản ở trên.

HG Trend is a data toolkit for sellers in Vietnam. This documentation is in Vietnamese. Terms of service: https://hgstudio.work/dieu-khoan
