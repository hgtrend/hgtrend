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

Giá: **~270–1.430 đ mỗi lượt** — không xem Douyin khoảng 270 đ, có xem tới khoảng 1.430 đ. **Rẻ thì báo rồi chạy luôn:** cộng tiền mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 2.000 đ: báo (chạy gì, bao nhiêu tiền) rồi gọi `chay_cong_cu` ngay trong cùng câu trả lời. Trên 2.000 đ: nêu số lượt, tổng tiền và **chờ đồng ý**.

Câu báo trước khi chạy gồm ba ý: chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **giá**.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ tính tiền theo số kết quả hay có mức cao vượt ngưỡng. Thứ họ hỏi mà dữ liệu không trả lời được thì nói ngay trong câu báo.

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
| `tiktok_shop_viet_nam` | Các món ở **trang kết quả đầu** TikTok Shop Việt Nam: `so_mon_tim_thay`, `so_shop`, `mon_da_ban_tren_1000`, `gia_dang_ban`, `gia_goc`, `mon_dang_de_gia_soc`, `mon_ban_chay_nhat` | Xếp theo `da_ban` = **tổng lượt bán cộng dồn**: món đứng đầu là món đã bán nhiều nhất trong vài chục món này, chưa chắc đang lên. Số của sàn là xấp xỉ — **đừng lấy hiệu hai lần chạy** để suy ra số bán trong ngày / tuần. `gia_goc` = giá niêm yết gạch ngang, **không phải giá khách trả**: nêu cả hai giá. `mon_dang_de_gia_soc` = số món dưới 10 % giá gốc; khi chiếm phần lớn thì giá đang bán ở giữa bị kéo xuống (có lượt còn 1.000 đ) — nói rõ |
| `google` → `xu_huong_tung_tu` | Mức quan tâm Google ở Việt Nam của loại hàng và vài cụm gõ kèm: `diem_4_tuan_gan_nhat`, `diem_trung_binh_12_thang`, `xu_huong` | Điểm 0–100 là **mức tương đối giữa các cụm trong lượt này**, không phải số lượt tìm. «Đang lên» = 4 tuần gần nhất cao hơn trung bình năm của chính cụm đó từ 30 % (khác `tuan_vua_qua_so_voi_4_tuan_truoc`). Cụm điểm rất thấp (dưới chừng 10): phần trăm tăng giảm ít ý nghĩa. Bỏ qua cụm trong `tu_qua_it_nguoi_tim` |
| `google` → `nguoi_ta_hay_tim_kem` | Cụm Google gợi ý | Không kèm số người gõ |
| `google_shopping` | Món Google liệt kê: `so_cho_ban` (số món, không phải số cửa hàng), `noi_ban_nhieu`, khoảng giá | Với một loại hàng rộng, khoảng giá trải từ vài đồng tới hàng chục triệu — **đừng dùng làm giá tham khảo**; chỉ để biết hàng loại này bán nhiều ở đâu |
| `douyin_shop` | Khi có `tu_khoa_douyin`: món ở trang đầu Douyin Shop, xếp theo `ban_trong_thang`; `gia_te` (¥), `ty_le_khen`, `so_nguoi_ban_ho`, `mon_ban_tren_10000_trong_thang` | Số bán **trong tháng** bên Trung Quốc — phần duy nhất có số theo kỳ. Dịch tên, giữ tên gốc bên cạnh. Hàng đó có về Việt Nam không, bao lâu: báo cáo không đo — nếu nêu thì ghi là nhận định |
| `hg_nhan_xet` | Câu máy ghép sẵn | **Đừng chép**; tự viết lại từ các số |
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

1. **Món đã bán được nhiều trên TikTok Shop** — 3–5 món: tên đúng, shop, số đã bán (cộng dồn), hai giá, link; kèm số món / số shop ở trang đầu, số món trên 1.000, số món dưới 10 % giá gốc. **Luôn kèm:** đây là các món ở trang đầu cho cụm này, không phải bảng xếp hạng cả sàn, không cho biết món nào đang lên.
2. **Google** — cụm nào đang lên, đi ngang; nói rõ là mức tương đối.
3. **Bên Trung Quốc** (nếu có) — 3–5 món: tên gốc + bản dịch, giá ¥, số bán trong tháng, link.
4. **Điều đáng cân nhắc** — 2–3 ý, ghi rõ là nhận định. Danh sách cho thấy thứ ĐÃ có người bán nhiều, không nói còn chỗ cho người mới hay không.
5. Kết bằng một hai dòng: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi như bảng «Đọc kết quả» ghi · phần nào lần này không lấy được.

Muốn đào sâu một món: đề nghị «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`) hoặc «Chi tiết một sản phẩm TikTok Shop» (`hgymznld`) — lượt thêm, hỏi trước.
