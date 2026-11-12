---
name: tu-khoa-google
description: Tìm và so từ khoá để chạy quảng cáo Google (Google Ads) ở Việt Nam — mỗi từ khoá được tìm khoảng bao nhiêu lượt mỗi tháng, đang lên hay xuống, mức cạnh tranh giữa các nhà quảng cáo, khung giá thầu một lượt bấm (khi mở rộng từ một cụm gốc còn có nhãn người tìm muốn mua hay muốn tìm hiểu) — bằng hai công cụ «Từ khoá Google mở rộng từ cụm gốc» và «Lịch sử lượt tìm và giá thầu Google» của HG Trend. Dùng khi người dùng (agency, người chạy ads, chủ shop) hỏi «từ khoá nào nên chạy Google Ads cho [sản phẩm]», «nghiên cứu từ khoá», «lên bộ từ khoá», «từ này bao nhiêu lượt tìm», «giá thầu từ khoá này», «CPC bao nhiêu», «mở rộng từ khoá từ [cụm gốc]»; và MỌI câu hỏi về dự tính Google Ads như «chạy Google Ads 5 triệu thì ra bao nhiêu đơn», «ngân sách Google Ads bao nhiêu là đủ», «một lượt bấm giá bao nhiêu» — đừng tự ước bằng con số chung chung: HG Trend không dự báo được số đơn, kỹ năng nói rõ trả lời thế nào và có số thật nào để dùng.
---
# Từ khoá chạy Google Ads

Người dùng sắp chạy hoặc đang chạy quảng cáo tìm kiếm trên Google và cần chọn từ khoá. Hai công cụ dưới đây trả số liệu **của Google Ads cho thị trường Việt Nam**: lượt tìm trung bình mỗi tháng, mức cạnh tranh, khung giá thầu. Đây là số Google công bố cho nhà quảng cáo, đã làm tròn theo bậc và chậm khoảng một đến hai tháng — dùng để **so các từ với nhau**, không phải để dự báo số lượt bấm hay số đơn.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Có một sản phẩm, một cụm gốc; cần tìm các từ khoá quanh nó | «Từ khoá Google mở rộng từ cụm gốc» (`hg54wjlo`) |
| Đã có sẵn danh sách từ khoá; cần lượt tìm, giá thầu từng từ | «Lịch sử lượt tìm và giá thầu Google» (`hgq724ed`) — một lượt cho cả danh sách (tối đa 30 từ mỗi lượt). **Đừng dùng** «Lượt tìm, giá thầu từ khoá Google» (`hglcx7nm`, ~470 token): tên gần giống nhưng đắt gấp nhiều lần và kỹ năng này chưa thử |
| Vừa muốn mở rộng vừa có sẵn vài từ | Chạy `hg54wjlo` cho cụm gốc trước. Từ nào của họ đã nằm trong kết quả thì không cần chạy thêm; còn thiếu mới chạy `hgq724ed` cho các từ thiếu (lượt thêm, hỏi trước) |
| **Chỉ** hỏi «chạy bao nhiêu tiền thì ra bao nhiêu đơn», «ngân sách bao nhiêu là đủ» | **Không chạy.** Nói HG Trend không có tỉ lệ ra đơn nên **không dự báo được số đơn**, và kỹ năng này chưa có số lượt bấm đã kiểm chứng cho Việt Nam; hỏi họ có muốn xem lượt tìm và khung giá thầu của các từ khoá không |
| Dự báo lượt bấm, lượt hiển thị theo một mức giá thầu | Có công cụ «Dự báo lượt truy cập từ Google Ads» (`hgik34p6`, ~470 token) nhưng kỹ năng này **chưa thử** nó cho Việt Nam: nói vậy, nêu giá, chờ đồng ý, `xem_cong_cu` trước khi chạy |
| Đối thủ đang mua từ khoá nào (theo tên miền) | «Từ khoá Google Ads theo tên miền» (`hgdn2jls`, ~470 token) trả các từ khoá Google gợi ý cho một trang web — **không phải** danh sách từ đối thủ đang mua. Chưa thử cho Việt Nam: nêu giá, chờ đồng ý, `xem_cong_cu` trước khi chạy |
| Món này có ai tìm, ai bán chưa (để quyết định bán hay không) | Kỹ năng xem-mon-dinh-ban (báo cáo `hgxemmon`), không phải kỹ năng này |
| Từ khoá cho TikTok, YouTube, Shopee | Không thuộc kỹ năng này. Shopee, Lazada, Tiki, Sendo, Zalo: HG Trend chưa có. TikTok, YouTube: `tim_cong_cu` |
| Nước khác, tiếng khác | Hỏi lại nước và tiếng; `xem_cong_cu` để biết cách điền mã nước. Kỹ năng này mới thử cho Việt Nam, tiếng Việt |

## Trước khi chạy

- `location_code` = 2704 (Việt Nam) và `language_code` = «vi». Luôn điền cả hai.
- Giữ đúng cách viết người dùng đưa. Từ không dấu mà hiểu được hơn một nghĩa, hoặc nghi là tên riêng, thì hỏi lại trước khi chạy.
- `hg54wjlo`: `keyword` = MỘT cụm gốc (ví dụ «kem chống nắng»); `limit` = 20 (lấy 20 từ nhiều lượt tìm nhất; lấy nhiều hơn thì kết quả dài, dễ bị cắt). Người dùng đưa cụm dài, cụ thể («kem chống nắng cho bà bầu») thì giữ nguyên — đừng tự rút ngắn; cụm càng dài càng ít kết quả. Công cụ này **chỉ trả các từ có chứa đúng cụm gốc**: nhập «kem chống nắng» sẽ không ra «xịt chống nắng».
- `hgq724ed`: `keywords` = danh sách từ khoá, mỗi từ không quá 10 chữ và 80 ký tự. Nguồn nhận được rất nhiều từ một lượt, nhưng kết quả dài sẽ bị cắt: kỹ năng này **gửi tối đa 30 từ mỗi lượt** để đọc được đủ; người dùng đưa nhiều hơn thì nói sẽ chia mấy lượt, tổng token bao nhiêu, và chờ đồng ý. Mới thử với 3 từ — nhiều từ hơn giá có thể nhích lên.

Giá: `hg54wjlo` — lượt thật trừ **75 token khi lấy 20 từ, 82 token khi lấy 30 từ** (cao hơn mức ghi trong kho, ~63 token); khi báo giá hay cộng trước, tính mỗi lượt 85 token · `hgq724ed` ~63 token (lượt thật với 3 từ trừ 65 token — khi cộng trước tính 70 token mỗi lượt). **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token; đừng tự đổi ra đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ trừ token theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

Mỗi cụm gốc là một lượt. Người dùng đưa nhiều sản phẩm: cộng token mọi lượt trước khi chạy.

## Chạy

```
chay_cong_cu(ma="hg54wjlo", tham_so={"keyword": "kem chống nắng", "location_code": 2704, "language_code": "vi", "limit": 20}, cat_ky_tu=45000)
chay_cong_cu(ma="hgq724ed", tham_so={"keywords": ["kem chống nắng", "sữa rửa mặt", "nước tẩy trang"], "location_code": 2704, "language_code": "vi"}, cat_ky_tu=45000)
```

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

Dữ liệu thô tiếng Anh. Các từ khoá nằm trong `items`; số liệu của mỗi từ nằm trong `keyword_info`.

**Riêng `hgq724ed`:** mỗi từ có `history`, mỗi mục là một khối `keyword_info` chụp ở một tháng, mới nhất đứng đầu; kết quả chỉ giữ 3 khối. **Đọc số hiện tại ở khối đầu.** `search_volume` trong từng khối vẫn là số **trung bình năm** tính tại tháng đó — không phải lượt tìm của riêng tháng đó; lượt tìm từng tháng nằm ở `monthly_searches` (cũng chỉ còn 3 tháng). Ba khối chỉ dùng để xem `cpc` và khung giá thầu đổi ra sao qua 3 tháng. Chỉ thấy vài tháng gần nhất nên **không kết luận mùa vụ cả năm** từ công cụ này. Danh sách trả về **không xếp theo lượt tìm** — tự so từng từ. `rut_gon` của công cụ này luôn báo «danh sách con giữ 3 mục đầu»: đó là cắt số tháng, không phải cắt bớt từ khoá.

| Trường | Là gì | Lưu ý |
|---|---|---|
| `search_volume` | Lượt tìm **trung bình mỗi tháng** trên Google ở Việt Nam (ở `hg54wjlo` thấy rõ là trung bình của 12 tháng trong `monthly_searches`) | Google làm tròn theo bậc (ví dụ 40.500 · 49.500 · 60.500): viết «khoảng». Hai từ cùng bậc là **ngang nhau**, không phải bằng nhau từng lượt. Đây là lượt tìm, không phải số người, không phải lượt bấm quảng cáo |
| `monthly_searches` | Lượt tìm từng tháng (tối đa 12 tháng ở `hg54wjlo`) | Dùng để nói mùa vụ: tháng nào cao, tháng nào thấp. Tháng mới nhất thường là **hai tháng trước** — nêu rõ số liệu tới tháng nào |
| `search_volume_trend` | Phần trăm thay đổi: `monthly` so tháng trước, `quarterly` so quý trước, `yearly` so cùng kỳ năm trước | Số âm là giảm. Vì lượt tìm làm tròn theo bậc, thay đổi một bậc đã ra ±18 % đến ±33 %: chỉ gọi là «đang lên / đang xuống» khi `quarterly` và `yearly` cùng chiều |
| `cpc` | Giá trung bình một lượt bấm mà nhà quảng cáo đã trả cho từ này, **tính bằng đô la Mỹ** | Giữ đơn vị đô la Mỹ, đừng tự đổi ra đồng. Viết «khoảng 0,09 đô la Mỹ một lượt bấm» |
| `low_top_of_page_bid`, `high_top_of_page_bid` | Khung giá thầu để lên đầu trang: mức thấp và mức cao, đô la Mỹ một lượt bấm | Là khung Google ước, không phải giá chắc chắn phải trả. Nêu cả hai đầu |
| `competition_level` | Mức cạnh tranh **giữa các nhà quảng cáo** mua từ này: «HIGH» = cao · «MEDIUM» = vừa · «LOW» = thấp | Không phải độ khó lên top tự nhiên (SEO). Ở lượt thử, gần như mọi từ quanh một mặt hàng phổ biến đều «HIGH» — khi cả danh sách cùng một mức thì mức này không giúp chọn, nói vậy |
| `main_intent` (trong `search_intent_info`, **chỉ có ở `hg54wjlo`** — chạy `hgq724ed` thì không có, đừng tự gắn nhãn) | Người tìm muốn gì: «transactional» = muốn mua · «commercial» = đang so sánh trước khi mua · «informational» = tìm hiểu · «navigational» = tìm một trang cụ thể | Là máy phân loại, có thể sai: hai cách viết của cùng một từ có khi ra hai nhãn khác nhau |
| `total_count`, `items_count` (nằm ngoài `items`; `total_count` chỉ có ở `hg54wjlo`) | Tổng số từ khoá tìm được quanh cụm gốc và số từ trả về lượt này | «Có khoảng 17.000 từ quanh cụm này, tôi lấy 20 từ nhiều lượt tìm nhất». Kết quả có `rut_gon` báo bị cắt thì số từ đã xem là số mục thật có trong `items` |
| `keyword_difficulty` (trong `keyword_properties`) | Độ khó lên top tự nhiên | Bằng 0 ở mọi từ trong lượt thử: **đừng dùng, đừng nhắc** |
| `last_updated_time` **trong `keyword_info`** | Lúc nguồn cập nhật số của từ đó | Thường cách lúc chạy vài tuần — nêu ở dòng lưu ý cuối. Đừng lấy trường cùng tên trong `search_intent_info` (cũ hơn nhiều) |

Những điều dễ sai:

- **Cách viết gần giống nhau** («kem chống nắng hàn quốc» và «kem chống nắng han quoc», «l'oreal» và «loreal») thường ra cùng một con số vì Google gộp chúng: **không cộng** lượt tìm của các cách viết này, chỉ kể một dòng (lấy cách viết đúng chính tả; hai cách viết lệch nhãn «muốn gì» thì ghi cả hai nhãn).
- **Từ có tên thương hiệu khác** (ví dụ «kem chống nắng anessa» khi người dùng không bán Anessa): tách thành nhóm riêng, đừng trộn với từ chung — **không bỏ** chúng như «mục lạc loại»; chỉ bỏ từ sai hẳn mặt hàng. Chạy quảng cáo bằng tên thương hiệu của người khác có thể vướng chính sách — chỉ nhắc một câu, không phán.
- Ở `hg54wjlo`, danh sách ở các lượt thử xếp theo lượt tìm, nhiều trước (không điền gì thêm). Từ nhiều lượt tìm nhất thường là từ chung, giá thầu không hẳn cao nhất: so bằng cả lượt tìm lẫn khung giá thầu.
- Ở lượt thử với một mặt hàng phổ biến, hơn nửa số từ đầu danh sách là từ kèm tên các hãng lớn. Còn quá ít từ sát với món người dùng bán thì **nói thẳng vậy** và đề nghị chạy thêm một cụm gốc cụ thể hơn (nêu giá) — đừng gượng khuyên trên vài từ.
- Không có: tỉ lệ bấm, tỉ lệ ra đơn, số nhà quảng cáo đang mua, đối thủ nào đang mua từ nào. Không nhân lượt tìm với một tỉ lệ tự nghĩ để ra «số lượt bấm» hay «ngân sách».

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

**Riêng kỹ năng này:** con số ở đây là **lượt tìm trung bình mỗi tháng do Google Ads công bố** — gọi đúng là «lượt tìm». Quy tắc «mức quan tâm trên Google» ở trên chỉ áp cho điểm 0–100 của các báo cáo khác, không áp ở đây. Tên trường tiếng Anh không đưa vào câu trả lời.

Bố cục:

1. **Dòng đầu** như mục «Trước khi chạy»: đã chạy cho cụm nào · số liệu Google Ads cho Việt Nam · tốn bao nhiêu token.
2. **Câu mở** — trả lời thẳng: quanh cụm này từ nào được tìm nhiều nhất (khoảng bao nhiêu lượt mỗi tháng) và khung giá thầu chung của nhóm. Người dùng hỏi «nên chạy từ nào» thì nói luôn bạn nghiêng về nhóm từ nào, mở bằng «Theo tôi».
3. **Bảng từ khoá** — tối đa 12 dòng, đã gộp các cách viết trùng: từ khoá · lượt tìm mỗi tháng (khoảng) · giá trung bình một lượt bấm và khung giá thầu (đô la Mỹ) · người tìm muốn gì (**chỉ khi chạy `hg54wjlo`**; chạy `hgq724ed` thì bỏ cột này). Chia hai nhóm khi có: **từ chung** và **từ kèm tên thương hiệu**.
4. **Nhận định của bạn** — hai ba câu: nhóm nào đáng thử trước và vì con số nào (ví dụ từ dài hơn, lượt tìm vừa phải, người tìm muốn mua, giá thầu thấp hơn từ chung); từ nào đang xuống theo mùa (chỉ nói mùa vụ khi có đủ 12 tháng). Chỉ khuyên **thử nhỏ rồi đo**; không viết «sẽ ra đơn», «chắc chắn hiệu quả».
5. **Dòng lưu ý cuối** — **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Thường là: lượt tìm là trung bình năm, làm tròn theo bậc, số liệu tới tháng nào và nguồn cập nhật lúc nào (đó là giờ nguồn cập nhật số, không phải giờ chạy — kết quả không ghi giờ chạy) · công cụ mở rộng chỉ tìm từ có chứa cụm gốc · giá thầu là khung Google ước, tính bằng đô la Mỹ · không có tỉ lệ bấm và tỉ lệ ra đơn nên chưa dự báo được ngân sách.
6. **Việc nên làm tiếp** — một câu; cần chạy thêm (cụm gốc khác, danh sách từ còn thiếu) thì nêu giá và chờ đồng ý.
