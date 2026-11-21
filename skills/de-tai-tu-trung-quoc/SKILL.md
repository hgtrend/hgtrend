---
name: de-tai-tu-trung-quoc
description: Tìm đề tài làm video từ Trung Quốc — Douyin, Bilibili, Weibo lúc này đang hot gì, phim bộ phim lẻ Trung Quốc nào đang được xem, truyện Trung Quốc nào đang được các kênh giới thiệu truyện trên Douyin, Bilibili làm video nhiều, đọc hiểu một video Douyin — bằng các bảng hot và công cụ tìm video của HG Trend. Dùng khi người làm video (truyện audio, tóm tắt phim, kể chuyện, kênh làm lại nội dung) hỏi «bên Trung Quốc đang hot gì», «Douyin đang có trend gì», «top truyện Trung Quốc», «truyện nào đang hot bên Trung», «phim Trung nào đang hot để làm review», «Bilibili đang xem gì», «video Douyin này nói gì». Kỹ năng nói rõ HG Trend không có bảng xếp hạng truyện chữ của các trang đọc truyện Trung Quốc và nhắc chuyện bản quyền khi định đọc, dịch nguyên truyện.
---
# Đề tài từ Trung Quốc

Người dùng làm video cho người Việt và muốn lấy đề từ Trung Quốc: chủ đề đang nổi trên Douyin, Bilibili, phim Trung Quốc đang được xem, truyện đang được giới thiệu nhiều. Kết quả là **dữ liệu gốc bằng tiếng Trung**: bạn đọc, dịch tên, đếm, rồi kể lại bằng tiếng Việt. Mọi bảng là **ảnh chụp lúc chạy**, không đoán được tuần sau.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| «Bên Trung Quốc / Douyin đang hot gì», «có đề gì hay» | Ba bảng rẻ: chủ đề hot Douyin + từ khoá hot Douyin + video hot Bilibili (khoảng 15 token ở lượt thử) |
| «Weibo đang bàn gì» | Bảng hot Weibo (`hgqndiyk`, ở lượt thử 77 token). Phần lớn là tin thời sự, chuyện người nổi tiếng: nói vậy trước |
| «Phim Trung nào đang hot» (làm review, tóm tắt phim) | Phim bộ: `hgt4pmzq`; phim lẻ: `hgkysktv` (phim bộ 77 token ở lượt thử; phim lẻ chưa thử — `xem_cong_cu` xem giá trước) |
| «Top truyện Trung Quốc», «truyện nào đang hot bên Trung» | Xem mục «Truyện» ở dưới: **HG Trend không có bảng xếp hạng truyện chữ**; có cách đo gần nhất là truyện nào đang được các kênh giới thiệu truyện làm video nhiều |
| Một chủ đề cụ thể (vd «truyện tu tiên», «phim cổ trang») | Tìm video theo từ tiếng Trung trên Douyin (`hgerlg6i`) hoặc Bilibili (`hgaut3zn`) |
| Link một video Douyin, muốn biết nói gì | «Dịch bài Tiểu Hồng Thư, Douyin sang tiếng Việt» (`hgdichtq`, ~77–116 token) — chỉ có chữ mô tả, hashtag, số liệu; **không nghe lời nói trong video** |
| Link một trang web (trang truyện, bài báo) | «Đọc một trang web ngay lúc hỏi» (`hgdoctrang`, 0 token) |
| Tiểu Hồng Thư, Kuaishou, Zhihu, Toutiao | Không thuộc kỹ năng này: `tim_cong_cu` với tên nền tảng |
| Đề YouTube, TikTok ở Việt Nam | Kỹ năng de-tai-youtube, bat-trend |

## Trước khi chạy

- Từ khoá tìm trên Douyin, Bilibili phải là **tiếng Trung**: bạn dịch, cho người dùng xem từ đã dịch ở dòng đầu. Ví dụ ở lượt thử: «小说推文» (video giới thiệu truyện), «小说解说» (video kể lại truyện).
- Giá ở lượt thử: ba bảng rẻ mỗi bảng 5 token; bảng Weibo, bảng phim Douban, tìm video Douyin, tìm video Bilibili mỗi lượt 77 token. Kho ghi khoảng giá rộng hơn (tìm Douyin ~52–160 token) vì mỗi công cụ có vài nguồn. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu: với các lệnh ghi sẵn trong kỹ năng này, cộng theo **giá đã đo ở lượt thử** ghi trong kỹ năng — không theo mức cao của khoảng giá trong kho (mức cao là của nguồn khác mà các lệnh này không dùng); công cụ nào kỹ năng không ghi giá đo thì cộng theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy): đã chạy gì, cho cụm / kênh / link / từ nào (kèm từ đã dịch nếu có) · dữ liệu lấy từ đâu · lượt này tốn bao nhiêu — số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token và nói là ước. Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi tự chạy thêm lượt (cụm khác, kênh khác, video khác), khi thiếu thông tin bắt buộc, khi tổng vượt ngưỡng. Họ **chỉ** hỏi thứ dữ liệu không có thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

## Chạy

```
chay_cong_cu(ma="hgdyxi33", tham_so={}, cat_ky_tu=30000)
chay_cong_cu(ma="hgi7665d", tham_so={}, cat_ky_tu=30000)
chay_cong_cu(ma="hg34h5nz", tham_so={}, cat_ky_tu=30000)
chay_cong_cu(ma="hgqndiyk", tham_so={"page": 1}, cat_ky_tu=30000)
chay_cong_cu(ma="hgt4pmzq", tham_so={"page": 1}, cat_ky_tu=30000)
chay_cong_cu(ma="hgerlg6i", tham_so={"keyword": "<từ tiếng Trung>"}, cat_ky_tu=30000)
chay_cong_cu(ma="hgaut3zn", tham_so={"keyword": "<từ tiếng Trung>", "page_size": 20}, cat_ky_tu=30000)
chay_cong_cu(ma="hgdichtq", tham_so={"link": "<link video Douyin>"})
```

Bảng phim lẻ `hgkysktv`: `xem_cong_cu` trước (kỹ năng này chưa thử bảng đó).

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

Kết quả là dữ liệu thô, nhiều trường kỹ thuật (ảnh bìa, mã theo dõi): bỏ qua, chỉ đọc các trường dưới. Kết quả dài **bị cắt** (`rut_gon` ghi giữ bao nhiêu mục — ở lượt thử: từ khoá hot Douyin giữ 19/51, tìm Bilibili 11/20, tìm Douyin 5 video): mọi phép đếm chỉ đúng cho phần đã xem, nói rõ «trong … mục đọc được».

| Bảng | Đọc gì | Lưu ý |
|---|---|---|
| Chủ đề hot Douyin (`hgdyxi33`) | `item_list`: `title` (tên chủ đề), `play_count` (lượt xem), `publish_count` (số video), `like_count`, `comment_count`, `share_count` | Là **chủ đề cho người làm video** (ở lượt thử: «短剧推荐» giới thiệu phim ngắn, «ai短剧» phim ngắn làm bằng AI, «好剧推荐»), không phải tin tức. Kết quả không ghi lượt xem tính trong bao lâu: nói «không ghi của kỳ nào» |
| Từ khoá hot Douyin (`hgi7665d`) | `data` → `word_list`: `word`, `hot_value` (điểm hot Douyin tự chấm), `view_count`, `discuss_video_count`; `active_time` là giờ cập nhật bảng | Phần lớn là tin tức, thể thao, chuyện người nổi tiếng. Dịch `word`. Mục đầu có khi `hot_value` = 0 là mục được ghim, không xếp theo điểm |
| Video hot Bilibili (`hg34h5nz`) | `data`: `title`, `bvid`, `cover_right_text_1` (độ dài), `right_desc_1` (kênh), `right_desc_2` (lượt xem · lúc đăng, vd «325.6万观看 · 8小时前») | Chỉ khoảng 10 video. «万» = 10.000 (325.6万 = khoảng 3,26 triệu). Link: `https://www.bilibili.com/video/` + `bvid` |
| Hot Weibo (`hgqndiyk`) | `data` → `realtime`: `word`, `num` (điểm nóng), `label_name` («新» mới, «热» nóng) | Phần lớn là thời sự; chuyện chính trị, tai nạn không nên làm video giải trí |
| Phim Douban (`hgt4pmzq`) | `items`: `title`, `rating` → `value` (điểm trên 10), `count` (số người chấm), `card_subtitle` (năm / nước / thể loại / đạo diễn / diễn viên), `episodes_info` | `count` = 0 là phim mới chưa đủ người chấm: không nói «điểm 0». Có cả phim Hàn, phim Mỹ: đọc nước trong `card_subtitle` |
| Tìm video Douyin (`hgerlg6i`) | `business_data` → `data` → `aweme_info`: `aweme_id`, `desc` (chú thích), `create_time`, `duration` (mili giây), `statistics` → `digg_count` (thích), `comment_count`, `share_count`; `author` → `nickname` | **`play_count` luôn bằng 0** (Douyin giấu lượt xem): dùng lượt thích để so. `create_time` là số giây tính từ 1/1/1970: chỉ dùng để xếp cũ mới; nói ngày thì ghi «khoảng tháng …». Link: `https://www.douyin.com/video/` + `aweme_id` |
| Tìm video Bilibili (`hgaut3zn`) | `data` → `result`: `title` (bỏ thẻ `<em>`), `play` (lượt xem), `favorites` (lượt lưu), `duration`, `pubdate`, `author`, `tag`, `arcurl` (link) | `pubdate` cũng là số giây như trên. Kết quả lẫn video không đúng chủ đề (trùng chữ): bỏ và nói đã bỏ bao nhiêu |
| Đọc một video Douyin (`hgdichtq`) | `bai` (tác giả, lượt thích / lưu / bình luận / chia sẻ, ngày đăng, độ dài), `nguyen_van`, `tu_lang_hg_giai_nghia` | Dịch theo `yeu_cau_cho_tro_ly`. Chỉ có chữ mô tả: không biết video nói gì bên trong |

## Truyện Trung Quốc

**HG Trend không có bảng xếp hạng truyện chữ** của các trang đọc truyện Trung Quốc (lượt đọc, phiếu bầu). Nói thẳng điều đó trước, rồi đề nghị cách đo gần nhất, nêu giá và chờ đồng ý:

1. Tìm video giới thiệu truyện trên Douyin và Bilibili bằng «小说推文» (hoặc từ hẹp hơn theo thể loại họ muốn: «修仙小说» tu tiên, «甜宠小说» ngôn tình ngọt…) — hai lượt, khoảng 154 token ở lượt thử.
2. Đọc tên truyện trong `desc`, `title`, `tag` (thường nằm trong 《》). Nói đã đọc bao nhiêu video (kết quả hay bị cắt, xem `rut_gon`). Đếm **mỗi truyện được bao nhiêu video nhắc, tổng lượt thích (Douyin) / lượt xem (Bilibili) của các video đó**.
3. Báo là «truyện được các kênh giới thiệu truyện làm video nhiều trong phần đã xem» — **không gọi là «top truyện», «truyện hot nhất Trung Quốc»**. Một truyện chỉ một video nhắc: ghi «mới thấy ở một video».

**Bản quyền — nói một lần, ngắn,** khi người dùng định **đọc lại, dịch nguyên truyện, lồng tiếng phim** để đăng: truyện và phim Trung Quốc có tác giả, nhà phát hành giữ quyền; đăng bản đọc hay bản dịch nguyên văn khi chưa có quyền dễ bị gỡ video, bị khiếu nại. HG Trend không kiểm được truyện nào đã có quyền. Tự viết nội dung mới từ một ý tưởng chung thì ít rủi ro hơn; còn bám theo cốt truyện, nhân vật, hình hay lời gốc thì người dùng vẫn phải tự kiểm quyền sử dụng. Không giảng thêm luật; không từ chối giúp phần tìm đề.

## Trả lời người dùng

Người dùng chọn đề, chọn từ khoá, viết nội dung theo câu trả lời này. **Soát trước khi gửi:**

- **Số, tên, link chép đúng** và mỗi dòng bảng có tên, link, con số thuộc về cùng một mục.
- **Nói cỡ mẫu:** đã xem bao nhiêu mục trong bao nhiêu mục trả về; kết quả bị cắt (`rut_gon` ghi giữ bao nhiêu mục) thì nói mới xem được chừng ấy. Không nói thay cả nền tảng, cả ngách.
- **Không thêm lý do như dữ kiện:** «vì sao một video, một đề, một từ nổi lên» là phỏng đoán — viết «theo tôi» và chỉ ra con số hay chi tiết đỡ cho nó; đếm không được thì bỏ.
- **«Tất cả», «đều», «không mục nào»** chỉ viết khi đã soát từng mục.
- **Không hứa:** không viết «chắc chắn lên», «sẽ có view», «làm theo là kiếm được tiền».
- Chữ, nhãn tiếng nước ngoài thì dịch; tên riêng giữ nguyên.

Riêng với kỹ năng này: tên tiếng Trung giữ nguyên, kèm nghĩa tiếng Việt trong ngoặc (vd «短剧推荐 (giới thiệu phim ngắn)»); tên truyện, tên phim nếu đã có tên tiếng Việt quen thì ghi, **không chắc thì chỉ dịch nghĩa**, đừng tự đặt tên Hán Việt như tên chính thức.

**Cách viết** — người đọc là người làm nội dung, làm marketing, đọc trên điện thoại:

- Dòng đầu nói giá lượt chạy, **ngay sau đó là câu mở trả lời thẳng**, kèm một hai con số chính.
- **Mỗi con số, mỗi ý nêu một lần.** Bảng khi xếp từ 3 mục cạnh nhau. Cả câu trả lời thường gọn trong khoảng 400–600 chữ, kể cả khi đã chạy vài lượt.
- **Lời thường, không viết tên trường.** Con số nói kèm kỳ đúng như kết quả ghi; kết quả không ghi kỳ thì nói «không ghi của kỳ nào». Gọi mỗi con số đúng tên của nó (lượt xem, lượt thích, điểm quan tâm…), không đổi loại.
- **Lưu ý về giới hạn dữ liệu gom vào MỘT dòng cuối** («Lưu ý khi đọc số: …»), mỗi ý một lần.
- **Kết bằng MỘT việc nên làm tiếp**, một câu; cần chạy thêm thì nêu giá và chờ đồng ý.

Bố cục:

1. **Dòng đầu** — đã chạy bảng nào / tìm từ nào (kèm nghĩa) / đọc link nào · dữ liệu lấy từ nền tảng nào lúc chạy · tổng token đã trừ (không ghi thì giá ước, nói là ước).
2. **Câu mở** — đề nào nổi nhất trong phần đã xem, kèm một con số.
3. **Bảng** — tối đa 8 dòng: tên (tiếng Trung + nghĩa) · nơi · con số chính (lượt xem / số video / lượt thích, ghi rõ loại) · link nếu có.
4. **Theo tôi, đề nên thử cho người xem Việt** — một hai đề, vì con số nào; đề thời sự Trung Quốc ít hợp người xem Việt thì nói.
5. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Với kỹ năng này thường là: bảng hot do nền tảng tự xếp, chụp lúc chạy · Douyin giấu lượt xem nên so bằng lượt thích · không có bảng xếp hạng truyện chữ.
6. **Việc nên làm tiếp** — một câu: tìm sâu một đề (nêu giá); hoặc xem đề đó đã có kênh Việt nào làm trên YouTube chưa bằng kỹ năng de-tai-youtube.
