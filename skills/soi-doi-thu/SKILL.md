---
name: soi-doi-thu
description: Xem một đối thủ (thương hiệu, shop, kênh) đang đăng gì trên TikTok, YouTube, Facebook, Instagram và đang chạy quảng cáo gì trên Facebook, Google — bằng báo cáo «Soi kênh, bài đăng, quảng cáo đối thủ» của HG Trend; hoặc xem các mẫu quảng cáo đang chạy của cả một ngành hàng. Dùng khi người dùng hỏi «đối thủ đang làm gì», «kênh này đăng gì, bao lâu một bài», «họ đang chạy quảng cáo gì», «spy ads», «ngành này đang chạy mẫu quảng cáo nào», kể cả khi họ hỏi doanh thu hay số đơn của đối thủ (HG Trend chưa có — kỹ năng nói rõ cách trả lời).
---
# Soi đối thủ: kênh, bài đăng, quảng cáo

Người dùng muốn biết đối thủ đang làm gì. Chạy báo cáo «Soi kênh, bài đăng, quảng cáo đối thủ» (`hgsoidt`) cho MỘT đối thủ, hoặc tìm mẫu quảng cáo theo ngành, rồi kể đúng thứ nhìn thấy được: đây là dữ liệu công khai về **bài đăng và mẫu quảng cáo**, không phải doanh thu, số đơn hay tiền quảng cáo của họ.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Nêu tên đối thủ, tên kênh (@…) hoặc link kênh / trang | Báo cáo `hgsoidt` |
| Quảng cáo của một NGÀNH theo từ khoá, không có đối thủ nào | Công cụ lẻ — mục «Quảng cáo theo ngành» (chỉ có Facebook / Instagram và TikTok; quảng cáo Google theo từ khoá ngành thì HG Trend chưa có) |
| Chỉ hỏi quảng cáo Google của một tên miền | Báo cáo `hgsoidt` với `ten_mien` cho biết lần này **có thấy mẫu không, bao nhiêu mẫu**. Muốn xem **từng mẫu** thì «Quảng cáo Google của đối thủ» (`hgcloe4t`, cuối mục «Quảng cáo theo ngành») — luôn báo giá và chờ đồng ý |
| Doanh thu, số đơn, tiền quảng cáo đã tiêu, mẫu nào «ra đơn», lượt xem của mẫu quảng cáo | HG Trend **chưa có**. Nói vậy; báo cáo chỉ cho biết họ đăng gì, mẫu nào đang chạy, từ bao giờ |
| Shop đối thủ trên Shopee, Lazada, Tiki, Sendo, Zalo | Chưa có; hỏi họ có muốn soi kênh mạng xã hội và quảng cáo của đối thủ đó không |
| Khách nói gì dưới bài của đối thủ | Báo cáo «Tóm tắt bình luận: khách khen, chê gì» (`hgbinhluan`), cần link bài |
| «Đối thủ của mình» mà không có tên hay link | Hỏi tên thương hiệu hoặc link kênh. Không đoán |
| Nhiều đối thủ | Mỗi đối thủ một lượt; cộng token |

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

`tu_tim_kenh` mặc định bật: HG dò thêm các kênh chưa được đưa theo tên thương hiệu, lượt chạy đắt hơn. Chọn theo điều họ hỏi:

- **Chỉ hỏi đúng kênh đã đưa link / tên (@…)**: điền ô của nền tảng đó, đặt `tu_tim_kenh` = false; **đừng điền thêm `thuong_hieu`, `ten_mien`** — điền là HG tra thêm quảng cáo, tốn thêm.
- **Chỉ hỏi quảng cáo**: quảng cáo Facebook thì chỉ điền `thuong_hieu`; quảng cáo Google thì chỉ điền `ten_mien`; hỏi cả hai mới điền cả hai. Đặt `tu_tim_kenh` = false.
- **Muốn biết đối thủ đang làm gì nói chung**: điền `thuong_hieu` (kèm kênh, tên miền nếu họ có), để `tu_tim_kenh` bật. Tên càng đầy đủ càng ít nhầm («Cocoon Vietnam», không phải «Cocoon»).
- Quảng cáo Facebook cần `thuong_hieu`; quảng cáo Google cần `ten_mien`. Thiếu ô nào thì phần đó không được tra — nói «chưa tra phần đó», đừng nói «họ không chạy quảng cáo».
- `xem_quang_cao_tiktok` chủ yếu ra quảng cáo ở châu Âu; chỉ bật khi người dùng nói rõ cần.

Giá: **~10–103 token mỗi lượt** — soi một kênh gần mức thấp, tự tìm đủ kênh và xem quảng cáo gần mức cao. Tính theo mức cao. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token; đừng tự đổi ra đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ trừ token theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

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
| `kenh` | Mỗi nền tảng một khối | `nguoi_theo_doi`, `tong_luot_thich`, `so_video` là của **cả kênh**. Nhịp đăng (`bai_moi_tuan`, `bai_moi_nhat_ngay`, `bai_trong_7_ngay_qua`), mức xem / thích / tương tác của bài đứng giữa (`luot_xem_o_giua`, `luot_thich_o_giua`, `tuong_tac_o_giua` — tức một bài bình thường của kênh), `gio_hay_dang`, `hashtag_hay_dung`, `bai_noi_bat`, `bai_gan_gio_hang` tính trên **`so_bai_xem` bài mới nhất** (khoảng 10 bài; Facebook có khi vài bài). Ngày đăng YouTube là ước. Nền tảng **không có trong `kenh`** hoặc có `khong_doc_duoc` = lần này không tìm thấy / không đọc được, không phải đối thủ không có kênh |
| `quang_cao` → Facebook | Mẫu **đang chạy ở Việt Nam** tìm theo tên: `tong_mau_khop_tu_khoa_o_VN`, `so_mau_da_xem`, `mau_cua_thuong_hieu_dang_chay`, `trang_cua_thuong_hieu`, `mau_chay_lau_nhat_tu`, `dang_quang_cao`, `nut_bam`, `hien_o`, `mau` (kèm `link_thu_vien`) | Ba con số nối nhau, nêu đủ: có `tong_mau_khop_tu_khoa_o_VN` mẫu khớp tên này ở Việt Nam (gồm cả trang khác nhắc tên) → HG chỉ xem `so_mau_da_xem` mẫu đầu → trong số đã xem, `mau_cua_thuong_hieu_dang_chay` mẫu là của các trang thuộc thương hiệu (phần còn lại của trang khác). Đừng nói đối thủ «chỉ chạy» chừng ấy mẫu, cũng đừng tính cả tổng là của họ. `trang_cua_thuong_hieu` có nhiều trang (cửa hàng, đại lý, trùng tên): kể đủ tên, và nói mọi con số ở khối này là **gộp của các trang ấy**, không tách được. `trang_khac_cung_chay_quang_cao_nhac_ten_nay` là trang khác nhắc tên thương hiệu. Mẫu chạy lâu chỉ cho biết nó còn được giữ chạy — không có tiền đã tiêu, lượt xem, đơn hàng |
| `quang_cao` → Google | Mẫu theo `ten_mien`: `so_mau_thay` | 0 = **lần này không thấy mẫu nào** cho tên miền đó; đừng kết luận «không chạy Google Ads» |
| `hg_nhan_xet` | Câu máy ghép sẵn | **Đừng chép**; tự viết lại |
| `phan_tam_thieu`, `ghi_chu` | Phần không lấy được; giới hạn dữ liệu | Nói lại cho người dùng |

## Quảng cáo theo ngành (không có tên đối thủ)

| Cần gì | Công cụ | Tham số chính |
|---|---|---|
| Mẫu Facebook / Instagram đang chạy theo từ khoá | «Quảng cáo đang chạy trên Facebook» (`hgycspqa`, ~10 token) | `query` = từ khoá ngành tiếng Việt; `country` = «VN»; `status` = «ACTIVE» (luôn kèm cả ba: thiếu `status` thì kết quả không có các trường ghi dưới đây) |
| Mẫu TikTok theo từ khoá | «Tìm quảng cáo TikTok theo từ khoá» (`hg76xztf`, ~10 token) | `query`. Thư viện này chủ yếu có quảng cáo ở châu Âu — ngành hàng Việt Nam thường ra ít mẫu, mẫu nhỏ |

Riêng **quảng cáo Google của MỘT tên miền** (không tìm theo từ khoá ngành được): «Quảng cáo Google của đối thủ» (`hgcloe4t`, ~10 token hoặc ~130 token/kết quả), tham số `domain`, `region` = «VN». Giá có phần tính **theo số kết quả**: luôn báo giá và chờ đồng ý. Người dùng muốn soi cả kênh lẫn quảng cáo của đối thủ đó thì dùng báo cáo `hgsoidt` ở trên.

Công cụ lẻ trả **dữ liệu thô** tiếng Anh. Với `hgycspqa`: mỗi mục trong `searchResults` là một mẫu — đọc `page_name`, `is_active`, `display_format`, `cta_text` và chữ quảng cáo. Kết quả thường bị cắt (trường `rut_gon` ghi giữ bao nhiêu trên tổng số): nói mới xem được chừng ấy mẫu. Tìm theo từ khoá ra rất nhiều mẫu không liên quan: **đọc chữ từng mẫu**, chỉ kể mẫu đúng ngành, nói đã bỏ bao nhiêu mẫu lạc đề. Với `hg76xztf`: các mẫu nằm trong `ads`, `total` là tổng số mẫu khớp — nói đã xem bao nhiêu trên tổng. `estimated_audience` (dạng «0-1K») là khung ước lượng của thư viện, chủ yếu ở châu Âu: **không phải lượt xem, không phải số người thấy quảng cáo ở Việt Nam**. Bỏ qua các trường về tài khoản của nguồn.

## Trả lời người dùng

Người dùng bỏ tiền theo câu trả lời này. **Phần sự thật** — soát trước khi gửi:

- **Số và tên chép đúng.** Rút gọn tên không được làm đổi mặt hàng hay cách bán (giữ «combo», «mua 2 tặng 1»). Tên shop, tên kênh không phải tên loại hàng.
- **Không thêm lý do, không thêm tính chất.** Không viết «vì…», «cho thấy…» như dữ kiện; không gắn «chính hãng», «loại cơ bản», «trôi nổi»… khi kết quả không ghi.
- **Nói cỡ mẫu.** Nêu đúng số mục có trong kết quả; không nói thay cả sàn, cả thị trường. Số gộp HG tính sẵn (khi có) tính cả mục không hiện tên và mục lạc loại.
- **Bỏ mục lạc loại** khỏi phần liệt kê và phần nhận định; nói đã bỏ gì.
- **«Tất cả», «đều», «không món nào»** chỉ viết khi đã soát từng mục trong danh sách; sót một mục là câu sai.
- **Nhận định ghi rõ là của bạn** («theo tôi», «tôi nghiêng về»), và phải chỉ ra được mục hay con số đỡ cho nó — đếm lại trước khi viết, không đếm được thì bỏ.
- **Giữ đơn vị gốc:** không tự đổi ¥ ra đồng, không ước doanh thu từ lượt bán, không đổi điểm 0–100 thành số người.
- **Được khuyên, không quyết thay.** Người dùng hỏi «nên hay không», «chọn cái nào» thì nói bạn nghiêng về phía nào, vì con số nào, và điều gì có thể làm đổi ý. Lời khuyên chỉ dựa trên phần dữ liệu thấy được — chưa tính những thứ dữ liệu không có (giá nhập, phí sàn, chi phí quảng cáo, vốn của họ…): nói điều này một lần. Dữ liệu thưa, thiếu phần chính hoặc trái chiều nhau: nói thẳng «chưa đủ dữ liệu để khuyên» và cần xem thêm gì. Không viết «chắc chắn», «đảm bảo», «sẽ bán được».

**Phần cách viết** — người đọc là chủ shop đang bận, đọc trên điện thoại:

- **Dòng đầu nói giá lượt chạy** (như mục «Trước khi chạy»), **ngay sau đó là câu mở trả lời thẳng điều họ hỏi**, kèm một hai con số chính. Họ hỏi «nên hay không» thì câu mở nói luôn bạn nghiêng về phía nào, mở bằng «Theo tôi».
- **Mỗi con số, mỗi ý chỉ nêu một lần.** Số đã nêu ở câu mở thì bên dưới không nêu lại; phần số liệu chỉ thêm số chưa nêu. Chỉ đưa số giúp họ quyết; bảng chỉ dùng khi xếp từ 3 mục cạnh nhau. Câu trả lời cho một lượt chạy thường gọn trong 300–450 chữ — dài hơn là đang lặp.
- **Lời thường, không dùng chữ của máy.** Không viết tên trường. Số bán nói kèm kỳ đúng như bảng trên ghi («đã bán 12.000 cái từ trước tới nay», «trong tháng», hoặc «không ghi của kỳ nào») thay cho «cộng dồn»; «giá niêm yết (giá gạch ngang)» thay cho «giá gốc» (dễ nhầm với giá nhập); «người ta hay tìm kèm: …» thay cho «cụm gõ kèm»; «tôi mới xem được 4 trong 30 mẫu» thay cho «kết quả bị cắt». Điểm Google nói bằng so sánh trước, điểm để trong ngoặc, và **gọi đúng tên là «mức quan tâm trên Google»** — không gọi là «lượt tìm», «số người tìm»: «mức quan tâm trên Google 4 tuần gần đây chỉ bằng khoảng một phần tư mức trung bình cả năm (điểm 6 so với 22, thang 100)». Chữ và nhãn tiếng nước ngoài thì dịch.
- **Lưu ý về giới hạn dữ liệu gom vào MỘT dòng cuối** («Lưu ý khi đọc số: …»): mỗi ý một lần, chỉ ý dính tới con số bạn đã dùng. Riêng lưu ý làm đổi nghĩa con số ngay tại chỗ thì viết liền con số bằng vài chữ («109.000 đ, niêm yết 199.000 đ»; «12 ¥ một cái, chưa gồm phí về Việt Nam») và không nhắc lại ở cuối.
- **Kết bằng MỘT việc nên làm tiếp**, một câu; cần chạy thêm thì nêu giá và chờ họ đồng ý.
- **Con số «đứng giữa»** (HG xếp từ thấp tới cao rồi lấy mục giữa — bảng trên ghi ô nào): viết «một nửa số món bán từ … trở xuống», «một bài bình thường được khoảng … lượt xem». Không viết «ở giữa», «trung vị»; **không gọi là «trung bình»** — đây chưa phải trung bình cộng.

Bố cục:

1. **Câu mở** — đối thủ (hoặc ngành) đang làm gì nổi bật nhất: dồn vào kênh nào, đăng đều tới đâu; và quảng cáo: **đang chạy** (viết liền con số: «20 mẫu trong 25 mẫu đã xem, gộp của 7 trang mang tên này») · **lần này không thấy mẫu nào** · **phần này chưa tra**. Kênh do HG tự tìm mà chưa được xác nhận thì câu mở nói «nếu đúng đây là kênh của họ».
2. **Đã soi những kênh nào** — tên + link; kênh HG tự tìm thì nhờ xác nhận đúng đối thủ; nền tảng nào không tìm thấy / không đọc được.
3. **Họ đăng gì** — từng nền tảng: nhịp đăng, bài mới nhất, một bài bình thường được bao nhiêu lượt xem / tương tác, 2–3 bài nổi bật kèm link, giờ hay đăng.
4. **Họ chạy quảng cáo gì** — số mẫu (ba mốc như bảng trên, của những trang nào), dạng, nút bấm, mẫu chạy lâu nhất, 2–3 mẫu kèm chữ và link. Phần chưa tra / không thấy thì nói đúng vậy.
5. **Việc nên làm trước** — theo bạn, MỘT việc người dùng nên làm sau khi đọc (kèm con số đỡ cho nó); thêm tối đa hai điều đáng cân nhắc. Dữ liệu chỉ cho biết họ ĐANG LÀM gì, không biết cái gì ra đơn hay có lãi: việc bạn khuyên chỉ nên là **tìm hiểu thêm hoặc thử nhỏ** (xem kỹ mẫu chạy lâu nhất, đọc bình luận bài nổi bật, thử một dạng bài họ đăng đều) — đừng khuyên «làm theo», «chạy mẫu này», «dồn vào kênh này» như thể nó đã hiệu quả.
6. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Thường là: các số về bài đăng tính trên bao nhiêu bài mới nhất · quảng cáo mới xem bao nhiêu mẫu đầu · nhịp đăng và số mẫu cho biết họ ĐANG LÀM gì, không cho biết cái gì ra đơn — không có doanh thu, tiền quảng cáo, lượt xem của mẫu quảng cáo.
7. **Việc nên làm tiếp** — một câu.
