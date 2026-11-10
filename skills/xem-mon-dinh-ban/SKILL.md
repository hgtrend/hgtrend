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
| Đang bán ở các sàn đó nhưng hỏi về MÓN | Vẫn dùng kỹ năng này; câu báo nói rõ không có số liệu của sàn họ nhắc |

## Trước khi chạy

1. **Tên món** (`mon_hang`): như người mua gõ — tiếng Việt có dấu, ngắn nhưng đủ phân biệt («quạt mini cầm tay», không phải «quạt»). Bỏ tên thương hiệu trừ khi họ muốn xem đúng thương hiệu. Rút từ lời tả dài thì nói bạn tìm theo cụm nào; phải đoán món thì chờ họ xác nhận.
2. **Giá sỉ 1688** (`tu_khoa_1688`): chỉ thêm khi người dùng **nói rõ** muốn giá sỉ, giá nhập Trung Quốc hay nhắc 1688 — «định nhập món X» chưa phải yêu cầu này (chạy phần cơ bản, cuối câu trả lời hỏi có muốn xem giá sỉ không). Từ khoá phải là **tiếng Trung giản thể**, bạn dịch và cho người dùng xem («quạt mini cầm tay» → 手持风扇).

Giá: **~270–1.040 đ mỗi lượt** — không xem 1688 khoảng 270 đ, có xem tới khoảng 1.040 đ. **Rẻ thì báo rồi chạy luôn:** cộng tiền mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 2.000 đ: báo (chạy gì, bao nhiêu tiền) rồi gọi `chay_cong_cu` ngay trong cùng câu trả lời. Trên 2.000 đ: nêu số lượt, tổng tiền và **chờ đồng ý**.

Câu báo trước khi chạy gồm ba ý: chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **giá**.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ tính tiền theo số kết quả hay có mức cao vượt ngưỡng. Thứ họ hỏi mà dữ liệu không trả lời được thì nói ngay trong câu báo.

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
| `ai_dang_ban` → `tiktok_shop` | Các món ở **trang kết quả đầu** TikTok Shop Việt Nam: `so_mon_tim_thay`, `so_shop`, `mon_da_ban_tren_1000`, `gia_dang_ban`, `gia_goc`, `mon_dang_de_gia_soc`, `ban_chay_nhat` | `gia_dang_ban` = giá khách trả lúc chạy; `gia_goc` = giá niêm yết gạch ngang, **không phải giá khách trả** — luôn nêu cả hai. `mon_dang_de_gia_soc` = số món có giá đang bán dưới 10 % giá gốc; khi chiếm phần lớn thì giá ở giữa bị kéo xuống — nói rõ, đừng lấy giá gốc thay vào. `da_ban` = số **cộng dồn**, không phải của tuần hay tháng này. Ô giá trống = không lấy được. Hai lượt cách vài phút có thể ra số món khác nhau |
| `ai_dang_ban` → `google_shopping` | Món Google liệt kê ở trang đầu: `so_cho_ban` (số món, không phải số cửa hàng), `noi_ban_nhieu`, khoảng giá, món mẫu | **Đọc tên món mẫu trước.** Phần lớn không đúng món hỏi thì chỉ nói «Google Shopping lần này ra phần lớn món khác» và bỏ cả phần này. Tên Shopee, Lazada ở đây là món Google liệt kê, **không phải số liệu của sàn**. Tên không phải cửa hàng (chữ trên nút bấm) thì bỏ qua |
| `gia_si_1688` | Khi có `tu_khoa_1688`: số món ở trang đầu (`so_mon`), `gia_te_mot_cai` (¥), `nhieu_don_nhat` kèm `so_don` | Giá ¥ một cái, **chưa gồm vận chuyển, thuế, phí nhập về**. `so_mon` = 0 là **lần này không lấy được**, không phải 1688 không có hàng. **Đọc `ten` các món** — từ khoá bạn dịch có thể lệch: phần lớn là mặt hàng khác thì nói vậy và bỏ khoảng giá. `so_don` không ghi của kỳ nào |
| `hg_nhan_xet` | Câu máy ghép sẵn | **Đừng chép**; tự viết lại từ các số theo cột này |
| `phan_tam_thieu`, `ghi_chu` | Phần không lấy được; giới hạn dữ liệu | Nói lại cho người dùng |

## Trả lời người dùng

Người dùng bỏ tiền theo câu trả lời này. Trước khi gửi, soát:

- **Số và tên chép đúng.** Rút gọn tên không được làm đổi mặt hàng hay cách bán (giữ «combo», «mua 2 tặng 1»). Tên shop, tên kênh không phải tên loại hàng.
- **Không thêm lý do, không thêm tính chất.** Không viết «vì…», «cho thấy…» như dữ kiện; không gắn «chính hãng», «loại cơ bản», «trôi nổi»… khi kết quả không ghi.
- **Nói cỡ mẫu.** Nêu đúng số mục có trong kết quả; không nói thay cả sàn, cả thị trường. Số gộp tính cả mục không hiện tên và mục lạc loại.
- **Bỏ mục lạc loại** khỏi phần liệt kê và phần nhận định; nói đã bỏ gì.
- **Nhận định để riêng**, ghi rõ là của bạn, và phải chỉ ra được mục hay con số đỡ cho nó — đếm lại trước khi viết, không đếm được thì bỏ.
- **Giữ đơn vị gốc:** không tự đổi ¥ ra đồng, không ước doanh thu từ lượt bán, không đổi điểm tương đối thành số người.
- **Không quyết thay:** nêu điều đáng cân nhắc, không phán «nên» hay «không nên».

Thứ tự:

1. **Có ai tìm không** — 4 tuần gần nhất so với trung bình năm, tháng được tìm nhiều, cụm gõ kèm. **Luôn kèm:** đây là mức tương đối 0–100 trên Google, không phải số lượt tìm, mới một năm dữ liệu nên chỉ gợi ý về mùa vụ.
2. **Ai đang bán, giá bao nhiêu** — TikTok Shop: số món / số shop ở trang đầu, số món đã bán trên 1.000 (cộng dồn), **cả khoảng giá đang bán lẫn giá gốc**, số món dưới 10 % giá gốc, 2–3 món bán chạy nhất (tên đúng, shop, số đã bán, hai giá, link). Google Shopping: chỉ khi món mẫu đúng mặt hàng.
3. **Giá sỉ** (nếu có) — số món ở trang đầu, khoảng giá ¥, mẫu nhiều đơn nhất kèm link. **Luôn kèm:** giá ¥ một cái, chưa gồm vận chuyển, thuế, phí nhập. Muốn ước lãi thì hỏi tỉ giá và phí của họ; họ bảo cứ ước thì chỉ nhân một tỉ giá ghi rõ là giả định — không tự đặt phí, không đưa con số lãi.
4. **Điều đáng cân nhắc** — 2–3 ý, ghi rõ là nhận định.
5. Kết bằng một hai dòng: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi như bảng «Đọc kết quả» ghi · phần nào lần này không lấy được.

## Tình huống hay gặp

- **Dữ liệu Google thưa** (hai điểm đều chỉ vài điểm, phần lớn số tuần gần như không ai tìm): không nói «đang lên», «đang xuống», «qua mùa» dù `nhan_xet` ghi vậy, không đọc `thang_tim_nhieu` thành mùa cao điểm. Nói: dữ liệu Google quá thưa để đọc xu hướng; chưa chắc là không ai mua — xem phần người bán.
- **Món theo mùa**: cả năm gần như không ai tìm nhưng 4 tuần gần nhất vọt lên rõ — tín hiệu thật, cứ nêu.
- `gia_si_1688` ra 0 món mà người dùng vẫn cần: đề nghị chạy riêng «Tìm hàng sỉ trên 1688» (`hgy3sv74`, ~770 đ) — lượt thêm, hỏi trước.
- Hỏi «bao nhiêu người tìm mỗi tháng», doanh thu một shop, món bán chạy nhất cả sàn: báo cáo này không có.
