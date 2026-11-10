---
name: soi-doi-thu
description: Xem một đối thủ (thương hiệu, shop, kênh) đang đăng gì trên TikTok, YouTube, Facebook, Instagram và đang chạy quảng cáo gì trên Facebook, Google — bằng báo cáo «Soi kênh, bài đăng, quảng cáo đối thủ» của HG Trend; hoặc xem các mẫu quảng cáo đang chạy của cả một ngành hàng. Dùng khi người dùng hỏi «đối thủ đang làm gì», «kênh này đăng gì, bao lâu một bài», «họ đang chạy quảng cáo gì», «spy ads», «ngành này đang chạy mẫu quảng cáo nào», kể cả khi họ hỏi doanh thu hay số đơn của đối thủ (HG Trend chưa có — kỹ năng nói rõ cách trả lời).
---
# Soi đối thủ: kênh, bài đăng, quảng cáo

Người dùng muốn biết đối thủ đang làm gì. Chạy báo cáo «Soi kênh, bài đăng, quảng cáo đối thủ» (`hgsoidt`) cho MỘT đối thủ, hoặc tìm mẫu quảng cáo theo ngành, rồi kể đúng thứ nhìn thấy được: đây là dữ liệu công khai về **bài đăng và mẫu quảng cáo**, không phải doanh thu, số đơn hay tiền quảng cáo của họ.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 đồng) · `xem_cong_cu` (tham số và giá, 0 đồng) · `chay_cong_cu` (chạy thật, tính tiền). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Nêu tên đối thủ, tên kênh (@…) hoặc link kênh / trang | Báo cáo `hgsoidt` |
| Quảng cáo của một NGÀNH, không có đối thủ nào | Công cụ lẻ — mục «Quảng cáo theo ngành» |
| Doanh thu, số đơn, tiền quảng cáo đã tiêu, mẫu nào «ra đơn», lượt xem của mẫu quảng cáo | HG Trend **chưa có**. Nói vậy; báo cáo chỉ cho biết họ đăng gì, mẫu nào đang chạy, từ bao giờ |
| Shop đối thủ trên Shopee, Lazada, Tiki, Sendo, Zalo | Chưa có; hỏi họ có muốn soi kênh mạng xã hội và quảng cáo của đối thủ đó không |
| Khách nói gì dưới bài của đối thủ | Báo cáo «Tóm tắt bình luận: khách khen, chê gì» (`hgbinhluan`), cần link bài |
| «Đối thủ của mình» mà không có tên hay link | Hỏi tên thương hiệu hoặc link kênh. Không đoán |
| Nhiều đối thủ | Mỗi đối thủ một lượt; cộng tiền |

## Trước khi chạy

| Tham số | Bắt buộc | Ý nghĩa |
|---|---|---|
| `thuong_hieu` | không | Tên đối thủ / thương hiệu, vd Cocoon Vietnam (cần cho quảng cáo Facebook và tự tìm kênh). Không có thì phải đưa ít nhất một kênh |
| `tiktok` | không | Tên kênh TikTok (@ten) hoặc link kênh |
| `youtube` | không | Link kênh YouTube (youtube.com/@ten hoặc /channel/UC…) |
| `facebook` | không | Link trang Facebook |
| `instagram` | không | Tên kênh Instagram hoặc link |
| `ten_mien` | không | Tên miền web đối thủ để xem quảng cáo Google, vd cocoonvietnam.com |
| `tu_tim_kenh` | không | Kênh nào không đưa thì HG tự tìm theo tên thương hiệu (mặc định true) |
| `xem_quang_cao_tiktok` | không | Xem thêm thư viện quảng cáo TikTok (chủ yếu quảng cáo hiển thị ở châu Âu) (mặc định false) |
| `so_bai` | không | Số bài nổi bật / mẫu quảng cáo liệt kê (mặc định 5) (từ 3 đến 10) |

- Đã có **link hoặc tên kênh (@…)**: điền đúng ô của nền tảng đó và **đặt `tu_tim_kenh` = false** (mặc định bật: HG dò thêm kênh khác, lượt chạy đắt hơn).
- **Chỉ có tên thương hiệu**: điền `thuong_hieu`, để `tu_tim_kenh` bật (kể cả khi họ chỉ hỏi một nền tảng). Tên càng đầy đủ càng ít nhầm («Cocoon Vietnam», không phải «Cocoon»).
- Quảng cáo Facebook cần `thuong_hieu`; quảng cáo Google cần `ten_mien`. Thiếu ô nào thì phần đó không được tra — nói «chưa tra phần đó», đừng nói «họ không chạy quảng cáo».
- `xem_quang_cao_tiktok` chủ yếu ra quảng cáo ở châu Âu; chỉ bật khi người dùng nói rõ cần.

Giá: **~100–820 đ mỗi lượt** — soi một kênh gần mức thấp, tự tìm đủ kênh và xem quảng cáo gần mức cao. Báo theo mức cao. **Rẻ thì báo rồi chạy luôn:** cộng tiền mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 2.000 đ: báo (chạy gì, bao nhiêu tiền) rồi gọi `chay_cong_cu` ngay trong cùng câu trả lời. Trên 2.000 đ: nêu số lượt, tổng tiền và **chờ đồng ý**.

Câu báo trước khi chạy gồm ba ý: chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **giá**.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ tính tiền theo số kết quả hay có mức cao vượt ngưỡng. Thứ họ hỏi mà dữ liệu không trả lời được thì nói ngay trong câu báo.

## Chạy

```
chay_cong_cu(ma="hgsoidt", tham_so={"thuong_hieu": "Cocoon Vietnam", "ten_mien": "cocoonvietnam.com"})
chay_cong_cu(ma="hgsoidt", tham_so={"tiktok": "@tenkenh", "tu_tim_kenh": false})
```

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

| Trường | Là gì | Lưu ý |
|---|---|---|
| `luc` | Giờ lấy dữ liệu | Luôn ghi lại |
| `kenh_hg_tu_tim` | Kênh HG **tự tìm** theo tên, kèm tìm từ đâu (`tim_tu`) | **Việc đầu tiên: nêu tên + link từng kênh đã soi và nhờ người dùng xác nhận đúng đối thủ.** Trang Facebook tự chọn mà không đọc được, hoặc ít người thích (`nguoi_thich_trang`) so với tầm thương hiệu, thì nhiều khả năng không phải trang chính: kể các tên trong `trang_cua_thuong_hieu`, nhờ họ đưa link trang chính thức |
| `kenh` | Mỗi nền tảng một khối | `nguoi_theo_doi`, `tong_luot_thich`, `so_video` là của **cả kênh**. Nhịp đăng (`bai_moi_tuan`, `bai_moi_nhat_ngay`, `bai_trong_7_ngay_qua`), mức xem / thích ở giữa, `tuong_tac_o_giua`, `gio_hay_dang`, `hashtag_hay_dung`, `bai_noi_bat`, `bai_gan_gio_hang` tính trên **`so_bai_xem` bài mới nhất** (khoảng 10 bài; Facebook có khi vài bài). Ngày đăng YouTube là ước. Nền tảng **không có trong `kenh`** hoặc có `khong_doc_duoc` = lần này không tìm thấy / không đọc được, không phải đối thủ không có kênh |
| `quang_cao` → Facebook | Mẫu **đang chạy ở Việt Nam** tìm theo tên: `tong_mau_khop_tu_khoa_o_VN`, `so_mau_da_xem`, `mau_cua_thuong_hieu_dang_chay`, `trang_cua_thuong_hieu`, `mau_chay_lau_nhat_tu`, `dang_quang_cao`, `nut_bam`, `hien_o`, `mau` (kèm `link_thu_vien`) | Chỉ xem **`so_mau_da_xem` mẫu đầu** trong tổng số — nêu cả hai. `trang_cua_thuong_hieu` có nhiều trang (cửa hàng, đại lý, trùng tên): kể đủ tên, và nói mọi con số ở khối này là **gộp của các trang ấy**, không tách được. `trang_khac_cung_chay_quang_cao_nhac_ten_nay` là trang khác nhắc tên thương hiệu. Mẫu chạy lâu chỉ cho biết nó còn được giữ chạy — không có tiền đã tiêu, lượt xem, đơn hàng |
| `quang_cao` → Google | Mẫu theo `ten_mien`: `so_mau_thay` | 0 = **lần này không thấy mẫu nào** cho tên miền đó; đừng kết luận «không chạy Google Ads» |
| `hg_nhan_xet` | Câu máy ghép sẵn | **Đừng chép**; tự viết lại |
| `phan_tam_thieu`, `ghi_chu` | Phần không lấy được; giới hạn dữ liệu | Nói lại cho người dùng |

## Quảng cáo theo ngành (không có tên đối thủ)

| Cần gì | Công cụ | Tham số chính |
|---|---|---|
| Mẫu Facebook / Instagram đang chạy theo từ khoá | «Quảng cáo đang chạy trên Facebook» (`hgycspqa`, ~100 đ) | `query` = từ khoá ngành tiếng Việt; `country` = «VN» |
| Mẫu TikTok theo từ khoá | «Tìm quảng cáo TikTok theo từ khoá» (`hg76xztf`, ~100 đ) | `query`. Thư viện này chủ yếu có quảng cáo ở châu Âu — ngành hàng Việt Nam thường ra ít mẫu, mẫu nhỏ |
| Quảng cáo Google của một tên miền | «Quảng cáo Google của đối thủ» (`hgcloe4t`, ~30–100 đ hoặc ~1.300 đ/kết quả) | `domain`, `region` = «VN»; không tìm theo từ khoá ngành được. Giá có phần tính **theo số kết quả**: luôn báo giá và chờ đồng ý |

Công cụ lẻ trả **dữ liệu thô** tiếng Anh. Với `hgycspqa`: mỗi mục trong `searchResults` là một mẫu — đọc `page_name`, `is_active`, `display_format`, `cta_text` và chữ quảng cáo. Kết quả thường bị cắt (trường `rut_gon` ghi giữ bao nhiêu trên tổng số): nói mới xem được chừng ấy mẫu. Tìm theo từ khoá ra rất nhiều mẫu không liên quan: **đọc chữ từng mẫu**, chỉ kể mẫu đúng ngành, nói đã bỏ bao nhiêu mẫu lạc đề. Bỏ qua các trường về tài khoản của nguồn.

## Trả lời người dùng

Người dùng bỏ tiền theo câu trả lời này. Trước khi gửi, soát:

- **Số và tên chép đúng.** Rút gọn tên không được làm đổi mặt hàng hay cách bán (giữ «combo», «mua 2 tặng 1»). Tên shop, tên kênh không phải tên loại hàng.
- **Không thêm lý do, không thêm tính chất.** Không viết «vì…», «cho thấy…» như dữ kiện; không gắn «chính hãng», «loại cơ bản», «trôi nổi»… khi kết quả không ghi.
- **Nói cỡ mẫu.** Nêu đúng số mục có trong kết quả; không nói thay cả sàn, cả thị trường. Số gộp tính cả mục không hiện tên và mục lạc loại.
- **Bỏ mục lạc loại** khỏi phần liệt kê và phần nhận định; nói đã bỏ gì.
- **Nhận định để riêng**, ghi rõ là của bạn, và phải chỉ ra được mục hay con số đỡ cho nó — đếm lại trước khi viết, không đếm được thì bỏ.
- **Giữ đơn vị gốc:** không tự đổi ¥ ra đồng, không ước doanh thu từ lượt bán, không đổi điểm tương đối thành số người.
- **Không quyết thay:** nêu điều đáng cân nhắc, không phán «nên» hay «không nên».

Thứ tự:

1. **Đã soi những kênh nào** — tên + link; kênh HG tự tìm thì nhờ xác nhận; nền tảng nào không tìm thấy / không đọc được.
2. **Họ đăng gì** — từng nền tảng: nhịp đăng, bài mới nhất, mức xem / tương tác ở giữa, 2–3 bài nổi bật kèm link, giờ hay đăng. **Luôn kèm:** tính trên bao nhiêu bài mới nhất.
3. **Họ chạy quảng cáo gì** — số mẫu đang chạy (trong bao nhiêu mẫu đã xem, của những trang nào), dạng, nút bấm, mẫu chạy lâu nhất, 2–3 mẫu kèm chữ và link. Phần chưa tra / không thấy thì nói đúng vậy.
4. **Điều đáng cân nhắc** — 2–3 ý, ghi rõ là nhận định. Nhịp đăng và số mẫu cho biết họ ĐANG LÀM gì, không cho biết cái gì hiệu quả.
5. Kết bằng một hai dòng: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi như bảng «Đọc kết quả» ghi · phần nào lần này không lấy được.
