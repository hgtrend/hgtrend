---
name: spy-quang-cao
description: Spy quảng cáo của MỘT đối thủ — họ đang chạy những mẫu quảng cáo nào trên Facebook, Instagram (và Google nếu có tên miền), mỗi mẫu chạy từ ngày nào, được bao nhiêu ngày, dạng ảnh hay video, nút bấm, chữ quảng cáo, link xem mẫu — lấy từ thư viện quảng cáo công khai qua HG Trend. Dùng khi người dùng (agency, người chạy ads, chủ shop) hỏi «spy ads đối thủ», «soi ads», «đối thủ đang chạy camp gì», «mẫu nào chạy lâu nhất», «tìm mẫu win của [thương hiệu]», «họ mới bật mẫu nào», «mẫu quảng cáo này chạy bao lâu rồi», kèm tên thương hiệu, link trang hoặc link một mẫu quảng cáo; kể cả khi họ hỏi hiệu quả của quảng cáo (tiền đã tiêu, lượt hiển thị, CTR, ROAS, số đơn) — HG Trend chưa có các số này, kỹ năng nói rõ có dấu hiệu nào thay thế. Muốn xem cả kênh và bài đăng của đối thủ, hoặc quảng cáo của cả một ngành theo từ khoá, thì dùng kỹ năng soi-doi-thu.
---
# Spy quảng cáo đối thủ

Người dùng muốn biết MỘT đối thủ đang chạy mẫu quảng cáo nào và chạy bao lâu rồi. Dữ liệu lấy từ **thư viện quảng cáo công khai** của Facebook và Google — ai cũng xem được, không phải xem lén tài khoản của ai. Thư viện cho biết **mẫu nào đang chạy, từ ngày nào** — Facebook kèm cả chữ của mẫu, Google phải xem chi tiết từng mẫu mới có chữ; thư viện **không** cho biết tiền đã tiêu, lượt hiển thị hay số đơn của quảng cáo bán hàng ở Việt Nam.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Quảng cáo Facebook / Instagram của một thương hiệu, một trang: đang chạy mẫu nào, bao lâu rồi, mẫu nào chạy lâu nhất, mới bật mẫu nào | Hai bước ở mục «Chạy»: tìm trang, rồi lấy mẫu đang chạy của trang đó |
| Đưa link một mẫu trong thư viện quảng cáo Facebook, hỏi mẫu này chạy bao lâu, của ai | «Thông tin mẫu quảng cáo trên Facebook» (`hgrz7wcp`), mục «Một mẫu cụ thể» |
| Quảng cáo Google của một tên miền | Mục «Quảng cáo Google» |
| **Chỉ** hỏi tiền đã tiêu, lượt hiển thị, CTR, ROAS, số đơn, mẫu nào «ra đơn» | **Không chạy.** Nói HG Trend chưa có các số này (thư viện công khai không công bố cho quảng cáo bán hàng ở Việt Nam), rồi hỏi họ có muốn xem mẫu nào đang chạy và chạy bao lâu không |
| Hỏi mẫu nào «win», mẫu nào hiệu quả | Chạy như dòng đầu; trả lời bằng **dấu hiệu** (mục «Dấu hiệu, không phải bằng chứng»), nói rõ không có số đo hiệu quả |
| Muốn biết cả kênh, bài đăng lẫn quảng cáo của đối thủ | Kỹ năng soi-doi-thu (báo cáo «Soi kênh, bài đăng, quảng cáo đối thủ», `hgsoidt`) |
| Quảng cáo của cả một NGÀNH theo từ khoá, không có tên đối thủ | Kỹ năng soi-doi-thu, công cụ «Quảng cáo đang chạy trên Facebook» (`hgycspqa`) |
| Quảng cáo TikTok của đối thủ | Thư viện công khai của TikTok chủ yếu có quảng cáo chạy ở châu Âu, đối thủ Việt Nam thường không có ở đó. Nói vậy; không chạy trừ khi họ vẫn muốn thử (kỹ năng soi-doi-thu) |
| «Đối thủ của mình» mà không có tên, link | Hỏi tên thương hiệu hoặc link trang. Không đoán |
| Nhiều đối thủ | Mỗi đối thủ hai đến ba lượt; cộng token trước khi chạy |

## Trước khi chạy

Một câu hỏi về quảng cáo Facebook của một đối thủ thường tốn **hai đến ba lượt**: tìm trang (~10 token), rồi một hoặc hai lượt lấy mẫu đang chạy (~10 token mỗi lượt). **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token; đừng tự đổi ra đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ trừ token theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

**Điều người dùng hỏi ngay từ đầu** thì chạy theo luật trên (rẻ thì chạy luôn): hỏi mẫu mới bật thì chạy luôn lượt «mẫu mới bật» ở bước 2; đưa link một mẫu thì chạy luôn công cụ xem một mẫu.

**Lượt chạy thêm sau khi đã trả kết quả** (xem trang kế tiếp, xem thêm mẫu mới bật, xem chi tiết một mẫu, chép lời video): nêu giá và chờ đồng ý.

## Chạy

**Bước 1 — tìm đúng trang.** «Tìm bên chạy quảng cáo trên Facebook» (`hgev7dtl`), tham số `query` = tên thương hiệu, càng đầy đủ càng ít nhầm (người dùng chỉ đưa link trang thì lấy phần tên ở đuôi link làm `query`; link đã có sẵn mã trang dạng số thì dùng thẳng mã đó cho bước 2):

```
chay_cong_cu(ma="hgev7dtl", tham_so={"query": "Cocoon Vietnam"})
```

Kết quả là danh sách trang trong `searchResults`; mỗi trang có `name`, `page_id`, `likes` (số người thích trang), `category`, `verification` (trang đã được Facebook xác minh hay chưa), `page_alias` (phần đuôi của link trang: link = facebook.com/ + `page_alias`; trống thì không có link, nêu `page_id` thay), `ig_username`.

- Người dùng đã đưa link trang: chọn trang có `page_alias` hoặc `page_id` trùng với đuôi hay dãy số trong link.
- Chưa đưa link: chỉ tự chọn khi có **một** trang đúng tên mà `likes` gấp từ 5 lần trang nhiều người thích thứ nhì trở lên (danh sách không xếp sẵn theo số người thích — tự so cả danh sách). Luôn **nêu tên, số người thích, link trang đã chọn, trang đã được xác minh hay chưa**, và nhờ họ xác nhận đúng đối thủ — kết quả tìm trang không chứng minh đây là trang chính thức. Người dùng đã nói ngành hàng mà `category` của trang nhiều người thích nhất lại khác hẳn ngành đó (ví dụ họ hỏi mỹ phẩm mà trang là quán cà phê): dừng và hỏi.
- Thường có nhiều trang trùng tên (ở lượt thử, một thương hiệu mỹ phẩm ra một trang hơn 400 nghìn người thích và hơn mười trang cùng tên ít người thích hơn hẳn). Nói «còn mấy trang khác cùng tên»; **đừng gọi đó là trang giả hay đại lý** — dữ liệu không cho biết.
- Không trang nào gấp 5 lần trang nhiều người thích thứ nhì, hoặc không thấy trang đúng tên: **dừng**, kể các trang tìm được và hỏi họ chọn trang nào. Không tự chạy bước 2 cho trang đoán.

**Bước 2 — lấy mẫu đang chạy của trang đó.** «Quảng cáo trang Facebook đang chạy» (`hgimtlsf`). Mỗi lượt chỉ đọc được khoảng 8–13 mẫu (kết quả dài, cửa cắt bớt), nên **chọn lượt theo câu hỏi**:

```
# Lượt tổng quan — luôn chạy trước khi cần biết trang đang chạy tổng cộng bao nhiêu mẫu
chay_cong_cu(ma="hgimtlsf", tham_so={"pageId": "<page_id ở bước 1>", "country": "VN", "status": "ACTIVE", "trim": true}, cat_ky_tu=45000)

# Lượt «mẫu chạy lâu» — chỉ lấy mẫu đang chạy đã bắt đầu từ 3 tháng trước trở về trước
chay_cong_cu(ma="hgimtlsf", tham_so={"pageId": "<page_id>", "country": "VN", "status": "ACTIVE", "start_date": "2015-01-01", "end_date": "<ngày này 3 tháng trước, dạng năm-tháng-ngày>", "trim": true}, cat_ky_tu=45000)

# Lượt «mẫu mới bật» — mẫu mới nhất đứng đầu
chay_cong_cu(ma="hgimtlsf", tham_so={"pageId": "<page_id>", "country": "VN", "status": "ACTIVE", "sort_by": "relevancy_monthly_grouped", "trim": true}, cat_ky_tu=45000)
```

| Người dùng hỏi | Chạy lượt nào |
|---|---|
| «Đang chạy mẫu nào», «mẫu nào chạy lâu nhất», «mẫu win» | Lượt tổng quan, rồi lượt «mẫu chạy lâu» |
| «Mới bật mẫu nào», «dạo này họ chạy gì mới» | Chỉ lượt «mẫu mới bật» (kết quả cũng có tổng số mẫu đang chạy) |
| Chỉ hỏi «họ có đang chạy quảng cáo không, bao nhiêu mẫu» | Chỉ lượt tổng quan |

- `country` = «VN»: chỉ mẫu đang chạy ở Việt Nam. Người dùng hỏi nước khác thì đổi mã nước.
- Không lọc riêng được Instagram: tổng số mẫu là của cả trang trên mọi nơi hiện. Người dùng hỏi riêng Instagram thì nói vậy, và chỉ kể mẫu có Instagram trong `publisher_platform` trong số đã xem.
- **Giữ `trim` = true và `cat_ky_tu` = 45000.** Đặt cao hơn thì kết quả dài quá, nhiều trợ lý không đọc được trong một lượt. `rut_gon` ghi giữ bao nhiêu mẫu trên 30 mẫu nguồn trả mỗi lượt. Trong mỗi mẫu, danh sách con (nơi hiện, ảnh, video) chỉ giữ 3 mục đầu và chữ dài bị cắt: **đừng kết luận** «mẫu này không hiện ở nơi khác» hay coi chữ bị cắt là hết.
- **Lượt «mẫu chạy lâu»:** chạy **sau** lượt tổng quan, không chạy cùng lúc. `end_date` là mốc ngày — lấy `end_date_string` của một mẫu ở lượt tổng quan (đó là ngày thư viện ghi nhận gần nhất), lùi 3 tháng; người dùng nêu mốc khác (6 tháng, 1 năm) thì lùi theo mốc đó. `searchResultsCount` của lượt này là **số mẫu đang chạy đã bắt đầu từ mốc đó trở về trước** — ở lượt thử, một trang đang chạy 151 mẫu thì 33 mẫu đã chạy từ 6 tháng trở lên. Lượt này ra **0 mẫu** nghĩa là không mẫu đang chạy nào bắt đầu trước mốc: nói vậy, rồi lấy mẫu chạy lâu nhất trong các mẫu của lượt tổng quan.
- Thứ tự mặc định trong lượt tổng quan chỉ là thứ tự nguồn trả về (xem mục «Dấu hiệu»); ở lượt thử nó không có mẫu nào bật trong 4 tháng gần nhất — muốn biết mẫu mới thì phải chạy lượt «mẫu mới bật».
- **Xem tiếp:** `cursor` lấy từ kết quả lượt trước sẽ nhảy sang 30 mẫu kế tiếp của nguồn, **bỏ qua các mẫu bị cắt** của lượt trước; gọi lại lệnh cũ thì ra đúng các mẫu cũ. Người dùng muốn xem thêm thì nói rõ giới hạn này trước khi chạy (lượt thêm, hỏi trước); với mẫu chạy lâu, cách chắc hơn là đổi mốc `end_date` (6 tháng, 1 năm) để lọc hẹp lại.
- Tên trang ghi trong `snapshot` của một mẫu khác với trang đã chọn (mẫu chạy chung với một nhãn hàng, một nhà bán khác): ghi rõ mẫu đó đứng tên trang nào, đừng tính gọn là quảng cáo do đối thủ tự đứng tên.
- `credits_charged`, `credits_remaining` trong kết quả là số của nguồn dữ liệu, **không phải token của người dùng**: đừng đọc thành giá, đừng nhắc tới.

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

Công cụ lẻ trả **dữ liệu thô** tiếng Anh. Mỗi mục trong `results` là một mẫu quảng cáo. Ngày chạy, link, `collation_count`, `publisher_platform` nằm ngay trong mục; dạng mẫu, nút bấm, chữ, trang đích nằm trong khối `snapshot` của mục đó (chữ của mẫu ở `snapshot` → `body` → `text`).

| Trường | Là gì | Lưu ý |
|---|---|---|
| `searchResultsCount` | Số mẫu khớp điều kiện của lượt đó: lượt tổng quan và lượt «mẫu mới bật» = tổng số mẫu trang đang chạy ở nước đã chọn; lượt «mẫu chạy lâu» = số mẫu đã chạy từ mốc ngày trở về trước | Nêu cùng số mẫu đã xem: «trang đang chạy 151 mẫu, trong đó 33 mẫu đã chạy từ 6 tháng trở lên; tôi xem được 13 mẫu trong số 33». Đừng nói thay cả nhóm bằng mấy mẫu đã xem |
| `rut_gon` | Kết quả bị cắt còn bao nhiêu mục | Số mẫu đã xem = số mục thật có trong `results` |
| `start_date_string` | Ngày mẫu bắt đầu chạy | Đổi sang ngày/tháng/năm |
| `end_date_string` | Với mẫu đang chạy: ngày thư viện ghi nhận gần nhất (ngày lấy dữ liệu hoặc hôm trước) | **Số ngày đã chạy** = `end_date_string` trừ `start_date_string`. Viết «khoảng … ngày»; trên 60 ngày có thể nói theo tháng. Đừng lấy ngày bạn tự nghĩ là hôm nay để trừ |
| `display_format` | Dạng mẫu | «IMAGE» = một ảnh · «VIDEO» = video · «MULTI_IMAGES» = nhiều ảnh · «CAROUSEL» = ảnh trượt ngang. Giá trị khác thì ghi nguyên chữ và nói chưa rõ là dạng gì |
| `cta_text` | Nút bấm | «Send message» = Gửi tin nhắn · «Shop now» = Mua ngay · «Learn more» = Tìm hiểu thêm · «No button» hoặc trống = không có nút |
| `publisher_platform` | Mẫu hiện ở đâu | Facebook, Instagram, Messenger, Threads; «AUDIENCE_NETWORK» = các ứng dụng, trang ngoài Facebook có nhận quảng cáo của Facebook |
| `body` | Chữ của mẫu | Tóm ý chính bằng lời bạn, tối đa chừng 15 chữ; trích nguyên văn thì để trong «» |
| `link_url` | Bấm vào mẫu thì tới đâu | Có link thì nói mẫu dẫn tới đâu (link bắt đầu bằng «m.me» là dẫn vào nhắn tin), kể cả khi `cta_text` ghi «No button». Trống = mẫu không gắn link ra trang ngoài |
| `is_active` | Mẫu còn chạy không | false = mẫu đã tắt; khi đó `end_date_string` là ngày mẫu dừng |
| `url` | Link xem mẫu trong thư viện | Luôn kèm cho mẫu bạn nêu tên |
| `collation_count` | Số bản quảng cáo thư viện gộp chung một nhóm với mẫu này | 1 hoặc trống = không thấy bản nào khác cùng nhóm. Lớn hơn 1 = có chừng ấy bản gần giống nhau cùng chạy |
| `spend`, `reach_estimate` | Tiền đã tiêu, số người ước tiếp cận | **Trống với quảng cáo bán hàng ở Việt Nam** (trống ở mọi mẫu của các lượt thử). Trống là «thư viện không công bố», không phải «bằng 0». Không suy ra, không ước |
| `total_active_time` | Một con số tính bằng **giây**; theo tên trường là tổng thời gian mẫu đã được phát (nguồn không giải thích thêm) | Chỉ một số mẫu có (ở lượt thử: các mẫu mới bật có, các mẫu cũ để trống). Có thì chia 3600 để đổi ra giờ («thư viện ghi mẫu đã phát khoảng 5 giờ»); trống thì bỏ qua, đừng tự tính thay. Đây không phải lượt hiển thị. Với **mẫu mới bật** (chạy chưa tới vài ngày) dùng số giờ này thay cho phép trừ hai ngày — trừ ngày ra 0 hoặc 1 ngày là quá thô |

## Dấu hiệu, không phải bằng chứng

Không có số đo hiệu quả. Chỉ có ba dấu hiệu cho biết đối thủ **còn giữ mẫu đó chạy** — nêu dấu hiệu nào thì nêu luôn giới hạn của nó:

- **Chạy lâu.** Mẫu chạy nhiều tháng chưa tắt là mẫu họ còn giữ chạy (dữ liệu không xác nhận tiền đã tiêu). Nhưng bài thương hiệu (ký kết, giải thưởng, hoạt động cộng đồng) cũng hay được để chạy nền rất lâu: **đọc chữ mẫu** — chữ có giới thiệu sản phẩm, công dụng, giá, ưu đãi hay lời mời mua thì mới gọi là mẫu bán hàng chạy lâu. Đừng dựa vào nút bấm: ở lượt thử, bài về lễ ký kết vẫn gắn nút nhắn tin còn mẫu «mua 1 tặng 1» lại không có nút.
- **Nhiều bản cùng nhóm** (`collation_count` lớn hơn 1): họ đang chạy nhiều bản gần giống nhau. Mẫu vừa bật vài giờ cũng có thể có nhiều bản — tự nó không nói mẫu đã chạy tốt.
- **Hiện ở nhiều nơi** (`publisher_platform`). Danh sách này bị cắt còn 3 mục đầu, và mẫu mới bật cũng thường hiện ở nhiều nơi: dấu hiệu yếu nhất trong ba.

**Thứ tự trong danh sách không phải dấu hiệu.** Đó là thứ tự mặc định nguồn trả về, không phải xếp hạng hiệu quả đã kiểm chứng (ở lượt thử, mẫu đứng đầu là một bài về lễ ký kết). Đừng nói với người dùng rằng danh sách xếp theo lượt hiển thị, đừng gọi mẫu đứng đầu là mẫu nhiều lượt xem nhất.

Từ «win», «hiệu quả», «ra đơn» chỉ dùng khi nhắc lại câu hỏi của người dùng; trong câu trả lời viết «mẫu được giữ chạy lâu», «mẫu có nhiều bản cùng chạy».

## Một mẫu cụ thể

Người dùng đưa link hoặc mã một mẫu trong thư viện quảng cáo Facebook, hoặc muốn xem kỹ một mẫu ở bước 2:

| Cần gì | Công cụ | Tham số |
|---|---|---|
| Mẫu này của trang nào, chạy từ ngày nào, còn chạy không, chữ và video của mẫu | «Thông tin mẫu quảng cáo trên Facebook» (`hgrz7wcp`, ~10 token) | `url` = link mẫu, hoặc `id` = dãy số sau «id=» trong link; `trim` = true |
| Lời nói trong video của mẫu | «Chép lời video quảng cáo Facebook» (`hg7u34ms`, ~10 token) | `id` hoặc `url` như trên |

Kết quả chi tiết một mẫu dùng tên trường viết liền kiểu khác (ngày bắt đầu, ngày ghi nhận gần nhất, còn chạy hay không, mã trang, tên trang): đọc theo nghĩa, cách tính số ngày như bảng trên; chữ của mẫu nằm thẳng ở `snapshot` → `body`, video ở `snapshot` → `videos`. Mẫu đã tắt thì ngày cuối là ngày dừng, không phải ngày lấy dữ liệu. Tiền tiêu và số người tiếp cận ở đây cũng trống.

**Chép lời video:** `transcript_available` = false nghĩa là nguồn không chép được lời video này — nói đúng vậy, đừng nói «video không có lời». Hai lượt thử với video quảng cáo tiếng Việt đều không chép được (mới hai lượt, chưa đủ để nói thành quy luật): **đừng tự đề nghị chép lời**; người dùng yêu cầu thì thử, và nói trước là có thể không ra. Số token đã trừ xem trong kết quả.

## Quảng cáo Google

Kỹ năng này tìm theo **tên miền** của đối thủ (chưa thử tìm theo tên thương hiệu hay từ khoá ngành).

```
chay_cong_cu(ma="hgcloe4t", tham_so={"domain": "<tên miền>", "region": "VN"}, nguon=1)
```

`nguon` = 1 đặt **ngang hàng với `tham_so`**, không nằm trong `tham_so`. Gọi đúng như vậy thì lượt này tính theo mức thấp của khoảng giá và theo luật tiền chung. Lượt lỗi thì dừng và báo; **không gọi lại mà bỏ `nguon`**. Xem chi tiết từng mẫu là lượt thêm: nêu giá, chờ đồng ý.

| Cần gì | Công cụ | Tham số |
|---|---|---|
| Các mẫu tên miền này đang chạy trên Google | «Quảng cáo Google của đối thủ» (`hgcloe4t`, ~3–10 token hoặc ~130 token/kết quả) | `domain` = tên miền, `region` = «VN» |
| Chữ của một mẫu (tiêu đề, mô tả, trang đích) | «Chi tiết mẫu Google Ads theo link» (`hgxx5j4m`, ~10 token) | `url` = `adUrl` của mẫu đó |

- Bỏ `nguon` thì khi nguồn 1 lỗi tạm, cửa có thể đổi sang nguồn tính **theo từng kết quả** — 40 mẫu là rất nhiều token. **Không điền `get_ad_details`**: bật là lượt chạy đắt gấp nhiều lần; muốn đọc chữ thì xem chi tiết từng mẫu.
- Mẫu nằm trong `ads` (mỗi lượt tối đa 40); `number_of_ads_estimate` là số mẫu **ước** của nhà quảng cáo này — nói «khoảng», và nói đã xem bao nhiêu.
- Mỗi mẫu: `format` («text» = mẫu dạng chữ · «image» = ảnh · «video» = video; không cho biết mẫu hiện ở đâu), `firstShown` và `lastShown` (ngày hiện lần đầu và lần gần nhất, **tính chung mọi nước**, không tách riêng Việt Nam), `adUrl`. `firstShown` ở danh sách và ở chi tiết của cùng một mẫu có thể lệch nhau (lượt thử lệch 10 ngày): nêu ngày nào thì nói lấy từ đâu, viết «khoảng». **Không lấy hai ngày này trừ nhau để nói «mẫu đã chạy … ngày ở Việt Nam»**: không biết ngày bắt đầu riêng ở Việt Nam, không biết mẫu có ngắt quãng không — chỉ nêu ngày hiện lần đầu và lần gần nhất. Danh sách **không có chữ của mẫu**; muốn đọc chữ phải xem chi tiết từng mẫu (lượt thêm).
- Chi tiết một mẫu: `variations` là các bản chữ của mẫu (`headline`, `description`; `headline` trống hoặc bị cắt thì đọc `allText`, trang đích ở `destinationUrl`). Số lượt hiển thị trong `overallImpressions` và `regionStats` ở lượt thử **chỉ có số ở hai nước châu Âu; dòng Việt Nam để trống** — không dùng hai trường này để nói về lượt hiển thị ở Việt Nam, kể cả con số tổng.
- `ads` rỗng = lần này không thấy mẫu nào cho tên miền đó; đừng kết luận «không chạy Google Ads».

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

Bố cục cho câu hỏi thường gặp nhất (mẫu Facebook đang chạy của một trang). Người dùng hỏi **mẫu mới bật** thì câu mở và bảng xếp mẫu mới nhất trước. Hỏi **một mẫu cụ thể** hoặc **quảng cáo Google** thì giữ dòng đầu (nêu mẫu hoặc tên miền đã tra thay cho tên trang), câu mở, dòng lưu ý, việc nên làm tiếp; phần giữa kể theo đúng các trường công cụ đó có (Google không có nút bấm, danh sách Google không có chữ của mẫu).

1. **Dòng đầu** như mục «Trước khi chạy»: đã xem trang nào (tên, số người thích, link) · dữ liệu từ thư viện quảng cáo công khai của Facebook, mẫu đang chạy ở Việt Nam · tốn bao nhiêu token.
2. **Câu mở** — trả lời thẳng: trang đang chạy bao nhiêu mẫu, bao nhiêu mẫu trong đó đã chạy từ mốc (3 tháng) trở lên, bạn xem được bao nhiêu; mẫu chạy lâu nhất trong số đã xem là mẫu gì, khoảng bao nhiêu ngày. Mẫu lâu nhất là bài thương hiệu thì nói rõ vậy và nêu kèm **mẫu bán hàng** chạy lâu nhất. Người dùng hỏi «mẫu nào win» thì câu mở nói ngay: không có số đo hiệu quả, dưới đây là mẫu được giữ chạy lâu nhất.
3. **Bảng mẫu** — tối đa 6 mẫu trong số đã xem, **xếp theo số ngày đã chạy, lâu nhất trước**. Cột: mẫu nói gì (tóm ý) · chạy từ · khoảng bao nhiêu ngày · dạng · nút bấm · link. Mẫu nào là bài thương hiệu, không chào hàng, thì ghi rõ ở cột đầu.
4. **Nhìn chung** — tối đa ba câu, chỉ đếm trên số mẫu đã xem: đếm theo từng dạng (một ảnh, nhiều ảnh, video); nút bấm nào nhiều nhất; bao nhiêu mẫu chào hàng, bao nhiêu bài thương hiệu. Nhận định ghi rõ là của bạn. Không nhắc lại số đã nêu ở câu mở.
5. **Dòng lưu ý cuối** — **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Thường là: thư viện không công bố tiền tiêu, lượt hiển thị, số đơn nên chạy lâu chỉ cho biết mẫu còn được giữ chạy · ngày tính theo ngày thư viện ghi · thứ tự danh sách không phải xếp hạng hiệu quả.
6. **Việc nên làm tiếp** — một câu. Chỉ khuyên **xem thêm hoặc thử nhỏ** (mở link mẫu chạy lâu nhất xem ảnh, video; xem mẫu mới bật — nêu giá; lọc hẹp hơn các mẫu chạy lâu, ví dụ từ 6 tháng — nêu giá). Đừng khuyên «làm theo mẫu này», «chạy mẫu này» như thể nó đã ra đơn.
