---
name: tu-khoa-google
description: Xem một nhóm từ khoá trên Google ở Việt Nam — mức quan tâm 12 tháng lên hay xuống và so giữa các từ, Google gợi ý những cụm nào khi người ta gõ từ đó, trang nào đang đứng đầu kết quả tìm, phần tóm tắt AI của Google nhắc thương hiệu, trang nào — bằng «Độ hot của từ khoá trên Google», «Tìm từ khoá liên quan trên Google», «Kết quả tìm kiếm Google» và «Tóm tắt AI đầu trang tìm kiếm Google» của HG Trend. Dùng khi người làm marketing, SEO, chạy quảng cáo, chủ shop hỏi «từ khoá này còn ai quan tâm không», «so hai từ khoá», «người ta hay gõ kèm gì», «ai đang đứng top Google cho từ này», «Google AI đang giới thiệu thương hiệu nào», «lên ý tưởng bài viết theo từ khoá». Dùng cả khi họ hỏi lượt tìm mỗi tháng, giá thầu, CPC, «chạy Google Ads bao nhiêu tiền ra bao nhiêu đơn» — HG Trend không có các số đó, kỹ năng nói rõ trả lời thế nào.
---
# Từ khoá trên Google

Người dùng có một hay vài từ khoá và muốn biết chúng đứng ở đâu trên Google ở Việt Nam. HG Trend trả bốn loại số liệu, mỗi loại trả lời một câu khác nhau:

- **Mức quan tâm theo thời gian** (`hgzpswyb`) — điểm 0–100 từng tuần trong 12 tháng, so được giữa tối đa 5 từ.
- **Cụm Google gợi ý** (`hgtmknuf`) — khoảng 10 cụm Google tự hiện khi gõ từ đó.
- **Trang đứng đầu kết quả tìm** (`hgnti2tw`) — 10 kết quả tự nhiên ở trang đầu (không gồm quảng cáo).
- **Tóm tắt AI của Google** (`hg4fieva`; chế độ AI `hgr76dfb`) — đoạn AI của Google viết ở đầu trang và các trang nó dẫn nguồn.

**HG Trend không có lượt tìm mỗi tháng, giá một lượt bấm (CPC), giá thầu, mức cạnh tranh quảng cáo của từ khoá.** Đó là số trong Google Ads (Keyword Planner) — người dùng xem bằng tài khoản của họ.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

Trong kết quả có `credits_charged`, `credits_remaining`: đó là số của nguồn, **không phải token của người dùng** — đừng nhắc tới.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| «Từ này còn ai quan tâm không», «đang lên hay xuống», «so hai từ» | Mức quan tâm (`hgzpswyb`), gửi tối đa 5 từ một lượt |
| «Người ta hay gõ kèm gì», «tìm thêm từ khoá quanh …», «ý tưởng bài viết» | Cụm Google gợi ý (`hgtmknuf`) |
| «Ai đang đứng top Google cho từ này» | Kết quả tìm (`hgnti2tw`) |
| «Google AI giới thiệu thương hiệu nào», «nhãn của tôi có được AI của Google nhắc không» | Tóm tắt AI (`hg4fieva`); không có tóm tắt thì thử chế độ AI (`hgr76dfb`) — lượt thêm, nêu giá |
| «Nghiên cứu từ khoá cho …» chung chung | Lượt đầu: cụm gợi ý cho từ gốc + mức quan tâm cho từ gốc và tối đa 4 cụm gợi ý (hai lượt, khoảng 82 token ở lượt thử). Kết quả tìm, tóm tắt AI để ở «việc nên làm tiếp» |
| **Chỉ** hỏi lượt tìm mỗi tháng, CPC, giá thầu, mức cạnh tranh | **Không chạy.** Nói HG Trend không có các số này, chỉ Google Ads (Keyword Planner) có; hỏi họ có muốn xem mức quan tâm và cụm gợi ý không |
| «Chạy Google Ads … triệu ra bao nhiêu đơn», «ngân sách bao nhiêu là đủ» | **Không chạy, không đưa con số nào** — kể cả «ước chừng», «kịch bản», «công thức» nhân giá bấm với tỉ lệ ra đơn tự đặt. Nói HG Trend không có giá bấm, tỉ lệ ra đơn, nên không dự báo được; cách biết là chạy thử một ngân sách nhỏ và đo |
| «Đối thủ có chạy quảng cáo Google không», mẫu quảng cáo của họ | Kỹ năng spy-quang-cao (cần tên miền của đối thủ) |
| Món này có ai tìm, ai bán chưa (để quyết bán hay không) | Kỹ năng xem-mon-dinh-ban (báo cáo `hgxemmon`, ~27–115 token) |
| Từ khoá trên TikTok, YouTube | Kỹ năng bat-trend, de-tai-youtube |
| Nước khác | `xem_cong_cu` để biết cách điền mã nước; kỹ năng này mới thử cho Việt Nam |

## Trước khi chạy

Giá ở lượt thử: mức quan tâm **78 token** mỗi lượt (tối đa 5 từ), cụm gợi ý **4 token**, kết quả tìm **10 token**, tóm tắt AI và chế độ AI **1 token**. Kho ghi khoảng giá rộng hơn (kết quả tìm ~1–78 token) vì mỗi công cụ có vài nguồn: **điền đúng tên tham số như các lệnh ở dưới**, cửa sẽ chọn nguồn đã thử. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu: với các lệnh ghi sẵn trong kỹ năng này, cộng theo **giá đã đo ở lượt thử** ghi trong kỹ năng — không theo mức cao của khoảng giá trong kho (mức cao là của nguồn khác mà các lệnh này không dùng); công cụ nào kỹ năng không ghi giá đo thì cộng theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy): đã chạy gì, cho cụm / kênh / link / từ nào (kèm từ đã dịch nếu có) · dữ liệu lấy từ đâu · lượt này tốn bao nhiêu — số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token và nói là ước. Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi tự chạy thêm lượt (cụm khác, kênh khác, video khác), khi thiếu thông tin bắt buộc, khi tổng vượt ngưỡng. Họ **chỉ** hỏi thứ dữ liệu không có thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

Từ khoá gửi **đúng chữ người dùng gõ** (có dấu tiếng Việt). Họ đưa hơn 5 từ để so: hỏi họ chọn 5, hoặc chia lượt (nêu giá) — các lượt khác nhau **không so điểm với nhau được** (mỗi lượt Google chấm một thang riêng).

## Chạy

```
chay_cong_cu(ma="hgzpswyb", tham_so={"q": "<từ 1>,<từ 2>,<từ 3>", "geo": "VN"})
chay_cong_cu(ma="hgtmknuf", tham_so={"query": "<từ gốc>", "gl": "vn", "hl": "vi"})
chay_cong_cu(ma="hgnti2tw", tham_so={"query": "<từ khoá>", "region": "VN"})
chay_cong_cu(ma="hg4fieva", tham_so={"q": "<câu tìm>", "gl": "vn", "hl": "vi"})
chay_cong_cu(ma="hgr76dfb", tham_so={"q": "<câu tìm>", "gl": "vn", "hl": "vi"})
```

- Mức quan tâm: nhiều từ thì **nối bằng dấu phẩy trong một chuỗi**, không gửi danh sách.
- Tóm tắt AI chỉ hiện với câu tìm kiểu hỏi («kem chống nắng nào tốt», «cách chọn …»); từ khoá trơn hay không có.

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

| Công cụ | Đọc gì | Lưu ý |
|---|---|---|
| Mức quan tâm (`hgzpswyb`) | `interest_over_time` → `timeline_data`: mỗi tuần một mục, `date` + `values` (mỗi từ: `query`, `extracted_value`); `averages`: điểm trung bình 12 tháng của từng từ (`query`, `value`) | Thang 0–100 **chung cho các từ trong lượt**: 100 là tuần cao nhất của từ cao nhất. Gọi là «mức quan tâm trên Google», **không phải lượt tìm**. Lên / xuống: so trung bình 4 tuần cuối với `averages` của chính từ đó, nói bằng so sánh («4 tuần gần đây cao hơn mức trung bình năm khoảng một phần ba, điểm 88 so với 66»). Tuần cuối thường chưa trọn tuần: đừng kết luận từ riêng tuần cuối. Từ điểm dưới chừng 10: lên xuống kém chắc — nêu kèm điểm |
| Cụm gợi ý (`hgtmknuf`) | `data` → `suggestions` → `value` | Là cụm Google tự hiện khi gõ, **không kèm lượt tìm**, không xếp theo độ phổ biến. Ở lượt thử: «kem chống nắng» ra 10 cụm, phần lớn là tên nhãn |
| Kết quả tìm (`hgnti2tw`) | `results`: `title`, `url`, `description` | 10 kết quả tự nhiên trang đầu, theo thứ tự Google xếp lúc chạy; **không có quảng cáo**, không có số lượt bấm. Kết quả Google đổi theo nơi, giờ, người tìm: nói «lúc chạy» |
| Tóm tắt AI (`hg4fieva`) | `ai_overview` → `text_blocks` (`type`: heading / paragraph / list; `snippet`; `list`), `references` (`title`, `link`, `source`) | Không có `ai_overview` = Google không hiện tóm tắt cho câu này lúc chạy. Nói thương hiệu nào được nhắc, trang nào được dẫn (`source`). Đây là chữ **AI của Google tự viết**, không bảo đảm đúng: không trình bày như dữ kiện đã kiểm |
| Chế độ AI (`hgr76dfb`) | `text_blocks`, `references` như trên | Như trên |

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

Riêng với kỹ năng này: không viết «lượt tìm», «số người tìm», «lưu lượng»; không ước số lượt bấm, số đơn, tiền quảng cáo từ bất kỳ số nào ở đây. Gợi ý từ nên nhắm thì nói «theo tôi» và chỉ ra con số đỡ cho nó (mức quan tâm cao, đang lên, Google gợi ý, chưa có trang nào trả lời đúng ý ở trang đầu).

Bố cục:

1. **Dòng đầu** — đã chạy gì cho từ nào · dữ liệu Google ở Việt Nam lúc chạy · tổng token đã trừ (không ghi thì giá ước, nói là ước). Họ có hỏi lượt tìm, CPC thì nói ngay ở đây là HG Trend không có.
2. **Câu mở** — trả lời thẳng câu họ hỏi, kèm một hai con số.
3. **Số liệu** — mỗi công cụ một đoạn ngắn hoặc một bảng (từ 3 mục trở lên).
4. **Theo tôi** — một hai từ nên nhắm hoặc nên viết bài, vì sao.
5. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Với kỹ năng này thường là: điểm là mức quan tâm so giữa các từ trong lượt, không phải lượt tìm · kết quả tìm và tóm tắt AI là lúc chạy, đổi theo nơi và giờ · không có lượt tìm, CPC.
6. **Việc nên làm tiếp** — một câu: thường là xem trang đứng đầu, tóm tắt AI cho từ đáng nhắm nhất (nêu giá); lượt tìm, giá thầu thì xem trong Google Ads của họ.
