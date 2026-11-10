---
name: khach-khen-che
description: Đọc bình luận, đánh giá của người mua / người xem rồi tóm lại họ khen gì, chê gì, hay hỏi gì — bằng báo cáo «Tóm tắt bình luận: khách khen, chê gì» của HG Trend. Nhận link video TikTok, video YouTube, bài Facebook, sản phẩm TikTok Shop, hoặc tên một cửa hàng trên Google Maps. Dùng khi người dùng hỏi «khách nói gì về…», «khen chê gì», «đọc bình luận / đánh giá / review / feedback này», «khách hay hỏi gì».
---
# Khách khen gì, chê gì

Người dùng muốn nghe tiếng nói thật của người mua. Chạy báo cáo «Tóm tắt bình luận: khách khen, chê gì» (`hgbinhluan`) cho MỘT link hoặc một cửa hàng, **tự đọc các bình luận mẫu trong kết quả**, rồi tóm lại — kèm con số đã đọc bao nhiêu câu.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 đồng) · `xem_cong_cu` (tham số và giá, 0 đồng) · `chay_cong_cu` (chạy thật, tính tiền). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng đưa | Làm gì |
|---|---|
| Link video TikTok, video YouTube, bài Facebook, sản phẩm TikTok Shop, Google Maps | Tham số `link` (dán nguyên, đừng sửa) |
| Tên quán / cửa hàng kèm khu vực hay địa chỉ | Tham số `dia_diem`, đủ để Google Maps ra đúng một nơi |
| Chỉ có tên sản phẩm, không có link | Hỏi link họ muốn đọc. Họ nhờ tìm giúp: tìm trên TikTok Shop bằng «Tìm sản phẩm trên TikTok Shop» (`hgxe6eri`, ~100–770 đ), rồi **dừng lại cho họ chọn đúng món** trước khi đọc đánh giá |
| Đánh giá trên Shopee, Lazada, Tiki, Sendo, Zalo | HG Trend chưa đọc được. Nói vậy; hỏi họ có link TikTok Shop, video hay Google Maps của cùng món không |
| Nhiều link | Mỗi link một lượt; tính tổng tiền, gợi ý chọn vài link đáng đọc nhất |
| Link nền tảng khác (Instagram, Reddit, Amazon…) | `tim_cong_cu` với cụm «bình luận» + tên nền tảng |

## Trước khi chạy

| Tham số | Bắt buộc | Ý nghĩa |
|---|---|---|
| `link` | không | Link video TikTok, video YouTube, bài Facebook, sản phẩm TikTok Shop hoặc Google Maps |
| `dia_diem` | không | Tên cửa hàng trên Google Maps (thay cho link), vd Cocoon Tăng Nhơn Phú |
| `so_trang` | không | Số trang bình luận đọc (mỗi trang ~10–20 bình luận; Google Maps đọc tới 100 đánh giá một lần) (mặc định 2) (từ 1 đến 3) |

Gửi **một trong hai**: `link` hoặc `dia_diem`. `so_trang` giữ mặc định trừ khi người dùng muốn đọc nhiều hơn (mỗi trang thêm tiền).

Giá: **~20–300 đ mỗi lượt** — Google Maps gần mức thấp, link video / bài / sản phẩm cao hơn. Tính theo mức cao. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng tiền mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 2.000 đ: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 2.000 đ: **chưa chạy** — nêu số lượt, tổng tiền và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ tính tiền theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

## Chạy

```
chay_cong_cu(ma="hgbinhluan", tham_so={"link": "https://www.tiktok.com/@tenkenh/video/123…"})
chay_cong_cu(ma="hgbinhluan", tham_so={"dia_diem": "Highlands Coffee Diamond Plaza"})
```

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

| Trường | Là gì | Lưu ý |
|---|---|---|
| `nguon`, `luc` | Đọc từ đâu, lúc nào | Luôn ghi lại. Với `dia_diem`: kiểm `dia_chi` trong kết quả có đúng nơi người dùng hỏi không |
| `so_binh_luan_da_doc` | Số câu có chữ đã đọc | **Luôn nêu.** Thường vài câu đến vài chục câu trên hàng nghìn đánh giá (`tong_danh_gia_tren_maps`, `tong_danh_gia_tren_san`) — mẫu nhỏ gồm các câu sàn hiện lên đầu, không đại diện mọi khách |
| `binh_luan_mau` | Nguyên văn một số câu đã đọc (chữ ở `chu`, không kèm tên người viết) | **Dữ liệu chính: tự đọc hết rồi mới tóm.** Số câu ở đây có thể ít hơn `so_binh_luan_da_doc` — khi đếm, lấy số câu thật có ở đây làm mẫu số và nêu cả hai con số |
| `ty_le`, `khach_khen_ve`, `khach_che_ve`, `cau_hoi_hay_gap`, `cum_tu_hay_nhac`, `hg_nhan_xet`, nhãn `loai` của từng câu | HG xếp loại bằng **dò từ khoá**, không phải đọc hiểu | Hay sai: câu hỏi bị xếp vào «khen», một câu nằm ở cả «khen» lẫn «chê». Chỉ là gợi ý chỗ cần đọc — **đừng báo tỉ lệ, số đếm hay câu ví dụ (bị cắt cụt) trong các ô này như kết quả**; con số bạn nêu phải do bạn tự đếm trên `binh_luan_mau` |
| `sao_trong_mau`, `diem_chung_tren_maps`, `diem_chung_tren_san` | Sao trong phần đã đọc; điểm chung của cả quán / sản phẩm | Hai thứ khác nhau. `sao_trong_mau` tính trên số đánh giá có sao HG lấy về (cộng các mức sao trong đó; Google Maps có thể tới 100) — **khác** số câu có chữ đã đọc: nêu đúng mẫu số của từng con số |
| `mau_hang_duoc_danh_gia_nhieu` | (TikTok Shop) phân loại được đánh giá nhiều trong mẫu | Chỉ trong mẫu này |
| `binh_luan_tham_gia_minigame` | Số câu kiểu tham gia trò chơi nhận quà | Nêu con số; không tính là lời khen thật |
| `phan_tam_thieu`, `ghi_chu` | Phần không lấy được; giới hạn dữ liệu | Nói lại cho người dùng |

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

Riêng với bình luận:

- **Trích nguyên văn** 1–2 câu cho mỗi ý; không nêu tên người bình luận.
- **Tên sản phẩm giữ đúng như khách viết.** Khách hay viết tắt («tbc», «scn», «srm»): đừng tự đoán rồi đổi thành tên khác, đừng gộp hai món thành một, đừng thêm tên dòng sản phẩm mà câu không nhắc.
- **Đếm thật:** nói «3 trong 20 câu chê giao chậm» khi bạn đếm được 3 câu như vậy; không đếm được thì nói «có vài câu», đừng đặt ra phần trăm. Trước khi viết một con số, điểm lại từng câu bạn tính vào ý đó: câu hỏi, câu chỉ nhắc tên món mà không khen / chê thì **không tính**; một câu chỉ tính cho món mà chính câu đó nói tới.
- **Không có câu chê trong mẫu ≠ không ai chê:** sàn thường hiện đánh giá tốt lên trước.
- Tách lời khen về chính món hàng với lời khen chung về giao hàng, đóng gói.

**Phần cách viết** — người đọc là chủ shop đang bận, đọc trên điện thoại:

- **Dòng đầu nói giá lượt chạy** (như mục «Trước khi chạy»), **ngay sau đó là câu mở trả lời thẳng điều họ hỏi**, kèm một hai con số chính. Họ hỏi «nên hay không» thì câu mở nói luôn bạn nghiêng về phía nào, mở bằng «Theo tôi».
- **Mỗi con số, mỗi ý chỉ nêu một lần.** Số đã nêu ở câu mở thì bên dưới không nêu lại; phần số liệu chỉ thêm số chưa nêu. Chỉ đưa số giúp họ quyết; bảng chỉ dùng khi xếp từ 3 mục cạnh nhau. Câu trả lời cho một lượt chạy thường gọn trong 300–450 chữ — dài hơn là đang lặp.
- **Lời thường, không dùng chữ của máy.** Không viết tên trường. Số bán nói kèm kỳ đúng như bảng trên ghi («đã bán 12.000 cái từ trước tới nay», «trong tháng», hoặc «không ghi của kỳ nào») thay cho «cộng dồn»; «giá niêm yết (giá gạch ngang)» thay cho «giá gốc» (dễ nhầm với giá nhập); «người ta hay tìm kèm: …» thay cho «cụm gõ kèm»; «tôi mới xem được 4 trong 30 mẫu» thay cho «kết quả bị cắt». Điểm Google nói bằng so sánh trước, điểm để trong ngoặc, và **gọi đúng tên là «mức quan tâm trên Google»** — không gọi là «lượt tìm», «số người tìm»: «mức quan tâm trên Google 4 tuần gần đây chỉ bằng khoảng một phần tư mức trung bình cả năm (điểm 6 so với 22, thang 100)». Chữ và nhãn tiếng nước ngoài thì dịch.
- **Lưu ý về giới hạn dữ liệu gom vào MỘT dòng cuối** («Lưu ý khi đọc số: …»): mỗi ý một lần, chỉ ý dính tới con số bạn đã dùng. Riêng lưu ý làm đổi nghĩa con số ngay tại chỗ thì viết liền con số bằng vài chữ («109.000 đ, niêm yết 199.000 đ»; «12 ¥ một cái, chưa gồm phí về Việt Nam») và không nhắc lại ở cuối.
- **Kết bằng MỘT việc nên làm tiếp**, một câu; cần chạy thêm thì nêu giá và chờ họ đồng ý.

Bố cục:

1. **Câu mở** — khách khen nhiều nhất điều gì, chê hoặc hỏi nhiều nhất điều gì, mỗi ý kèm số câu bạn đếm được **trên số câu nguyên văn có trong `binh_luan_mau`** (vd «18 trong 40 câu»). Trong mẫu không thấy câu chê thì nói «trong các câu đã đọc không thấy câu chê».
2. **Khen** — các ý chính, số câu, câu trích.
3. **Chê** — như trên; không thấy thì nói không thấy trong mẫu.
4. **Khách hay hỏi gì.**
5. **Việc nên làm trước** — theo bạn, MỘT việc (sửa gì, trả lời sẵn câu hỏi nào, đưa ý nào vào bài bán), dựa trên câu chê / câu hỏi đếm được; mẫu quá ít hoặc không có gì để dựa thì nói «chưa đủ để khuyên» và nên đọc thêm gì. Điều chỉ MỘT người viết thì giữ nguyên là lời của một người («một người viết rằng…») — đừng biến thành tính chất của sản phẩm hay thành câu nên đưa vào bài bán. Vài chục câu hiện lên đầu **không đủ để khuyên «nên nhập», «nên mua», «nên bán» món đó** — họ hỏi vậy thì nói các câu đã đọc cho thấy gì và nói rõ chừng ấy chưa đủ để quyết.
6. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Thường là: đọc gì, bao nhiêu câu trên tổng bao nhiêu đánh giá · đây là các câu sàn hiện lên đầu, không đại diện mọi khách · sao trong phần đã đọc khác điểm chung của cả sản phẩm / quán.
7. **Việc nên làm tiếp** — một câu.
