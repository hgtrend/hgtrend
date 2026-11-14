---
name: nguon-hang-1688
description: Tìm nguồn hàng sỉ bên Trung Quốc trên 1688 và Taobao bằng HG Trend — tìm mẫu theo từ khoá kèm giá sỉ ¥, xem chi tiết một mẫu khi đã có link, đọc đánh giá của người mua Taobao. Dùng khi người dùng hỏi «tìm nguồn sỉ món X», «giá sỉ 1688 bao nhiêu», «tìm xưởng», «xem giúp link 1688 / Taobao này», «khách Trung Quốc đánh giá mẫu này thế nào», kể cả khi họ muốn tìm bằng ảnh hay hỏi phí vận chuyển (hai việc HG Trend chưa làm — kỹ năng nói rõ cách trả lời).
---
# Tìm nguồn hàng sỉ 1688, Taobao

Người dùng muốn nhập hàng từ Trung Quốc. Chọn đúng công cụ, dịch từ khoá sang tiếng Trung cho đúng mặt hàng, rồi kể lại dữ liệu — đây là **dữ liệu thô của trang bán hàng Trung Quốc** (tiếng Trung, giá ¥), HG Trend không tính sẵn gì.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Chọn công cụ

| Người dùng cần | Công cụ | Tham số |
|---|---|---|
| Tìm mẫu / xưởng / giá sỉ theo tên món | «Tìm hàng sỉ trên 1688» (`hgy3sv74`, ~77 token) | `keyword` tiếng Trung |
| Có link 1688, xem chi tiết mẫu | «Thông tin sản phẩm sỉ 1688 theo mã» (`hgjhfxv6`, ~77 token) | `itemId` = dãy số trong link (`…/offer/906325763433.html`) |
| Tìm trên Taobao / Tmall (giá lẻ Trung Quốc) | «Tìm hàng trên Taobao, Tmall» (`hgfom7ek`, ~120 token) | `keyword` tiếng Trung; lọc giá ¥ bằng `startPrice`, `endPrice`; chỉ Tmall bằng `tmall` |
| Có link Taobao, xem chi tiết | «Thông tin sản phẩm Taobao, Tmall» (`hg7lsplr`, ~120–200 token) | `itemId` = số sau `id=`. Giá cao, sát ngưỡng hỏi trước (200 token): **luôn báo giá và chờ đồng ý**. Chưa có số đo thật cho công cụ này — chỉ kể điều thấy rõ |
| Người mua Trung Quốc đánh giá một mẫu Taobao | «Đánh giá sản phẩm trên Taobao, Tmall» (`hg3vypxg`, ~120 token) | `itemId` của mẫu Taobao |

Việc khác: muốn biết món đó bán ở Việt Nam ra sao → «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`, ~27–115 token; phần 1688 trong đó có lượt không lấy được). Hàng đang hot bên Trung Quốc → «Tìm hàng hot: TikTok Shop, Douyin, Google» (`hgtimhot`, ~27–153 token). Hai báo cáo này có giá riêng — nêu đúng giá của chúng, đừng coi như «gần 100 token».

**HG Trend chưa làm được** — nói thẳng, đừng chạy công cụ khác thay:

- **Tìm bằng ảnh.** Đừng bảo người dùng gửi ảnh rồi hứa sẽ tìm; đề nghị tìm bằng từ khoá (họ tả món, hoặc bạn tả từ ảnh họ gửi).
- **Phí vận chuyển về Việt Nam, thuế, phí mua hộ, tỉ giá** — hỏi bên vận chuyển / mua hộ của họ.
- **Điểm uy tín của xưởng** (số năm, tỉ lệ mua lại, điểm dịch vụ), có nhận **in logo / làm theo mẫu** không — phải hỏi xưởng. Thứ kể được: tên công ty, dấu «đã kiểm xưởng», số đã bán, các mức giá.
- Đánh giá của người mua **trên 1688** (chỉ có Taobao).

## Trước khi chạy

1. **Dịch từ khoá sang tiếng Trung giản thể**, ngắn (2–6 chữ Hán), đúng cách người Trung gọi món đó: «quạt cầm tay» → 手持风扇. **Cho người dùng xem từ đã dịch** — dịch lệch là ra mặt hàng khác.
2. Tìm 1688 **chỉ theo từ khoá**: không lọc được giá, số lượng tối thiểu, nơi bán. Đưa đặc điểm quan trọng nhất vào từ khoá; trên kết quả chỉ tự lọc được theo thứ có trong danh sách (tên, giá hiển thị, nơi bán). Số lượng tối thiểu phải xem chi tiết từng mẫu.
3. Có link thì lấy đúng dãy số làm `itemId`; đừng tìm lại bằng từ khoá.

**Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token; đừng tự đổi ra đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ trừ token theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

Mỗi công cụ trong bảng trên gần 100 token một lượt: lượt đầu chỉ chạy **một công cụ, đúng nơi và đúng việc người dùng hỏi**.

## Chạy

```
chay_cong_cu(ma="hgy3sv74", tham_so={"keyword": "手持风扇"})
chay_cong_cu(ma="hgjhfxv6", tham_so={"itemId": "906325763433"})
```

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

Dữ liệu thô, rất nhiều trường; chỉ cần các trường dưới đây. Tên đều bằng tiếng Trung: **dịch và giữ tên gốc bên cạnh**; nhãn tiếng Trung (kiểu «限时价», «深度验厂») thì dịch nghĩa, đừng để nguyên chữ Hán. Bỏ qua các trường về tài khoản của nguồn. Danh sách con (phân loại, bậc giá, ảnh, nhãn) cũng bị cắt bớt, chỗ cắt ghi «…(còn N mục)»: nói còn bao nhiêu mục chưa hiện, đừng nói mẫu chỉ có chừng ấy phân loại hay chừng ấy bậc giá.

| Công cụ | Trường đáng đọc | Lưu ý |
|---|---|---|
| `hgy3sv74` | Mẫu nằm ở `data` → `OFFER` → `items`, thông tin từng mẫu trong khối `data` của nó (`result` ngoài cùng rỗng là bình thường). `found`; mỗi mẫu: `title`, `priceInfo`, `bookedCount`, `province` + `city`, `loginId` (tên shop), `factoryInspection`, `offerId` | **Bị cắt bớt**: `rut_gon` ghi giữ bao nhiêu mẫu (vd 19 trên 60) — nói mới xem được chừng ấy. `priceInfo` là giá hiện trên trang tìm, đừng gọi «giá thấp nhất». `bookedCount` không ghi của kỳ nào. `factoryInspection` chỉ là dấu «đã kiểm xưởng», không phải bảo chứng. Nhãn «包邮» = bao vận chuyển **nội địa Trung Quốc**. Link: `https://detail.1688.com/offer/` + `offerId` + `.html` |
| `hgjhfxv6` | `companyName`, `saledCount`, `currentPrices` (giá ¥ + `beginAmount` = mua từ bao nhiêu cái), khoảng giá, tên phân loại | Chỉ có **một** mức `currentPrices` kèm khoảng giá kiểu «4.20-14.00»: đó là giá **theo phân loại**, không phải bậc theo số lượng. Nhiều mức `currentPrices` mới là bậc theo số lượng |
| `hgfom7ek` | `itemList`: `itemName`, `priceYuanDouble`, `orderPayUV` (số người đã trả tiền), `itemLoc`, `itemId` | Giá **lẻ** bên Trung Quốc, thường cao hơn giá sỉ 1688. Link: `https://item.taobao.com/item.htm?id=` + `itemId` |
| `hg3vypxg` | `totalFuzzy`, `keywords` (cụm hay nhắc + số lần), `comments` → `content` | Một lượt chỉ đọc một trang (~20 câu). Nhiều câu — có lượt cả trang — là lời khen mặc định hệ thống tự điền: bỏ, nói có bao nhiêu câu thật. `keywords` đáng dùng hơn 20 câu mẫu |

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

Năm công cụ trong bảng «Chọn công cụ» trả dữ liệu thô, HG không tính sẵn con số nào ở đó: mọi con số bạn nêu chỉ tính trên **các mẫu thật có trong kết quả đã giữ và đúng mặt hàng** — ghi rõ trong bao nhiêu mẫu, đừng suy ra cho cả trang hay cho `found`.

**Phần cách viết** — người đọc là chủ shop đang bận, đọc trên điện thoại:

- **Dòng đầu nói giá lượt chạy** (như mục «Trước khi chạy»), **ngay sau đó là câu mở trả lời thẳng điều họ hỏi**, kèm một hai con số chính. Họ hỏi «nên hay không» thì câu mở nói luôn bạn nghiêng về phía nào, mở bằng «Theo tôi».
- **Mỗi con số, mỗi ý chỉ nêu một lần.** Số đã nêu ở câu mở thì bên dưới không nêu lại; phần số liệu chỉ thêm số chưa nêu. Chỉ đưa số giúp họ quyết; bảng chỉ dùng khi xếp từ 3 mục cạnh nhau. Câu trả lời cho một lượt chạy thường gọn trong 300–450 chữ — dài hơn là đang lặp.
- **Lời thường, không dùng chữ của máy.** Không viết tên trường. Số bán nói kèm kỳ đúng như bảng trên ghi («đã bán 12.000 cái từ trước tới nay», «trong tháng», hoặc «không ghi của kỳ nào») thay cho «cộng dồn»; «giá niêm yết (giá gạch ngang)» thay cho «giá gốc» (dễ nhầm với giá nhập); «người ta hay tìm kèm: …» thay cho «cụm gõ kèm»; «tôi mới xem được 4 trong 30 mẫu» thay cho «kết quả bị cắt». Điểm Google nói bằng so sánh trước, điểm để trong ngoặc, và **gọi đúng tên là «mức quan tâm trên Google»** — không gọi là «lượt tìm», «số người tìm»: «mức quan tâm trên Google 4 tuần gần đây chỉ bằng khoảng một phần tư mức trung bình cả năm (điểm 6 so với 22, thang 100)». Chữ và nhãn tiếng nước ngoài thì dịch.
- **Lưu ý về giới hạn dữ liệu gom vào MỘT dòng cuối** («Lưu ý khi đọc số: …»): mỗi ý một lần, chỉ ý dính tới con số bạn đã dùng. Riêng lưu ý làm đổi nghĩa con số ngay tại chỗ thì viết liền con số bằng vài chữ («109.000 đ, niêm yết 199.000 đ»; «12 ¥ một cái, chưa gồm phí về Việt Nam») và không nhắc lại ở cuối.
- **Kết bằng MỘT việc nên làm tiếp**, một câu; cần chạy thêm thì nêu giá và chờ họ đồng ý.

Bố cục:

1. **Câu mở** — trả lời thẳng điều họ hỏi. Hỏi giá sỉ: «trong N mẫu đúng mặt hàng, giá hiện trên trang tìm từ A đến B ¥» (mua ít nhất bao nhiêu cái và giá theo số lượng thì phải xem chi tiết từng mẫu — nói vậy), và theo bạn nên xem kỹ mẫu nào trước, vì con số nào (giá, số đơn, dấu «đã kiểm xưởng»). Dữ liệu ở đây chỉ đủ để khuyên **xem kỹ / hỏi thử mẫu nào trước**: họ hỏi «có nên nhập về bán không», «đặt luôn xưởng này được không» thì câu mở là «chưa đủ dữ liệu để khuyên chốt» — chưa có sức mua ở Việt Nam, chi phí về tới nơi, độ tin của xưởng — rồi nói cần xem thêm gì. Đưa link một mẫu: giá theo từng bậc số lượng hoặc theo phân loại. Phần lớn kết quả lạc loại thì câu mở nói vậy: từ khoá dịch chưa trúng, đề nghị từ khoá khác (lượt thêm, chờ họ đồng ý).
2. **Bảng 5–8 mẫu đúng mặt hàng nhất** — tên (bản dịch + tên gốc), giá ¥, số đơn / đã bán, nơi bán, shop (1688 có; kết quả Taobao không có tên shop thì bỏ cột này), link.
3. **Trước khi đặt hàng cần kiểm, cần tính thêm** — hai ba ý sát với mẫu vừa nêu: phí vận chuyển về Việt Nam, thuế, phí mua hộ (dữ liệu không có — hỏi bên vận chuyển) · số lượng mua tối thiểu và giá theo bậc (xem chi tiết mẫu, mỗi mẫu một lượt, chờ họ đồng ý) · uy tín xưởng: nêu thứ dữ liệu có, nói rõ chưa đủ để kết luận.
4. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Thường là: giá ¥ là giá hiện trên trang tìm, chưa rõ mua tối thiểu bao nhiêu, chưa gồm vận chuyển, thuế, phí nhập · mới xem bao nhiêu mẫu trên tổng · kết quả ở đây không ghi mốc giờ.
5. **Việc nên làm tiếp** — một câu.

**Không tự đổi ¥ ra đồng**, không ước giá về tới Việt Nam; họ đưa tỉ giá và phí thì tính theo đúng số họ đưa.
