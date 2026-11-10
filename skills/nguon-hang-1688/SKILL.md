---
name: nguon-hang-1688
description: Tìm nguồn hàng sỉ bên Trung Quốc trên 1688 và Taobao bằng HG Trend — tìm mẫu theo từ khoá kèm giá sỉ ¥, xem chi tiết một mẫu khi đã có link, đọc đánh giá của người mua Taobao. Dùng khi người dùng hỏi «tìm nguồn sỉ món X», «giá sỉ 1688 bao nhiêu», «tìm xưởng», «xem giúp link 1688 / Taobao này», «khách Trung Quốc đánh giá mẫu này thế nào», kể cả khi họ muốn tìm bằng ảnh hay hỏi phí vận chuyển (hai việc HG Trend chưa làm — kỹ năng nói rõ cách trả lời).
---
# Tìm nguồn hàng sỉ 1688, Taobao

Người dùng muốn nhập hàng từ Trung Quốc. Chọn đúng công cụ, dịch từ khoá sang tiếng Trung cho đúng mặt hàng, rồi kể lại dữ liệu — đây là **dữ liệu thô của trang bán hàng Trung Quốc** (tiếng Trung, giá ¥), HG Trend không tính sẵn gì.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 đồng) · `xem_cong_cu` (tham số và giá, 0 đồng) · `chay_cong_cu` (chạy thật, tính tiền). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Chọn công cụ

| Người dùng cần | Công cụ | Tham số |
|---|---|---|
| Tìm mẫu / xưởng / giá sỉ theo tên món | «Tìm hàng sỉ trên 1688» (`hgy3sv74`, ~770 đ) | `keyword` tiếng Trung |
| Có link 1688, xem chi tiết mẫu | «Thông tin sản phẩm sỉ 1688 theo mã» (`hgjhfxv6`, ~770 đ) | `itemId` = dãy số trong link (`…/offer/906325763433.html`) |
| Tìm trên Taobao / Tmall (giá lẻ Trung Quốc) | «Tìm hàng trên Taobao, Tmall» (`hgfom7ek`, ~1.200 đ) | `keyword` tiếng Trung; lọc giá ¥ bằng `startPrice`, `endPrice`; chỉ Tmall bằng `tmall` |
| Có link Taobao, xem chi tiết | «Thông tin sản phẩm Taobao, Tmall» (`hg7lsplr`, ~1.200–4.300 đ) | `itemId` = số sau `id=`. Mức cao vượt ngưỡng: **luôn báo giá và chờ đồng ý**. Chưa có số đo thật cho công cụ này — chỉ kể điều thấy rõ |
| Người mua Trung Quốc đánh giá một mẫu Taobao | «Đánh giá sản phẩm trên Taobao, Tmall» (`hg3vypxg`, ~1.200 đ) | `itemId` của mẫu Taobao |

Việc khác: muốn biết món đó bán ở Việt Nam ra sao → «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`; phần 1688 trong đó có lượt không lấy được). Hàng đang hot bên Trung Quốc → «Tìm hàng hot: TikTok Shop, Douyin, Google» (`hgtimhot`).

**HG Trend chưa làm được** — nói thẳng, đừng chạy công cụ khác thay:

- **Tìm bằng ảnh.** Đừng bảo người dùng gửi ảnh rồi hứa sẽ tìm; đề nghị tìm bằng từ khoá (họ tả món, hoặc bạn tả từ ảnh họ gửi).
- **Phí vận chuyển về Việt Nam, thuế, phí mua hộ, tỉ giá** — hỏi bên vận chuyển / mua hộ của họ.
- **Điểm uy tín của xưởng** (số năm, tỉ lệ mua lại, điểm dịch vụ), có nhận **in logo / làm theo mẫu** không — phải hỏi xưởng. Thứ kể được: tên công ty, dấu «đã kiểm xưởng», số đã bán, các mức giá.
- Đánh giá của người mua **trên 1688** (chỉ có Taobao).

## Trước khi chạy

1. **Dịch từ khoá sang tiếng Trung giản thể**, ngắn (2–6 chữ Hán), đúng cách người Trung gọi món đó: «quạt cầm tay» → 手持风扇. **Cho người dùng xem từ đã dịch** — dịch lệch là ra mặt hàng khác.
2. Tìm 1688 **chỉ theo từ khoá**: không lọc được giá, số lượng tối thiểu, nơi bán. Đưa đặc điểm quan trọng nhất vào từ khoá; trên kết quả chỉ tự lọc được theo thứ có trong danh sách (tên, giá hiển thị, nơi bán). Số lượng tối thiểu phải xem chi tiết từng mẫu.
3. Có link thì lấy đúng dãy số làm `itemId`; đừng tìm lại bằng từ khoá.

**Rẻ thì báo rồi chạy luôn:** cộng tiền mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 2.000 đ: báo (chạy gì, bao nhiêu tiền) rồi gọi `chay_cong_cu` ngay trong cùng câu trả lời. Trên 2.000 đ: nêu số lượt, tổng tiền và **chờ đồng ý**.

Câu báo trước khi chạy gồm ba ý: chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **giá**.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ tính tiền theo số kết quả hay có mức cao vượt ngưỡng. Thứ họ hỏi mà dữ liệu không trả lời được thì nói ngay trong câu báo.

Mỗi công cụ ở đây gần nghìn đồng một lượt: lượt đầu chỉ chạy **một công cụ, đúng nơi và đúng việc người dùng hỏi**.

## Chạy

```
chay_cong_cu(ma="hgy3sv74", tham_so={"keyword": "手持风扇"})
chay_cong_cu(ma="hgjhfxv6", tham_so={"itemId": "906325763433"})
```

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

Dữ liệu thô, rất nhiều trường; chỉ cần các trường dưới đây. Tên đều bằng tiếng Trung: **dịch và giữ tên gốc bên cạnh**. Bỏ qua các trường về tài khoản của nguồn.

| Công cụ | Trường đáng đọc | Lưu ý |
|---|---|---|
| `hgy3sv74` | Mẫu nằm ở `data` → `OFFER` → `items`, thông tin từng mẫu trong khối `data` của nó (`result` ngoài cùng rỗng là bình thường). `found`; mỗi mẫu: `title`, `priceInfo`, `bookedCount`, `province` + `city`, `loginId` (tên shop), `factoryInspection`, `offerId` | **Bị cắt bớt**: `rut_gon` ghi giữ bao nhiêu mẫu (vd 19 trên 60) — nói mới xem được chừng ấy. `priceInfo` là giá hiện trên trang tìm, đừng gọi «giá thấp nhất». `bookedCount` không ghi của kỳ nào. `factoryInspection` chỉ là dấu «đã kiểm xưởng», không phải bảo chứng. Nhãn «包邮» = bao vận chuyển **nội địa Trung Quốc**. Link: `https://detail.1688.com/offer/` + `offerId` + `.html` |
| `hgjhfxv6` | `companyName`, `saledCount`, `currentPrices` (giá ¥ + `beginAmount` = mua từ bao nhiêu cái), khoảng giá, tên phân loại | Chỉ có **một** mức `currentPrices` kèm khoảng giá kiểu «4.20-14.00»: đó là giá **theo phân loại**, không phải bậc theo số lượng. Nhiều mức `currentPrices` mới là bậc theo số lượng |
| `hgfom7ek` | `itemList`: `itemName`, `priceYuanDouble`, `orderPayUV` (số người đã trả tiền), `itemLoc`, `itemId` | Giá **lẻ** bên Trung Quốc, thường cao hơn giá sỉ 1688. Link: `https://item.taobao.com/item.htm?id=` + `itemId` |
| `hg3vypxg` | `totalFuzzy`, `keywords` (cụm hay nhắc + số lần), `comments` → `content` | Một lượt chỉ đọc một trang (~20 câu). Nhiều câu — có lượt cả trang — là lời khen mặc định hệ thống tự điền: bỏ, nói có bao nhiêu câu thật. `keywords` đáng dùng hơn 20 câu mẫu |

## Trả lời người dùng

Người dùng bỏ tiền theo câu trả lời này. Trước khi gửi, soát:

- **Số và tên chép đúng.** Rút gọn tên không được làm đổi mặt hàng hay cách bán (giữ «combo», «mua 2 tặng 1»). Tên shop, tên kênh không phải tên loại hàng.
- **Không thêm lý do, không thêm tính chất.** Không viết «vì…», «cho thấy…» như dữ kiện; không gắn «chính hãng», «loại cơ bản», «trôi nổi»… khi kết quả không ghi.
- **Nói cỡ mẫu.** Nêu đúng số mục có trong kết quả; không nói thay cả sàn, cả thị trường. Số gộp tính cả mục không hiện tên và mục lạc loại.
- **Bỏ mục lạc loại** khỏi phần liệt kê và phần nhận định; nói đã bỏ gì.
- **Nhận định để riêng**, ghi rõ là của bạn, và phải chỉ ra được mục hay con số đỡ cho nó — đếm lại trước khi viết, không đếm được thì bỏ.
- **Giữ đơn vị gốc:** không tự đổi ¥ ra đồng, không ước doanh thu từ lượt bán, không đổi điểm tương đối thành số người.
- **Không quyết thay:** nêu điều đáng cân nhắc, không phán «nên» hay «không nên».

Ở đây không có số gộp tính sẵn: mọi con số bạn nêu chỉ tính trên **các mẫu thật có trong kết quả đã giữ** — ghi rõ trong bao nhiêu mẫu, đừng suy ra cho cả trang hay cho `found`.

Trình bày thành bảng 5–8 mẫu đúng mặt hàng nhất: tên (bản dịch + tên gốc), giá ¥, số đơn / đã bán, nơi bán, shop, link. Sau bảng:

- **Luôn kèm:** giá ¥ một cái trên trang, chưa gồm vận chuyển, thuế, phí nhập; đã xem bao nhiêu mẫu.
- **Không tự đổi ¥ ra đồng**, không ước giá về tới Việt Nam; họ đưa tỉ giá và phí thì tính theo đúng số họ đưa.
- Phần lớn kết quả lạc loại = từ khoá dịch chưa trúng: nói vậy, đề nghị từ khoá khác (lượt thêm, hỏi trước).
- Chọn xưởng: nêu thứ dữ liệu có và nói rõ chưa đủ để kết luận uy tín; gợi ý xem chi tiết 1–2 mẫu (mỗi mẫu một lượt, hỏi trước).

Kết bằng một hai dòng: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi như bảng «Đọc kết quả» ghi · phần nào lần này không lấy được. Kết quả ở đây không ghi mốc giờ.
