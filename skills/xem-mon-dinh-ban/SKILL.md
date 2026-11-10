---
name: xem-mon-dinh-ban
description: Xem một món định nhập hoặc định bán ở Việt Nam có ai tìm, ai đang bán, giá bao nhiêu, giá sỉ bên Trung Quốc — bằng báo cáo «Xem món định bán có ai tìm, ai bán chưa» của HG Trend. Dùng khi người dùng nêu một món cụ thể — hoặc vài món muốn so với nhau — và hỏi «có nên bán / nhập món này không», «món nào đáng nhập hơn», «thị trường món này ra sao», «món này có ai tìm không», «đang bán giá bao nhiêu», «qua mùa chưa», «còn dư địa không».
---
# Xem món định bán có ai tìm, ai bán chưa

Người dùng sắp bỏ tiền nhập một món. Chạy báo cáo «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`) cho món đó rồi kể lại cho đúng: phần nào là số đo, phần nào là suy luận, phần nào dữ liệu không nói được.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 đồng) · `xem_cong_cu` (tham số và giá, 0 đồng) · `chay_cong_cu` (chạy thật, tính tiền). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| Nêu một món cụ thể («định nhập quạt mini cầm tay») | Dùng kỹ năng này |
| So 2–3 món | Dùng kỹ năng này, mỗi món một lượt; tính tổng tiền bằng con số. Đừng trả lời thay bằng hiểu biết chung |
| Chưa có món, hỏi «nên bán gì» | Báo cáo «Tìm hàng hot: TikTok Shop, Douyin, Google» (`hgtimhot`, ~270–1.430 đ) |
| Chỉ cần mẫu, xưởng, giá sỉ Trung Quốc | «Tìm hàng sỉ trên 1688» (`hgy3sv74`, ~770 đ) |
| Hỏi đúng số liệu của Shopee, Lazada, Tiki, Sendo, Zalo | HG Trend chưa có. Nói vậy, hỏi họ có muốn xem Google + TikTok Shop thay không |
| Đang bán ở các sàn đó nhưng hỏi về MÓN | Vẫn dùng kỹ năng này; dòng đầu câu trả lời nói rõ không có số liệu của sàn họ nhắc |

## Trước khi chạy

1. **Tên món** (`mon_hang`): như người mua gõ — tiếng Việt có dấu, ngắn nhưng đủ phân biệt («quạt mini cầm tay», không phải «quạt»). Bỏ tên thương hiệu trừ khi họ muốn xem đúng thương hiệu. Rút từ lời tả dài thì nói bạn tìm theo cụm nào; phải đoán món thì chờ họ xác nhận.
2. **Giá sỉ 1688** (`tu_khoa_1688`): chỉ thêm khi người dùng **nói rõ** muốn giá sỉ, giá nhập Trung Quốc hay nhắc 1688 — «định nhập món X» chưa phải yêu cầu này: chạy phần cơ bản; cuối câu trả lời hỏi có muốn xem giá sỉ không — khi đó chạy riêng «Tìm hàng sỉ trên 1688» (`hgy3sv74`, ~770 đ), đừng chạy lại cả báo cáo này. Từ khoá phải là **tiếng Trung giản thể**, bạn dịch và cho người dùng xem («quạt mini cầm tay» → 手持风扇).

Giá: **~270–1.040 đ mỗi lượt** — không xem 1688 khoảng 270 đ, có xem tới khoảng 1.040 đ. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng tiền mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 2.000 đ: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 2.000 đ: **chưa chạy** — nêu số lượt, tổng tiền và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ tính tiền theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

## Chạy

```
chay_cong_cu(ma="hgxemmon", tham_so={"mon_hang": "quạt mini cầm tay"})
chay_cong_cu(ma="hgxemmon", tham_so={"mon_hang": "quạt mini cầm tay", "tu_khoa_1688": "手持风扇"})
```

| Tham số | Bắt buộc | Ý nghĩa |
|---|---|---|
| `mon_hang` | có | Tên món bằng tiếng Việt, vd quạt mini cầm tay |
| `tu_khoa_1688` | không | Từ khoá TIẾNG TRUNG để xem giá sỉ 1688, vd 手持风扇. Bỏ trống thì không xem 1688 (rẻ hơn khoảng 770 đ) |
| `so_mon` | không | Số món mẫu mỗi nơi (mặc định 5) (từ 3 đến 10) |

Chờ vài chục giây là bình thường.

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

| Trường | Là gì | Lưu ý |
|---|---|---|
| `luc` | Giờ lấy dữ liệu | Luôn ghi lại |
| `co_ai_tim` → `google_12_thang` | Mức quan tâm trên Google ở Việt Nam, khoảng một năm: `diem_4_tuan_gan_nhat`, `diem_trung_binh_12_thang`, `tuan_tim_nhieu_nhat`, `thang_tim_nhieu`, `so_tuan_gan_nhu_khong_ai_tim`, `nhan_xet` | Điểm **0–100 là mức tương đối** của chính món này (100 = tuần cao nhất), **không phải số lượt tìm**, không so được giữa hai món. Chỉ nói được 4 tuần gần nhất cao hay thấp hơn trung bình năm. `thang_tim_nhieu` không ghi năm — đừng gắn năm |
| `co_ai_tim` → `nguoi_ta_hay_go_kem` | Cụm Google gợi ý | Không kèm số người gõ; đừng suy ra «khách chuộng loại nào» |
| `ai_dang_ban` → `tiktok_shop` | Các món ở **trang kết quả đầu** TikTok Shop Việt Nam: `so_mon_tim_thay`, `so_shop`, `mon_da_ban_tren_1000`, `gia_dang_ban`, `gia_goc`, `mon_dang_de_gia_soc`, `ban_chay_nhat` | `gia_dang_ban` = giá khách trả lúc chạy; `gia_goc` = giá niêm yết gạch ngang, **không phải giá khách trả**. Mỗi khối giá có `thap_nhat`, `trung_binh`, `cao_nhat` tính trên `so_mon_tinh` món, sau khi HG bỏ **món giá sốc** (`bo_gia_soc`: giá đang bán dưới 10 % giá niêm yết — kiểu 1.000 đ để kéo khách, không phải giá bán thật) và **món giá lệch hẳn** khỏi số đông (`bo_gia_lech`, vài giá đã bỏ ghi ở `gia_lech_da_bo`). Nêu giá trung bình thì nói kèm tính trên mấy món, đã bỏ mấy món; chỉ còn dưới 5 món thì nói thêm «quá ít món để coi là giá chung». `mon_dang_de_gia_soc` = số món giá sốc trên tổng số món. Khối `gia_dang_ban` trống = cả trang đầu để giá sốc, **chưa có giá bán thật**: nói vậy, đừng lấy giá niêm yết thay vào. Món trong `ban_chay_nhat` có giá đang bán dưới 10 % giá niêm yết cũng là giá sốc — đừng trình bày như giá bán. Món không ghi giá niêm yết mà giá đang bán thấp hẳn so với cả loạt (kiểu 1.000 đ) cũng là giá sốc. `da_ban` = số **cộng dồn**, không phải của tuần hay tháng này. Ô giá trống = không lấy được. Hai lượt cách vài phút có thể ra số món khác nhau |
| `ai_dang_ban` → `google_shopping` | Món Google liệt kê ở trang đầu: `so_cho_ban` (số món, không phải số cửa hàng), `noi_ban_nhieu`, khối `gia` (cùng cách tính như trên), món mẫu | **Đọc tên món mẫu trước.** Phần lớn không đúng món hỏi thì chỉ nói «Google Shopping lần này ra phần lớn món khác» và bỏ cả phần này. Tên Shopee, Lazada ở đây là món Google liệt kê, **không phải số liệu của sàn**. Tên không phải cửa hàng (chữ trên nút bấm) thì bỏ qua |
| `gia_si_1688` | Khi có `tu_khoa_1688`: số món ở trang đầu (`so_mon`), `gia_te_mot_cai` (¥), `nhieu_don_nhat` kèm `so_don` | Giá ¥ một cái, **chưa gồm vận chuyển, thuế, phí nhập về**. `so_mon` = 0 là **lần này không lấy được**, không phải 1688 không có hàng. **Đọc `ten` các món** — từ khoá bạn dịch có thể lệch: phần lớn là mặt hàng khác thì chỉ nói «1688 lần này ra phần lớn mặt hàng khác, có thể do từ khoá dịch chưa trúng» và bỏ cả khoảng giá lẫn mẫu nhiều đơn nhất. `so_don` không ghi của kỳ nào |
| `hg_nhan_xet` | Câu máy ghép sẵn | **Đừng chép**; tự viết lại từ các số theo cột này |
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

1. **Câu mở** — có người tìm không, đã đông người bán chưa; và khi họ hỏi nên nhập / nên bán không, theo bạn nghiêng về bên nào trong bốn ý: **nên nhập lúc này · chưa nên lúc này (chờ mùa, hoặc thử ít) · không nên · chưa đủ dữ liệu để khuyên** — kèm con số chính. Khi cân: số «đã bán» tính từ trước tới nay, **không phải bằng chứng món đang bán chạy lúc này**; số món, số shop là ở trang kết quả đầu, không phải tổng người bán. Mức quan tâm 4 tuần gần nhất thấp hơn trung bình năm thì đừng nghiêng «nên nhập lúc này» chỉ vì số đã bán cao. **Dữ liệu Google thưa** (trung bình năm chỉ vài điểm, hoặc quá nửa số tuần gần như không ai tìm — trừ trường hợp «món theo mùa» ở mục dưới) hoặc phần Google lần này không lấy được: câu mở là **«chưa đủ dữ liệu để khuyên nên nhập hay không»**, không nghiêng về bên nào; về người tìm chỉ nói «Google quá thưa, không đọc được», không viết «ít người mua», «không ai tìm», không đoán mùa. Số đã bán từ trước tới nay không thay được cho phần này.
2. **Giá bán tham khảo** — một hai câu: trên TikTok Shop giá đang bán **trung bình** bao nhiêu, từ đâu tới đâu (tính trên mấy món, đã bỏ mấy món giá sốc — lần đầu nhắc thì giải thích: giá kiểu 1.000 đ để kéo khách, không phải giá bán thật); các món bán chạy nhất đang bán giá nào. Google Shopping: nêu giá trung bình khi món mẫu đúng mặt hàng — đó là giá cửa hàng đăng trên Google. Chưa có giá bán thật thì nói vậy.
3. **Rủi ro lớn nhất** — theo bạn, MỘT ý, một hai câu (số đã nêu ở câu mở thì chỉ dẫn lại ý); thêm tối đa hai điều đáng cân nhắc khác, mỗi điều một câu. Số món để giá sốc chỉ cho biết giá hiện trên trang chưa phải giá bán thật — **đừng suy ra «giá bị kéo xuống», «khó cạnh tranh về giá»** từ con số đó; giá bán thật xem ở khối giá trung bình.
4. **Số liệu chưa nêu ở trên** — gọn: *người tìm* (4 tuần gần nhất so với trung bình năm, tháng được tìm nhiều, vài cụm gõ kèm đáng chú ý) · *người bán* (số món / số shop ở trang đầu, bao nhiêu món đã bán trên 1.000 cái, 2–3 món bán chạy nhất: tên đúng, shop, đã bán, giá đang bán, link) · *giá sỉ* nếu có (khoảng giá ¥, mẫu nhiều đơn nhất kèm link; muốn ước lãi thì hỏi tỉ giá và phí của họ — họ bảo cứ ước thì chỉ nhân một tỉ giá ghi rõ là giả định, không tự đặt phí, không đưa con số lãi).
5. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Với báo cáo này thường là: mức quan tâm Google là thang 0–100 của riêng món này, không phải số lượt tìm, mới một năm dữ liệu nên chỉ gợi ý về mùa · số món là ở trang kết quả đầu, không phải cả sàn · số đã bán tính từ trước tới nay, không phải của tháng này · giá ¥ là giá một cái trên trang, chưa gồm vận chuyển, thuế, phí nhập.
6. **Việc nên làm tiếp** — một câu.

## Tình huống hay gặp

- **Dữ liệu Google thưa** (hai điểm đều chỉ vài điểm, phần lớn số tuần gần như không ai tìm): không nói «đang lên», «đang xuống», «qua mùa» dù `nhan_xet` ghi vậy, không đọc `thang_tim_nhieu` thành mùa cao điểm. Nói: dữ liệu Google quá thưa để đọc xu hướng; chưa chắc là không ai mua — xem phần người bán. Về phía người tìm thì câu mở là «chưa đủ dữ liệu để khuyên».
- **Món theo mùa**: cả năm gần như không ai tìm nhưng 4 tuần gần nhất vọt lên rõ — tín hiệu thật, cứ nêu.
- `gia_si_1688` ra 0 món mà người dùng vẫn cần: đề nghị chạy riêng «Tìm hàng sỉ trên 1688» (`hgy3sv74`, ~770 đ) — lượt thêm, hỏi trước.
- Hỏi «bao nhiêu người tìm mỗi tháng», doanh thu một shop, món bán chạy nhất cả sàn: báo cáo này không có.
