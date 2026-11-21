---
name: de-tai-youtube
description: Tìm đề tài cho video YouTube bằng số liệu công khai — tìm trong một ngách những video «thắng» (lượt xem vượt xa mức thường của chính kênh đăng nó), gom thành các họ đề tài, đếm bao nhiêu kênh khác nhau cùng thắng một đề; hoặc soi một kênh YouTube xem video nào nổ so với mức thường của kênh — bằng «Tìm video YouTube theo từ khoá» và «Video mới trên kênh YouTube đối thủ» của HG Trend. Dùng khi người làm YouTube (kênh kể chuyện, truyện audio, kênh không lộ mặt, kênh làm bằng AI, người sắp mở kênh) hỏi «làm video gì bây giờ», «đề tài nào đang lên trong ngách [X]», «video nào đang nổ ở ngách này», «kênh nhỏ nào vừa có video bùng view», «kênh @… video nào nổ nhất», «ngách này còn làm được không». Dùng cả cho câu hỏi về RPM, doanh thu, tỉ lệ bấm, tỉ lệ giữ chân của kênh người khác — HG Trend không có các số đó, kỹ năng nói rõ trả lời thế nào.
---
# Đề tài YouTube: video nào đang thắng trong ngách

Người dùng làm kênh YouTube và cần chọn đề cho video tới. Kỹ năng này không nghĩ đề thay họ: nó **lấy số thật** của các video đang có trong ngách, tìm video nào vượt xa mức thường của chính kênh đăng nó, rồi lập bảng cho người dùng chọn. Mọi số là dữ liệu công khai lúc chạy và chỉ là **một mẫu nhỏ** của ngách.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

Chỉ dùng trường thật sự có trong kết quả; thiếu số nào (lượt xem, ngày đăng, độ dài) thì nói thiếu, không đoán. Trong kết quả có `credits_charged`, `credits_remaining`: đó là số của nguồn, **không phải token của người dùng** — đừng nhắc tới.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Tìm đề tài, ý tưởng video cho một ngách | Chặng 1 rồi chặng 2 ở dưới |
| Đã có một kênh cụ thể, hỏi «kênh này video nào nổ» | Chỉ chặng 2 cho kênh đó: «Video mới trên kênh YouTube đối thủ» (`hgg3hy22`) |
| Đã chọn được một video thắng, muốn biết nó kể thế nào, người xem nói gì | Kỹ năng mo-video-mau (chép lời, số liệu video, bình luận) — lượt thêm, nêu giá và chờ đồng ý |
| Video ngắn (Shorts), TikTok đang hot | Kỹ năng bat-trend. Kỹ năng này tìm video dài (từ 3 phút) ở chặng 1 |
| Đề lấy từ Trung Quốc (Douyin, Bilibili, Weibo, truyện, phim Trung Quốc) | Kỹ năng de-tai-tu-trung-quoc |
| **Chỉ** hỏi doanh thu, RPM, tỉ lệ bấm vào bìa, tỉ lệ giữ chân, nguồn lượt xem của kênh người khác | **Không chạy.** Nói HG Trend không có các số này (chỉ chủ kênh xem được trong YouTube Studio) và **không tự đưa con số ước** từ kiến thức chung; hỏi họ có muốn xem lượt xem công khai của các video trong ngách không |
| «Đề này chắc chắn lên không», «làm theo có kiếm được tiền không» | Không hứa. Nói bảng chỉ cho biết đề nào **đã** thắng ở kênh khác; kênh của họ ra sao còn tuỳ tiêu đề, bìa, cách kể |
| Đề tài cho TikTok, Facebook | Không thuộc kỹ năng này: `tim_cong_cu` với tên nền tảng |

## Trước khi chạy

Cần biết hai thứ; thiếu thì hỏi **một lần**, gộp trong một câu:

1. **Ngách và ngôn ngữ của kênh** (ví dụ «kể chuyện lịch sử, tiếng Việt», «what if, tiếng Anh»).
2. **Một hai cụm tìm** mà người xem ngách đó hay gõ, đúng ngôn ngữ của kênh. Người dùng chưa có thì bạn đề xuất hai cụm và nói rõ đó là bạn đề xuất. Muốn biết người xem hay gõ gì: «Gợi ý từ khoá tìm kiếm trên YouTube» (`hgharr5k`, ~5 token) trả các cụm YouTube gợi ý khi gõ một chữ (ở lượt thử: 14 cụm, không kèm số lượt tìm) — lượt thêm, nêu giá.
Kỹ năng này chỉ tìm và so **video dài** (từ 3 phút). Người dùng muốn video ngắn (Shorts): nói HG Trend chưa có cách tìm Shorts theo ngách; có danh sách Shorts YouTube đang hot chung (kỹ năng bat-trend).

**Lượt đầu mặc định:** tối đa 2 cụm × 2 lượt tìm + đọc tối đa 8 kênh = tối đa 12 lượt. Ở các lượt thử, với đúng cách điền ở dưới: mỗi lượt tìm trừ **10 token**, mỗi lượt đọc kênh trừ **10 token** — cả lượt đầu khoảng **120 token**. Kho ghi khoảng giá rộng hơn (tìm ~5–78 token, đọc kênh ~5–77 token) vì mỗi công cụ có vài nguồn; **điền đúng tên tham số như các lệnh ở dưới, không thêm bớt**, cửa sẽ chọn đúng nguồn đã thử.

Cầu dao: lượt nào trừ **quá 15 token** thì **dừng**, báo người dùng giá thật của lượt đó, tổng ước cho các lượt còn lại, và chờ đồng ý. Dòng đầu câu trả lời nêu **tổng token đã trừ ghi trong các kết quả**; chỉ khi kết quả không ghi mới nêu số ước và nói đó là ước. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu: với các lệnh ghi sẵn trong kỹ năng này, cộng theo **giá đã đo ở lượt thử** ghi trong kỹ năng — không theo mức cao của khoảng giá trong kho (mức cao là của nguồn khác mà các lệnh này không dùng); công cụ nào kỹ năng không ghi giá đo thì cộng theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy): đã chạy gì, cho cụm / kênh / link / từ nào (kèm từ đã dịch nếu có) · dữ liệu lấy từ đâu · lượt này tốn bao nhiêu — số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token và nói là ước. Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi tự chạy thêm lượt (cụm khác, kênh khác, video khác), khi thiếu thông tin bắt buộc, khi tổng vượt ngưỡng. Họ **chỉ** hỏi thứ dữ liệu không có thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

Người dùng muốn quét rộng hơn (thêm cụm, thêm kênh): nói sẽ thêm bao nhiêu lượt, khoảng bao nhiêu token, và chờ đồng ý.

## Chạy

**Chặng 1 — tìm video trong ngách.** Mỗi cụm chạy hai lượt: nhiều lượt xem nhất trong tháng, và nhiều lượt xem nhất trong năm.

```
chay_cong_cu(ma="hg4tsgov", tham_so={"query": "<cụm tìm>", "type": "videos", "sortBy": "popular", "uploadDate": "this_month"}, cat_ky_tu=45000)
chay_cong_cu(ma="hg4tsgov", tham_so={"query": "<cụm tìm>", "type": "videos", "sortBy": "popular", "uploadDate": "this_year"}, cat_ky_tu=45000)
```

- `sortBy` chỉ nhận «relevance» hoặc «popular». `uploadDate`: «today», «this_week», «this_month», «this_year». **Giữ đủ bốn tham số này**: chỉ điền mỗi `query` thì cửa chuyển sang một nguồn khác, kết quả không có mã kênh để làm chặng 2.
- Mỗi lượt trả khoảng 20 video trong `videos` (ở lượt thử không bị cắt). Buổi phát trực tiếp nằm riêng trong `lives`, video ngắn trong `shorts`: không lấy hai danh sách đó.
- Thêm `region` = «VN» ở lượt thử **không làm đổi kết quả**: đừng viết «kết quả của riêng Việt Nam».

Đọc mỗi video trong `videos`:

| Trường | Là gì | Lưu ý |
|---|---|---|
| `title`, `url` | Tiêu đề và link | Tiêu đề có khi là **bản YouTube tự dịch sang tiếng Anh** dù kênh nói tiếng Việt: ghi «tiêu đề hiện bằng tiếng Anh, có thể là bản tự dịch», đừng coi là tiêu đề trong kết quả |
| `viewCountInt` | Lượt xem lúc chạy | Số nguyên, dùng số này để so |
| `lengthSeconds` | Độ dài, tính bằng giây | Dưới 180 giây thì bỏ (kỹ năng này so video dài) |
| `publishedTimeText` | «12 days ago», «3 weeks ago»… | **Dùng trường này để nói video đăng khi nào.** `publishedTime` trông như ngày giờ chính xác nhưng chỉ là máy suy ra từ dòng chữ trên — không viết thành «đăng ngày 13/8» |
| `channel` → `id`, `title`, `handle` | Mã kênh, tên kênh, tên sau dấu @ | Chặng 2 cần **`id`** (bắt đầu bằng «UC»). `handle` có khi trống hoặc là chuỗi ký tự mã hoá: khi gọi công cụ thì dùng `id` |

- Bỏ khỏi danh sách: video không thuộc ngách (cụm tìm trùng chữ nhưng khác chuyện — ở lượt thử «lịch sử việt nam» lẫn cả video tin thời sự, đố vui), video dưới 180 giây, video trùng giữa hai lượt. Nói đã bỏ bao nhiêu.
- Cụm tìm quá chung (ví dụ «what if you») ra lẫn nhiều loại kênh giải trí lớn: ít video dùng được thì nói thẳng và đề nghị một cụm sát ngách hơn (lượt thêm, nêu giá).

**Chọn kênh để đọc ở chặng 2** (tối đa 8 ở lượt đầu): lấy kênh của các video thuộc ngách đứng đầu danh sách, mỗi kênh một lần. Kết quả tìm **không có số người đăng ký**: chưa biết kênh nào nhỏ cho tới khi đọc kênh.

**Chặng 2 — đo mức thường của từng kênh.**

```
chay_cong_cu(ma="hgg3hy22", tham_so={"channelId": "<mã kênh bắt đầu bằng UC, lấy ở chặng 1>", "sort": "latest"}, cat_ky_tu=45000)
```

- Trả khoảng 30 video mới nhất của kênh trong `videos` (ở lượt thử 21/11: 30 video, không bị cắt), mỗi video có `title`, `url`, `viewCountInt`, `lengthSeconds`, `publishedTimeText` như ở chặng 1. Video ngắn của kênh nằm riêng trong `shorts`: không lấy.
- Điền `channel` + `limit` (cách ghi ở bản cũ của kỹ năng) thì kho hiện tại báo lỗi thiếu tham số: đừng dùng.
- Người dùng chỉ đưa tên kênh sau dấu @: chạy «Số liệu kênh YouTube của đối thủ» (`hgjmonrl`) với `handle` (bỏ dấu @) để lấy mã kênh, rồi đọc kênh — hai lượt, 20 token ở lượt thử, nằm trong việc họ hỏi nên chạy luôn. Đừng đoán mã.

## Tính «video thắng»

Làm cho từng kênh đã đọc ở chặng 2:

1. Lấy các video dài (từ 180 giây) của kênh có trong `videos`. **Bỏ video mới đăng chưa đủ 3 ngày** («… hours ago», «1 day ago», «2 days ago») khỏi cả phần làm nền lẫn phần xét thắng: chúng chưa kịp có lượt xem và kéo lệch mức thường; ghi đã bỏ mấy video.
2. **Mức thường của kênh** = xếp lượt xem của các video dài **khác** (không tính video đang xét) từ thấp tới cao, lấy số đứng giữa; số video là số chẵn thì lấy trung bình cộng của hai số đứng giữa. Video nền nào **không có lượt xem** trong kết quả thì bỏ khỏi phép tính và đếm đã bỏ mấy video. Còn dưới 5 video dài khác có lượt xem để làm nền thì **không tính, không gọi video nào là thắng**: ghi «chưa đủ video để so».
   Mức thường này chỉ tính trên **các video nhận được trong kết quả** (thường là các video mới nhất), không phải cả lịch sử kênh — nói đúng như vậy.
3. Video có lượt xem **từ 3 lần mức thường trở lên** là «video thắng». Mốc 3 lần là mốc khởi đầu của kỹ năng này, không phải chuẩn của mọi ngách: người dùng muốn mốc khác thì dùng mốc của họ và ghi rõ.
   **Kênh có hơn một phần ba số video «thắng»** (ở lượt thử: một kênh 27 video có 10 video vượt mốc, vì phần lớn video còn lại chỉ vài trăm lượt xem): mức thường của kênh đó quá thấp để làm thước. Đừng liệt kê cả loạt là thắng; ghi «kênh này chưa có mức thường ổn định» và chỉ nêu một hai video nhiều lượt xem nhất của kênh, kèm lượt xem thật.
   **Bội số trên 20 lần** gần như luôn do mức thường của kênh rất thấp: vẫn kể, ghi rõ điều đó, và không xếp nó trên một video có lượt xem thật cao hơn nhiều chỉ vì bội số.
4. Video đăng dưới một tháng còn đang chạy lượt xem: vẫn tính, và ghi «đăng … trước» bên cạnh để người dùng tự cân.

Tính bằng số trong kết quả, **viết phép tính ra được** khi người dùng hỏi (mức thường bao nhiêu, lấy từ mấy video). Chỉ dùng lượt xem là số nguyên (`viewCountInt`); gặp số viết tắt kiểu «1.2M» mà không có số nguyên đi kèm thì bỏ video đó khỏi phép tính và nói vậy.

**Kênh lớn.** Ở kênh rất đông người xem, video nào cũng nhiều lượt xem nên ít khi vượt 3 lần mức thường. Vì vậy lập thêm một danh sách ngắn «nhiều lượt xem nhất trong phần đã tìm» (không so với mức kênh) để không bỏ sót đề lớn — ghi rõ danh sách này **không** chứng tỏ đề đó thắng ở kênh nhỏ.

## Gom họ đề tài

Sau khi có các video thắng:

- Gom những video có **cùng lời hứa về cùng một chủ đề** thành một họ (ví dụ «nếu bạn sinh ra ở nước X», «một ngày của người làm nghề Y»). Tên họ do bạn đặt — nói rõ đó là cách bạn gom.
- Xếp các họ theo **số kênh khác nhau** có video thắng trong họ, rồi mới tới số video thắng. Một đề thắng ở hai ba kênh khác nhau, nhất là kênh nhỏ, đáng tin hơn một video nổ ở một kênh.
- Họ chỉ có một video ở một kênh: vẫn kể, ghi «mới thấy ở một kênh».
- Chỉ dùng video **có thật trong kết quả**, kèm link. Không thêm video bạn nhớ từ trước.

## Khi người dùng muốn đi sâu một video

Chép lời, đọc số liệu, đọc bình luận một video: theo kỹ năng mo-video-mau. Ở đây chỉ nói giá ước và chờ đồng ý.

Số người đăng ký của một kênh khi cần: «Số liệu kênh YouTube của đối thủ» (`hgjmonrl`), điền `channelId` = `id` lấy ở chặng 1 (người dùng chỉ đưa tên sau dấu @ thì điền `handle`) — lượt thêm, 10 token ở lượt thử. Trả `subscriberCount`, `videoCount` (số video), `viewCount` (tổng lượt xem cả kênh).

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Những điều dễ sai

- **Mẫu nhỏ.** Bạn mới xem vài chục video và tối đa 8 kênh, mỗi kênh tối đa 30 video mới nhất, không phải cả ngách. Viết «trong phần tôi đã xem», không viết «ngách này», «cả YouTube».
- **Lượt xem không phải lượt xem tự nhiên.** Số công khai không cho biết bao nhiêu lượt đến từ quảng cáo trả tiền. Không viết «video tự nhiên», «viral tự nhiên».
- **Thắng ở kênh khác chưa chắc thắng ở kênh người dùng.** Chỉ nói đề đó **đã** kéo người xem ở đâu, bao nhiêu kênh.
- **Không có:** doanh thu, RPM, tỉ lệ bấm, tỉ lệ giữ chân, số lần hiển thị, độ tuổi người xem của kênh người khác. Không ước các số này từ lượt xem.
- **Hai lượt tìm trùng nhau nhiều** (tháng nằm trong năm): đếm mỗi video một lần.
- **Tiêu đề giật gân** không có nghĩa là video thắng: chỉ gọi là thắng khi qua phép tính ở trên.
- Kết quả bị cắt (`rut_gon`): nói đã xem được bao nhiêu video trong bao nhiêu video trả về; mọi phép tính chỉ đúng cho phần đã xem.

## Trả lời người dùng

Trước khi gửi, soát: **mỗi dòng trong bảng có tiêu đề, link, lượt xem thuộc về cùng một video** (thấy lệch thì sửa ngay trong bảng — không gửi bảng sai kèm lời đính chính bên dưới) · số và tên chép đúng từ kết quả · mỗi video trong bảng có link · không thêm lý do «vì sao nó nổ» như dữ kiện (đó là phỏng đoán — muốn nói thì ghi «theo tôi») · nêu cỡ mẫu · nhận định ghi rõ là của bạn.

Viết bằng lời thường, không đưa tên trường tiếng Anh; mỗi con số nêu một lần. **Cả câu trả lời gọn trong khoảng 600 chữ** (ở lượt thử, câu trả lời không giới hạn dài tới 1.500 chữ, người dùng không đọc hết): mỗi họ đề chỉ **một** video tiêu biểu, chi tiết phép tính chỉ đưa khi người dùng hỏi. Bố cục:

1. **Dòng đầu:** đã tìm cụm nào hoặc đọc kênh nào, đọc mấy kênh · dữ liệu công khai trên YouTube lúc chạy · tổng token đã trừ (kết quả không ghi thì giá ước, nói là ước).
2. **Câu mở** — trả lời thẳng: trong phần đã xem, họ đề nào có nhiều kênh cùng thắng nhất (mấy kênh, mấy video). Không có họ nào nổi lên thì nói thẳng vậy.
3. **Bảng họ đề tài** — tối đa 5 dòng: họ đề · số kênh có video thắng · số video thắng · video tiêu biểu (tiêu đề trong kết quả, link).
4. **Bảng video thắng** — tối đa 8 dòng, xếp theo số lần vượt mức thường; video trên 20 lần do mức thường của kênh rất thấp thì để cuối bảng, ghi «mức thường của kênh rất thấp»: tiêu đề trong kết quả · kênh · lượt xem · mức thường của kênh · gấp mấy lần · ngày đăng · link. Tiêu đề tiếng nước ngoài giữ nguyên, thêm nghĩa tiếng Việt ngắn trong ngoặc khi người dùng viết tiếng Việt.
5. **Nhiều lượt xem nhất trong phần đã tìm** — hai ba dòng, chỉ khi có đề lớn không lọt bảng trên.
6. **Nhận định của bạn** — hai ba câu, mở bằng «Theo tôi»: nghiêng về họ đề nào và vì con số nào; điều gì làm bạn đổi ý. Không viết «chắc chắn lên», «sẽ có view».
7. **Dòng lưu ý cuối** — một dòng «Lưu ý khi đọc số: …» gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · mới xem bao nhiêu video, mấy kênh · mốc thắng là 3 lần mức thường của chính kênh đó, tính trên các video nhận được · lượt xem công khai không tách được lượt từ quảng cáo · kênh nào chưa đủ video để so · phần nào lần này không lấy được.
8. **Việc nên làm tiếp** — một câu: chọn một đề rồi **chốt tiêu đề và bìa trước khi viết kịch bản**; muốn đi sâu một video thắng (kỹ năng mo-video-mau) hay quét thêm thì nêu giá và chờ đồng ý.
