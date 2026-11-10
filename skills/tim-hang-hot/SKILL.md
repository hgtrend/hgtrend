---
name: tim-hang-hot
description: Tìm món đang bán chạy trong một loại hàng ở Việt Nam (TikTok Shop, Google) và hàng đang hot bên Trung Quốc (Douyin) — bằng báo cáo «Tìm hàng hot: TikTok Shop, Douyin, Google» của HG Trend. Dùng khi người dùng CHƯA chọn được món và hỏi «nên bán gì», «loại hàng này món nào đang hot», «món gì đang bán chạy», «bên Trung Quốc đang hot gì». Đã có một món cụ thể thì dùng kỹ năng xem-mon-dinh-ban.
---
# Tìm hàng đang bán chạy

Người dùng chưa biết bán gì. Chạy báo cáo «Tìm hàng hot: TikTok Shop, Douyin, Google» (`hgtimhot`) cho MỘT loại hàng rồi kể đúng điều dữ liệu cho thấy — nhất là phân biệt «đã bán được nhiều từ trước tới nay» với «đang hot lúc này».

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 đồng) · `xem_cong_cu` (tham số và giá, 0 đồng) · `chay_cong_cu` (chạy thật, tính tiền). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Nêu một loại hàng («đồ gia dụng món nào đang hot») | Dùng kỹ năng này, chạy với đúng cụm họ nêu — đừng bắt họ thu hẹp trước |
| Hỏi chung, không nêu loại hàng («giờ nên nhập gì») | **Hỏi lại họ quan tâm loại hàng nào** (gợi ý vài nhóm). Đừng tự chọn thay rồi chạy; đừng trả lời bằng hiểu biết chung như thể là dữ liệu |
| Đã có một món cụ thể | Báo cáo «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`, ~270–1.040 đ) |
| Bán chạy «tuần này», «tháng này» ở Việt Nam | Chạy được, nhưng nói trước: số đã bán trên TikTok Shop là cộng dồn, không có số theo tuần / tháng |
| Hàng hot bên Trung Quốc | Thêm `tu_khoa_douyin` |
| Top bán chạy của Shopee, Lazada, Tiki, Sendo, Zalo | HG Trend chưa có. Nói vậy, hỏi họ có muốn xem TikTok Shop thay không |

## Trước khi chạy

1. **Loại hàng** (`tu_khoa`): cụm tiếng Việt có dấu như người mua gõ («đồ gia dụng nhà bếp», «son kem»). Cụm rộng («mỹ phẩm») cho danh sách tạp — nói điều đó khi trình bày và gợi ý nhóm hẹp hơn để xem tiếp.
2. **Douyin Shop** (`tu_khoa_douyin`): chỉ thêm khi người dùng **nói rõ** muốn xem hàng Trung Quốc; đắt hơn nhiều. Phải là **tiếng Trung giản thể**, bạn dịch và cho người dùng xem («son kem» → 唇釉).

Giá: **~270–1.430 đ mỗi lượt** — không xem Douyin khoảng 270 đ, có xem tới khoảng 1.430 đ. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng tiền mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 2.000 đ: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 2.000 đ: **chưa chạy** — nêu số lượt, tổng tiền và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ tính tiền theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

## Chạy

```
chay_cong_cu(ma="hgtimhot", tham_so={"tu_khoa": "đồ gia dụng nhà bếp"})
chay_cong_cu(ma="hgtimhot", tham_so={"tu_khoa": "son kem", "tu_khoa_douyin": "唇釉"})
```

| Tham số | Bắt buộc | Ý nghĩa |
|---|---|---|
| `tu_khoa` | có | Loại hàng bằng tiếng Việt, vd đồ gia dụng nhà bếp |
| `tu_khoa_douyin` | không | Từ khoá TIẾNG TRUNG để xem Douyin Shop, vd 厨房小工具. Bỏ trống thì không xem Douyin (rẻ hơn khoảng 1.150 đ) |
| `so_mon` | không | Số món liệt kê mỗi nơi (mặc định 8) (từ 3 đến 10) |

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

| Trường | Là gì | Lưu ý |
|---|---|---|
| `luc` | Giờ lấy dữ liệu | Luôn ghi lại |
| `tiktok_shop_viet_nam` | Các món ở **trang kết quả đầu** TikTok Shop Việt Nam: `so_mon_tim_thay`, `so_shop`, `mon_da_ban_tren_1000`, `gia_dang_ban`, `gia_goc`, `mon_dang_de_gia_soc`, `mon_ban_chay_nhat` | Xếp theo `da_ban` = **tổng lượt bán cộng dồn**: món đứng đầu là món đã bán nhiều nhất trong vài chục món này, chưa chắc đang lên. Số của sàn là xấp xỉ — **đừng lấy hiệu hai lần chạy** để suy ra số bán trong ngày / tuần. `gia_goc` = giá niêm yết gạch ngang, **không phải giá khách trả**. Mỗi khối giá có `thap_nhat`, `trung_binh`, `cao_nhat` tính trên `so_mon_tinh` món, sau khi HG bỏ **món giá sốc** (`bo_gia_soc`: giá đang bán dưới 10 % giá niêm yết — kiểu 1.000 đ để kéo khách, không phải giá bán thật) và **món giá lệch hẳn** khỏi số đông (`bo_gia_lech`, vài giá đã bỏ ghi ở `gia_lech_da_bo`). Nêu giá trung bình thì nói kèm tính trên mấy món, đã bỏ mấy món; chỉ còn dưới 5 món thì nói thêm «quá ít món để coi là giá chung». `mon_dang_de_gia_soc` = số món giá sốc trên tổng. Khối giá đang bán trống = cả trang đầu để giá sốc, chưa có giá bán thật. Món bán chạy có giá đang bán dưới 10 % giá niêm yết cũng là giá sốc — đừng trình bày như giá bán. Món không ghi giá niêm yết mà giá đang bán thấp hẳn so với cả loạt (kiểu 1.000 đ) cũng là giá sốc |
| `google` → `xu_huong_tung_tu` | Mức quan tâm Google ở Việt Nam của loại hàng và vài cụm gõ kèm: `diem_4_tuan_gan_nhat`, `diem_trung_binh_12_thang`, `xu_huong` | Điểm 0–100 là **mức tương đối giữa các cụm trong lượt này**, không phải số lượt tìm. «Đang lên» = 4 tuần gần nhất cao hơn trung bình năm của chính cụm đó từ 30 % (khác `tuan_vua_qua_so_voi_4_tuan_truoc`). Cụm điểm rất thấp (dưới chừng 10): phần trăm tăng giảm ít ý nghĩa. Bỏ qua cụm trong `tu_qua_it_nguoi_tim` |
| `google` → `nguoi_ta_hay_tim_kem` | Cụm Google gợi ý | Không kèm số người gõ |
| `google_shopping` | Món Google liệt kê: `so_cho_ban` (số món, không phải số cửa hàng), `noi_ban_nhieu`, khoảng giá | Với một loại hàng rộng, khoảng giá trải từ vài đồng tới hàng chục triệu — **đừng dùng làm giá tham khảo**; chỉ để biết hàng loại này bán nhiều ở đâu |
| `douyin_shop` | Khi có `tu_khoa_douyin`: món ở trang đầu Douyin Shop, xếp theo `ban_trong_thang`; `gia_te` (¥), `ty_le_khen`, `so_nguoi_ban_ho`, `mon_ban_tren_10000_trong_thang` | Số bán **trong tháng** bên Trung Quốc — phần duy nhất có số theo kỳ. Dịch tên, giữ tên gốc bên cạnh. Hàng đó có về Việt Nam không, bao lâu: báo cáo không đo — nếu nêu thì ghi là nhận định |
| `hg_nhan_xet` | Câu máy ghép sẵn | **Đừng chép**; tự viết lại từ các số |
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

**Phần cách viết** — người đọc là chủ shop đang bận, đọc trên điện thoại:

- **Dòng đầu nói giá lượt chạy** (như mục «Trước khi chạy»), **ngay sau đó là câu mở trả lời thẳng điều họ hỏi**, kèm một hai con số chính. Họ hỏi «nên hay không» thì câu mở nói luôn bạn nghiêng về phía nào, mở bằng «Theo tôi».
- **Mỗi con số, mỗi ý chỉ nêu một lần.** Số đã nêu ở câu mở thì bên dưới không nêu lại; phần số liệu chỉ thêm số chưa nêu. Chỉ đưa số giúp họ quyết; bảng chỉ dùng khi xếp từ 3 mục cạnh nhau. Câu trả lời cho một lượt chạy thường gọn trong 300–450 chữ — dài hơn là đang lặp.
- **Lời thường, không dùng chữ của máy.** Không viết tên trường. Số bán nói kèm kỳ đúng như bảng trên ghi («đã bán 12.000 cái từ trước tới nay», «trong tháng», hoặc «không ghi của kỳ nào») thay cho «cộng dồn»; «giá niêm yết (giá gạch ngang)» thay cho «giá gốc» (dễ nhầm với giá nhập); «người ta hay tìm kèm: …» thay cho «cụm gõ kèm»; «tôi mới xem được 4 trong 30 mẫu» thay cho «kết quả bị cắt». Điểm Google nói bằng so sánh trước, điểm để trong ngoặc: «4 tuần gần đây chỉ bằng khoảng một phần tư mức cả năm (6 so với 22, thang 100)». Chữ và nhãn tiếng nước ngoài thì dịch.
- **Lưu ý về giới hạn dữ liệu gom vào MỘT dòng cuối** («Lưu ý khi đọc số: …»): mỗi ý một lần, chỉ ý dính tới con số bạn đã dùng. Riêng lưu ý làm đổi nghĩa con số ngay tại chỗ thì viết liền con số bằng vài chữ («109.000 đ, niêm yết 199.000 đ»; «12 ¥ một cái, chưa gồm phí về Việt Nam») và không nhắc lại ở cuối.
- **Kết bằng MỘT việc nên làm tiếp**, một câu; cần chạy thêm thì nêu giá và chờ họ đồng ý.

Bố cục cho báo cáo này:

1. **Câu mở** — theo bạn nên xem kỹ món nào trước (một, nhiều nhất hai món: tên đúng, đã bán bao nhiêu từ trước tới nay, giá đang bán) và vì con số nào. Danh sách tạp do cụm quá rộng thì nói vậy ngay ở đây và gợi ý nhóm hẹp hơn. Báo cáo này chỉ đủ để khuyên **xem kỹ món nào trước**, chưa đủ để khuyên nhập: họ hỏi «nên nhập món nào» thì nói rõ đây là món đáng xem kỹ trước, và bước sau mới trả lời được chuyện nhập.
2. **Các món đã bán được nhiều trên TikTok Shop** — 3–5 món: tên đúng, shop, số đã bán, giá đang bán (niêm yết trong ngoặc), link; kèm số món / số shop ở trang đầu, bao nhiêu món đã bán trên 1.000 cái.
3. **Google** — cụm nào đang lên, cụm nào đi ngang (một hai câu).
4. **Bên Trung Quốc** (nếu có) — 3–5 món: tên gốc + bản dịch, giá ¥, số bán trong tháng, link.
5. **Phải tự kiểm trước khi nhập** — điều danh sách này CHƯA cho biết, một hai ý sát với món bạn vừa nêu: món đó đang lên hay đã qua đỉnh (số đã bán tính từ trước tới nay) · còn chỗ cho người mới không · giá nhập.
6. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Với báo cáo này thường là: đây là các món ở trang kết quả đầu cho cụm này, không phải bảng xếp hạng cả sàn · số đã bán tính từ trước tới nay, không cho biết món nào đang lên · điểm Google là mức so giữa các cụm trong lượt này, không phải số lượt tìm · hàng bên Trung Quốc có về Việt Nam không, báo cáo không đo.
7. **Việc nên làm tiếp** — một câu: thường là xem kỹ món vừa nêu bằng «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`, ~270–1.040 đ) hoặc «Chi tiết một sản phẩm TikTok Shop» (`hgymznld`) — lượt thêm, nêu giá và chờ họ đồng ý.
