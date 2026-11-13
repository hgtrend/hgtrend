---
name: tim-kol-koc
description: Tìm KOL, KOC trên TikTok ở Việt Nam cho một ngành hàng hay một sản phẩm, rồi soát từng kênh trước khi liên hệ — ai đang làm video về mặt hàng đó, bao nhiêu người theo dõi, một video bình thường được bao nhiêu lượt xem, tương tác ra sao, đăng đều không (xem người theo dõi ở nước nào là công cụ riêng, giá cao) — bằng công cụ «Tìm video trên TikTok theo từ khoá» và báo cáo «Soi kênh, bài đăng, quảng cáo đối thủ» của HG Trend. Dùng khi người dùng (agency, nhãn hàng, chủ shop) hỏi «tìm KOC review [sản phẩm]», «tìm KOL ngành [ngành] cho chiến dịch», «booking KOL nào hợp», «lên danh sách KOC», «kênh này có đáng book không», «soát kênh @… giúp tôi», kể cả khi họ hỏi giá booking, doanh số bán của KOC hay follow ảo (HG Trend chưa có — kỹ năng nói rõ cách trả lời).
---
# Tìm KOL, KOC cho chiến dịch (TikTok Việt Nam)

Người dùng cần danh sách người làm nội dung để mời hợp tác, hoặc muốn soát một kênh trước khi liên hệ. Làm hai chặng: **tìm ứng viên** qua các video đang có về mặt hàng đó, rồi **soát từng kênh** họ chọn. Mọi số là dữ liệu công khai lúc chạy; HG Trend **không có** giá booking, doanh số bán qua KOC, hay phép đo người theo dõi ảo.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Tìm KOL / KOC cho một sản phẩm, một ngành | Chặng 1: «Tìm video trên TikTok theo từ khoá» (`hgqekxpa`) |
| Đã có tên kênh (@…) hoặc link, hỏi «kênh này có đáng book không» | Chặng 2: báo cáo «Soi kênh, bài đăng, quảng cáo đối thủ» (`hgsoidt`) cho kênh đó |
| Chỉ nhớ tên hiển thị, chưa có @ | «Tìm tài khoản TikTok theo từ khoá» (`hgir277x`, ~10 token) để tìm @ — xem mục «Tìm @ theo tên». Tìm xong **dừng lại hỏi**, không tự chạy tiếp chặng 2 |
| Người theo dõi của kênh ở nước nào | «Follower kênh TikTok theo quốc gia» (`hgl7wtot`, ~250 token) — **đắt, luôn nêu giá và chờ đồng ý** |
| **Chỉ** hỏi giá booking, doanh số KOC bán được, tỉ lệ chuyển đổi, follow ảo bao nhiêu phần trăm | **Không chạy.** Nói HG Trend chưa có các số này; hỏi họ có muốn xem lượt xem, tương tác, nhịp đăng của kênh không |
| Giỏ hàng TikTok Shop của một KOC Việt Nam | **Chưa có cho Việt Nam** (nguồn của «Giỏ hàng trên kênh KOC TikTok Shop» hiện chỉ lấy được ở Mỹ; lượt thử với kênh Việt Nam trả lỗi). Không chạy `hgub72zt` cho kênh Việt Nam |
| Khách bình luận gì dưới video của KOC | Báo cáo «Tóm tắt bình luận: khách khen, chê gì» (`hgbinhluan`, ~2–30 token), cần link video |
| KOL trên Instagram, YouTube, Facebook | Kỹ năng này mới thử cho TikTok. Nói vậy; muốn thì `tim_cong_cu` với tên nền tảng |
| KOL Trung Quốc (Douyin, Tiểu Hồng Thư) | Kho có nhóm công cụ riêng, giá cao (từ khoảng 120 token mỗi lượt). Ngoài kỹ năng này: `tim_cong_cu`, nêu giá, chờ đồng ý |
| Trên Shopee, Lazada, Tiki, Sendo, Zalo | HG Trend chưa có |
| Không nói sản phẩm hay ngành nào | Hỏi lại. Không đoán |

## Trước khi chạy

Chặng 1 một lượt: ~10 token. Chặng 2 mỗi kênh một lượt báo cáo `hgsoidt`: ~10–82 token — soi một kênh đã có @ thì gần mức thấp (lượt thử: 20 token), nhưng khi cộng trước vẫn tính theo mức cao. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token; đừng tự đổi ra đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ trừ token theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

Thứ tự hỏi – chạy:

- Người dùng mới chỉ nêu sản phẩm / ngành: chạy **chặng 1** luôn. Trả danh sách ứng viên, rồi **hỏi họ muốn soát những kênh nào**, kèm số lượt và tổng token — chặng 2 là lượt chạy thêm, phải chờ đồng ý.
- Người dùng đưa sẵn một kênh: chạy chặng 2 cho kênh đó luôn.
- Người dùng đưa sẵn nhiều kênh: cộng token theo mức cao; quá ngưỡng thì nêu giá và chờ đồng ý.

## Chặng 1 — tìm ứng viên qua video

```
chay_cong_cu(ma="hgqekxpa", tham_so={"query": "review kem chống nắng", "region": "VN", "trim": true}, cat_ky_tu=45000)
```

- `query`: chữ người mua hay gõ, tiếng Việt có dấu: «review» + tên mặt hàng, hoặc tên mặt hàng + «có tốt không». Ngành rộng («làm đẹp») ra lẫn lộn: hỏi họ một mặt hàng cụ thể, hoặc chọn một mặt hàng tiêu biểu và nói rõ đã chọn.
- `region` = «VN» chỉ là nơi đặt máy tìm, **không lọc** video theo nước: phải tự đọc `region` của từng video.
- Đừng điền `sort_by`, `date_posted`: nguồn không bảo đảm xếp và lọc đúng. Cần video mới thì tự lọc theo `create_time_utc`.
- Giữ `trim` = true và `cat_ky_tu` = 45000 (cao hơn thì kết quả dài quá, nhiều trợ lý không đọc được). Số video đã xem là số mục thật có trong kết quả.
- **Xem thêm** (lượt thêm, hỏi trước): cùng lệnh, thêm `cursor` từ kết quả trước.
- `rut_gon` của công cụ này luôn có vài dòng về việc lược link, lược trường phụ — đó không phải cắt video. Chỉ khi có dòng «giữ … / … mục» thì danh sách video mới bị cắt bớt.

Mỗi mục trong `search_item_list` là một video:

| Trường | Là gì | Lưu ý |
|---|---|---|
| `url` | Link video; phần nằm giữa «@» và «/video/» trong link là tên kênh | Tên kênh (@…) lấy từ đây |
| `author` → `nickname`, `follower_count` | Tên hiển thị và số người theo dõi của kênh | `nickname` có khi trống |
| `statistics` → `play_count`, `digg_count`, `comment_count`, `share_count` | Lượt xem, lượt thích, bình luận, chia sẻ của **video này** | Một video nổ không nói lên kênh: lượt xem của một video bình thường phải soát ở chặng 2 |
| `desc` | Chữ mô tả video | Đọc để bỏ video lạc đề (không nói về mặt hàng đang hỏi) |
| `region` | Nước của video | Chỉ giữ video «VN» khi tìm KOC Việt Nam; nói đã bỏ mấy video nước khác |
| `create_time_utc` | Ngày đăng | Video quá cũ (trên một năm) thì ghi rõ |
| `is_ad` | TikTok gắn nhãn có yếu tố quảng cáo | Chỉ là nhãn của nền tảng: **không biết** nhãn hàng nào trả tiền, có phải bài được thuê hay không. Đừng viết «kênh này nhận quảng cáo của…» |

Gom theo kênh: một kênh có thể có vài video trong kết quả — lấy video nhiều lượt xem nhất làm đại diện và ghi kênh có mấy video khớp. Đây là **những kênh có video khớp từ khoá trong số video lượt tìm đó trả về** (nêu đúng số video đã xem), không phải danh sách đầy đủ KOC của ngành, không phải bảng xếp hạng.

## Chặng 2 — soát từng kênh

```
chay_cong_cu(ma="hgsoidt", tham_so={"tiktok": "@tenkenh", "tu_tim_kenh": false})
```

Chỉ điền `tiktok` và `tu_tim_kenh` = false; **đừng điền** `thuong_hieu`, `ten_mien` (điền là báo cáo tra thêm quảng cáo, tốn thêm).

| Trường (trong `kenh`, khối `tiktok`) | Là gì | Lưu ý |
|---|---|---|
| `nguoi_theo_doi`, `tong_luot_thich`, `so_video` | Số của cả kênh | |
| `luot_xem_o_giua` | Lượt xem của một bài bình thường — bài đứng giữa trong `so_bai_xem` bài đầu trang kênh (khoảng 10 bài, có thể gồm bài ảnh) | Mốc tham khảo tốt nhất về sức hút thường ngày của kênh; **không phải dự báo** lượt xem của bài hợp tác. HG xếp lượt xem các bài đã xem từ thấp tới cao rồi lấy bài đứng giữa: viết «một bài bình thường được khoảng … lượt xem», không viết «trung bình», «trung vị». Bài ghim cũ nhiều lượt xem cũng nằm trong 10 bài này (xem ngày đăng ở `bai_noi_bat`): thấy có bài ghim cũ thì nói con số có thể cao hơn mức của các bài mới đăng |
| `tuong_tac_o_giua` | Tỉ lệ tương tác của bài đứng giữa | Tính trên khoảng 10 bài mới nhất |
| `bai_trong_7_ngay_qua`, `bai_moi_nhat_ngay` | Nhịp đăng gần đây | **Dùng hai số này.** `bai_moi_tuan` có thể thấp sai khi kênh ghim bài cũ (ở lượt thử: 7 bài trong 7 ngày qua nhưng trường này ghi 0,1) — thấy lệch thì bỏ `bai_moi_tuan`, và đừng chép câu «… bài/tuần» trong `hg_nhan_xet` |
| `bai_noi_bat` | Vài bài nhiều lượt xem nhất trong số đã xem | Có thể gồm bài ghim rất cũ: nêu ngày đăng. Bài có thể là video hoặc bài ảnh (`loai_bai`): gọi chung là «bài» |
| `luc` | Giờ lấy dữ liệu | Ghi ở dòng lưu ý cuối |
| `bai_gan_gio_hang` | Bao nhiêu bài trong số đã xem có gắn giỏ hàng | «0/10» = không thấy trong 10 bài đã xem, không phải «kênh không bán hàng» |
| `hashtag_hay_dung` | Hashtag kênh hay dùng | Gợi ý kênh hay làm về gì, nhãn hàng nào |
| `gioi_thieu` | Phần giới thiệu kênh | Thư, số điện thoại liên hệ công việc **chỉ nêu khi chính kênh ghi ở đây**, chép đúng. Không tìm liên hệ ở nơi khác |
| `khong_doc_duoc` | Lần này không đọc được kênh | Nói «lần này không đọc được», không nói kênh không tồn tại |

**Người theo dõi ở nước nào** (`hgl7wtot`, tham số `handle` = tên kênh không có «@»): trả danh sách nước kèm `count` và `percentage`. Số này tính trên **một mẫu nhỏ người theo dõi**; kết quả không ghi cỡ mẫu — **tự cộng `count` của mọi nước** để ra cỡ mẫu của lượt đó (ở lượt thử: 163 người của một kênh hơn 100 nghìn người theo dõi). Viết «trong mẫu 163 người theo dõi, 94 % ở Việt Nam», không viết «94 % người theo dõi ở Việt Nam». Không cho biết tuổi, giới tính, tài khoản ảo.

**Kênh thuộc nước nào** (`hg3upwg7`, ~10 token, tham số `handle` = tên kênh không có «@»): chỉ cần khi chưa có video nào của kênh để đọc `region`.

**Tìm @ theo tên** (`hgir277x`): `chay_cong_cu(ma="hgir277x", tham_so={"query": "<tên hiển thị>", "trim": true})`. Kết quả là danh sách `users`, mỗi tài khoản chỉ có `nickname` (tên hiển thị), `unique_id` (tên kênh, chưa có «@») và `follower_count` — không có giới thiệu, không có nước. Công cụ tìm theo **tên tài khoản**, thường ra nhiều tài khoản trùng hoặc gần giống tên: liệt kê các tài khoản khớp kèm số người theo dõi, **hỏi người dùng đâu là kênh họ cần**, nêu giá chặng 2, rồi mới soát.

`credits_charged`, `credits_remaining` trong kết quả công cụ lẻ là số của nguồn dữ liệu, **không phải token của người dùng**: đừng đọc thành giá, đừng nhắc tới.

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

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

**Sau chặng 1** (danh sách ứng viên):

1. **Dòng đầu** như mục «Trước khi chạy»: đã tìm cụm nào · dữ liệu là video công khai trên TikTok, lấy lúc chạy · tốn bao nhiêu token.
2. **Câu mở** — tìm được bao nhiêu kênh Việt Nam có video về mặt hàng này trong bao nhiêu video đã xem; đã bỏ bao nhiêu video lạc đề hay nước khác.
3. **Bảng ứng viên** — tối đa 10 kênh, xếp theo số người theo dõi từ cao xuống: kênh (@ và link video) · người theo dõi · video khớp nói gì (tóm ý) và được bao nhiêu lượt xem · ngày đăng. Người dùng có nêu cỡ kênh mong muốn (ví dụ dưới 100 nghìn người theo dõi) thì lọc theo đó và nói đã lọc. Chưa nêu mà có trên 10 kênh: lấy đều ba cỡ (trên 500 nghìn · từ 50 đến 500 nghìn · dưới 50 nghìn người theo dõi) để không chỉ toàn kênh lớn, và nói còn bao nhiêu kênh chưa kể.
4. **Dòng lưu ý cuối** — **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Thường là: đây là kênh có video khớp trong một lượt tìm, chưa phải danh sách đầy đủ · lượt xem ở bảng là của một video, chưa phải mức thường của kênh · không có giá booking, doanh số, người theo dõi ảo.
5. **Việc nên làm tiếp** — hỏi họ muốn soát những kênh nào: nêu số lượt, giá mỗi lượt, tổng token, chờ đồng ý. Đừng tự soát.

**Sau chặng 2** (soát kênh):

1. **Dòng đầu**: đã soát kênh nào · số tính trên bao nhiêu bài mới nhất · tốn bao nhiêu token.
2. **Câu mở** — trả lời thẳng điều họ hỏi. Hỏi «có đáng book không» thì nói bạn nghiêng về phía nào, mở bằng «Theo tôi», kèm con số chính (một bài bình thường được khoảng bao nhiêu lượt xem, so với số người theo dõi).
3. **Số của kênh** — từ 3 kênh thì dùng bảng: người theo dõi · một bài bình thường được bao nhiêu lượt xem · tương tác · số bài 7 ngày qua · bài gắn giỏ hàng. Một hai kênh thì viết thành vài dòng, chỉ thêm số chưa nêu ở câu mở.
4. **Điều đáng để ý** — kênh hay làm về gì (theo hashtag và bài nổi bật), có hợp mặt hàng không; liên hệ nếu kênh có ghi.
5. **Dòng lưu ý cuối**: lấy lúc nào · số tính trên khoảng 10 bài mới nhất (gồm cả bài ghim nếu có) · lời khuyên chưa tính giá booking, độ hợp hình ảnh nhãn hàng, lịch của kênh · không có doanh số và người theo dõi ảo.
6. **Việc nên làm tiếp** — một câu (ví dụ xem người theo dõi ở nước nào — nêu giá; đọc bình luận một video của kênh — nêu giá).

Khi khuyên: nói bạn nghiêng về kênh nào, vì con số nào, và điều gì có thể làm đổi ý. Kênh nhiều người theo dõi mà một video bình thường ít lượt xem thì nói thẳng. Không viết «chắc chắn bán được», «đảm bảo hiệu quả».
