---
name: mo-video-mau
description: Mổ một video mẫu trên YouTube hoặc TikTok để học cách kể — chép lời kèm mốc giờ, đọc số liệu video (lượt xem, thích, bình luận, độ dài, các chương), đọc bình luận nhiều lượt thích nhất để biết người xem khen, cãi, hỏi gì — bằng «Chép lời một video YouTube», «Chép lời một video TikTok» và các công cụ số liệu, bình luận của HG Trend. Dùng khi người làm video (YouTube, TikTok, kênh kể chuyện, truyện audio, review) đưa link một video và hỏi «video này mở đầu thế nào», «chép lời video này», «dàn ý video này», «vì sao video này nhiều view», «người xem bình luận gì», «học cách kể của video này», «làm video giống kiểu này». Muốn tìm video nào đang thắng trong ngách thì dùng kỹ năng de-tai-youtube; muốn đếm khen, chê của người mua dưới một sản phẩm thì dùng kỹ năng khach-khen-che.
---
# Mổ một video mẫu

Người dùng có một video họ muốn học theo. Kỹ năng này lấy **lời nói thật** của video, **số liệu công khai** của nó và **bình luận** của người xem, rồi rút ra cách video được dựng: mở đầu hứa gì, chia mấy đoạn, người xem phản ứng với chỗ nào. Mục đích là học **cách kể**, không phải chép nội dung.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

Trong kết quả có `credits_charged`, `credits_remaining`: đó là số của nguồn, **không phải token của người dùng** — đừng nhắc tới.

## Khi nào dùng

| Người dùng đưa / hỏi | Làm gì |
|---|---|
| Link video YouTube, muốn mổ cả video | Ba lượt: số liệu video + chép lời + bình luận (khoảng 30 token ở lượt thử) |
| Link video TikTok | Hai lượt: chép lời + bình luận. Số liệu video TikTok không thuộc kỹ năng này: `tim_cong_cu` với «thông tin video TikTok» |
| Chỉ hỏi «chép lời», «video này nói gì» | Chỉ lượt chép lời |
| Chỉ hỏi «người xem nói gì» | Chỉ lượt bình luận. Muốn **đếm** bao nhiêu khen, chê, hỏi: báo cáo «Tóm tắt bình luận: khách khen, chê gì» (`hgbinhluan`, ~2–30 token) theo kỹ năng khach-khen-che |
| Chưa có link, chỉ có tên kênh hay đề tài | Hỏi link. Muốn tìm video đáng mổ trong ngách: kỹ năng de-tai-youtube |
| Video Douyin, Bilibili | Kỹ năng de-tai-tu-trung-quoc |
| «Viết lại kịch bản y như video này», «dịch nguyên lời để đăng lại» | Không làm. Nói: lời video là của người làm ra nó; bạn chỉ đưa dàn ý và cách kể bằng lời của bạn để họ viết bài của riêng họ |
| Tỉ lệ giữ chân, tỉ lệ bấm, doanh thu của video người khác | **Không có** (chỉ chủ kênh xem được trong YouTube Studio). Không ước từ lượt xem |

## Trước khi chạy

Cần **một link video**. Nhiều link: mỗi link là một bộ lượt riêng; cộng token và hỏi trước nếu vượt ngưỡng. Ở các lượt thử, mỗi lượt trừ **10 token**; kho ghi khoảng giá rộng hơn (~9–42 token cho chép lời YouTube) vì mỗi công cụ có vài nguồn — **điền đúng tên tham số như các lệnh ở dưới**, cửa sẽ chọn nguồn đã thử. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu: với các lệnh ghi sẵn trong kỹ năng này, cộng theo **giá đã đo ở lượt thử** ghi trong kỹ năng — không theo mức cao của khoảng giá trong kho (mức cao là của nguồn khác mà các lệnh này không dùng); công cụ nào kỹ năng không ghi giá đo thì cộng theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy): đã chạy gì, cho cụm / kênh / link / từ nào (kèm từ đã dịch nếu có) · dữ liệu lấy từ đâu · lượt này tốn bao nhiêu — số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token và nói là ước. Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi tự chạy thêm lượt (cụm khác, kênh khác, video khác), khi thiếu thông tin bắt buộc, khi tổng vượt ngưỡng. Họ **chỉ** hỏi thứ dữ liệu không có thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

## Chạy

**YouTube**

```
chay_cong_cu(ma="hg3z3hfr", tham_so={"url": "<link video>"})
chay_cong_cu(ma="hgwzlx44", tham_so={"url": "<link video>", "language": "<mã tiếng hai chữ cái>"}, cat_ky_tu=45000)
chay_cong_cu(ma="hgaxbuwg", tham_so={"url": "<link video>"})
```

- Mổ cả video thì chạy lượt số liệu trước: biết video dài bao lâu, có chương không, nói tiếng gì (theo tiêu đề và mô tả). Người dùng chỉ xin chép lời thì chạy thẳng lượt chép lời.
- Chép lời: chưa chắc video nói tiếng gì thì **bỏ `language`**, đừng đoán — điền sai tiếng thì kết quả rỗng.

**TikTok**

```
chay_cong_cu(ma="hgjs2p3p", tham_so={"url": "<link video>"})
chay_cong_cu(ma="hgckpiif", tham_so={"url": "<link video>"})
```

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.
- Chép lời TikTok báo lỗi «không tìm thấy»: thường là video **không có lời nói** (chỉ nhạc, chỉ chữ trên hình). Nói vậy; không suy nội dung từ chú thích.

## Đọc kết quả

**Số liệu video YouTube** (`hg3z3hfr`)

| Trường | Là gì | Lưu ý |
|---|---|---|
| `title`, `description` | Tiêu đề, mô tả | Mô tả hay chứa dàn chương và link video khác của kênh |
| `viewCountInt`, `likeCountInt`, `commentCountInt` | Lượt xem, thích, bình luận lúc chạy | Số công khai, cộng dồn từ ngày đăng |
| `publishDate`, `publishDateText` | Ngày đăng | Dùng `publishDateText` khi nói với người dùng |
| `durationFormatted` | Độ dài | |
| `chapters` | Các chương kênh tự đặt: `title`, `timeDescription` (mốc giờ), `startSeconds` | Rỗng = kênh không chia chương. Có chương thì đây là **dàn ý chính chủ** — dùng trước, rồi đối chiếu với lời chép |
| `keywords` | Thẻ từ khoá kênh gắn | Không phải từ khoá người xem tìm |
| `isMadeWithAI` | Kênh tự khai video có hình hoặc tiếng làm bằng AI | Chỉ là lời khai của kênh |
| `isPaidPromotion` | Kênh tự khai có nội dung được trả tiền quảng bá | |
| `channel` | Tên, link kênh | |

**Lời chép** — YouTube (`hgwzlx44`): `transcript` là danh sách câu ngắn (`text`) kèm mốc giờ (`startTimeText`). TikTok (`hgjs2p3p`): `transcript_with_timestamp` là danh sách câu (`text`) kèm giây bắt đầu, kết thúc (`start`, `end`); đừng đọc `transcript` dạng chuỗi dài (trùng nội dung).
- Video dài thì danh sách **bị cắt** (lượt thử: video 25 phút còn tới phút 19:50; `rut_gon` ghi giữ bao nhiêu mục). Nói rõ bạn đọc được tới phút nào; **không tả đoạn kết khi chưa đọc được**.
- Lời chép do máy làm: có chỗ dính chữ, sai tên riêng. Trích lại thì sửa dính chữ, không đổi ý.

**Bình luận** — YouTube (`hgaxbuwg`): `comments` (ở lượt thử 20 bình luận), mỗi bình luận có `content`, `publishedTimeText`, `engagement` → `likes`, `replies`. TikTok (`hgckpiif`): `comments` (ở lượt thử 19), mỗi bình luận có `text`, `digg_count` (lượt thích), `reply_comment_total` (số trả lời).
- Đây là **một trang bình luận**, không phải mọi bình luận: nói «trong 20 bình luận đọc được». Không tính tỉ lệ khen chê từ một trang.
- Không nêu tên người bình luận.

## Rút cách kể

Từ lời chép (và chương nếu có), viết bằng lời của bạn:

1. **Nửa phút đầu** hứa với người xem điều gì; câu đầu tiên mở bằng gì (một cảnh, một con số, một câu hỏi). Trích tối đa **một câu ngắn** của video để minh hoạ, ghi mốc giờ.
2. **Các đoạn**: chia mấy đoạn, mỗi đoạn bắt đầu ở phút nào, mỗi đoạn mở bằng gì. Có chương thì theo chương.
3. **Nhịp**: đoạn nào dài nhất; chỗ nào có câu hỏi treo, lời hứa «lát nữa sẽ nói».
4. **Người xem phản ứng ở đâu**: bình luận nhiều lượt thích nhất nói về chi tiết nào, cãi chỗ nào, hỏi gì chưa được trả lời — đó là gợi ý cho video tiếp theo. Chỉ nói điều bình luận ghi, không đoán cảm xúc.

**Không chép câu chữ** của video vào kịch bản của người dùng, không dịch nguyên văn để dùng lại. Lý do vì sao video nhiều view là **phỏng đoán** — nói «theo tôi» và chỉ ra chi tiết nào đỡ cho nó.

## Trả lời người dùng

Người dùng chọn đề, chọn từ khoá, viết nội dung theo câu trả lời này. **Soát trước khi gửi:**

- **Số, tên, link chép đúng** và mỗi dòng bảng có tên, link, con số thuộc về cùng một mục.
- **Nói cỡ mẫu:** đã xem bao nhiêu mục trong bao nhiêu mục trả về; kết quả bị cắt (`rut_gon` ghi giữ bao nhiêu mục) thì nói mới xem được chừng ấy. Không nói thay cả nền tảng, cả ngách.
- **Không thêm lý do như dữ kiện:** «vì sao một video, một đề, một từ nổi lên» là phỏng đoán — viết «theo tôi» và chỉ ra con số hay chi tiết đỡ cho nó; đếm không được thì bỏ.
- **«Tất cả», «đều», «không mục nào»** chỉ viết khi đã soát từng mục.
- **Không hứa:** không viết «chắc chắn lên», «sẽ có view», «làm theo là kiếm được tiền».
- Chữ, nhãn tiếng nước ngoài thì dịch; tên riêng giữ nguyên.

**Cách viết** — người đọc là người làm nội dung, làm marketing, đọc trên điện thoại:

- Dòng đầu nói giá lượt chạy, **ngay sau đó là câu mở trả lời thẳng**, kèm một hai con số chính.
- **Mỗi con số, mỗi ý nêu một lần.** Bảng khi xếp từ 3 mục cạnh nhau. Cả câu trả lời thường gọn trong khoảng 400–600 chữ, kể cả khi đã chạy vài lượt.
- **Lời thường, không viết tên trường.** Con số nói kèm kỳ đúng như kết quả ghi; kết quả không ghi kỳ thì nói «không ghi của kỳ nào». Gọi mỗi con số đúng tên của nó (lượt xem, lượt thích, điểm quan tâm…), không đổi loại.
- **Lưu ý về giới hạn dữ liệu gom vào MỘT dòng cuối** («Lưu ý khi đọc số: …»), mỗi ý một lần.
- **Kết bằng MỘT việc nên làm tiếp**, một câu; cần chạy thêm thì nêu giá và chờ đồng ý.

Bố cục:

1. **Dòng đầu** — đã chạy gì cho link nào · dữ liệu công khai lúc chạy · tổng token đã trừ ghi trong các kết quả (không ghi thì giá ước, nói là ước).
2. **Câu mở** — video này dựng theo kiểu gì, trong một câu (vd «mở bằng một cảnh cụ thể có ngày giờ, rồi lùi về kể nguyên nhân qua 6 chương»), với YouTube kèm lượt xem và độ dài (TikTok: kỹ năng này không lấy số liệu video, đừng nêu).
3. **Dàn ý** — bảng: mốc giờ · đoạn nói gì (lời của bạn) · mở đoạn bằng gì. Tối đa 8 dòng.
4. **Người xem nói gì** — 3–5 ý từ bình luận, mỗi ý kèm số lượt thích của bình luận đó.
5. **Theo tôi, điều đáng học** — hai ba điều, mỗi điều chỉ ra chỗ nào trong video.
6. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Với kỹ năng này thường là: lời chép đọc được tới phút nào · bình luận là một trang, bao nhiêu câu · số liệu là số công khai lúc chạy.
7. **Việc nên làm tiếp** — một câu: thường là chọn tiêu đề và bìa cho video của họ trước khi viết kịch bản; hoặc mổ thêm một video cùng ngách để so (nêu giá).
