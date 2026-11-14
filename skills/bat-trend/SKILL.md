---
name: bat-trend
description: Xem TikTok ở Việt Nam hoặc một nước khác lúc này đang đẩy gì (hashtag đứng đầu bảng 7 ngày, video đang hot) và làm bản tin tuần cho một ngành hàng (từ khoá Google lên / xuống, hashtag của ngành, món bán chạy trên TikTok Shop, mẫu quảng cáo) — bằng hai báo cáo «Báo cáo trend TikTok hôm nay» và «Bản tin trend tuần theo ngành hàng» của HG Trend. Dùng khi người dùng hỏi «TikTok đang có trend gì», «hôm nay có gì hot», «hashtag nào đang lên», «nên làm video kiểu gì», «tuần này ngành … có gì mới», «theo dõi ngành giúp tôi», «mỗi tuần gửi tôi bản tin ngành …», «TikTok ở Thái Lan đang có trend gì». Đã có một món cụ thể thì dùng kỹ năng xem-mon-dinh-ban; muốn tìm món để bán thì dùng tim-hang-hot.
---
# Bắt trend: TikTok lúc này và bản tin tuần của ngành

Người dùng muốn biết đang có gì nổi để làm nội dung, hoặc muốn theo dõi ngành mình bán. Có hai báo cáo, mỗi cái trả lời một câu khác nhau:

- «Báo cáo trend TikTok hôm nay» (`hgtrendtt`) — TikTok ở một nước **lúc chạy**: 3 hashtag đứng đầu bảng 7 ngày và một mẫu vài chục video đang được đẩy.
- «Bản tin trend tuần theo ngành hàng» (`hgbantin`) — một **ngành hàng** ở Việt Nam: vài từ khoá trên Google đang lên hay xuống, 3 hashtag đầu ngành, món đã bán nhiều trên TikTok Shop cho một từ, mẫu quảng cáo TikTok.

Cả hai là **ảnh chụp lúc chạy trên một mẫu nhỏ**: không phải bảng xếp hạng đầy đủ, không đoán được ngày mai. Kể đúng điều mẫu cho thấy.

Dùng kết nối `hgtrend`: `tim_cong_cu` (tìm công cụ, 0 token) · `xem_cong_cu` (tham số và giá, 0 token) · `chay_cong_cu` (chạy thật, trừ token). Công cụ nào chưa ghi tham số ở dưới thì `xem_cong_cu` trước; đừng đoán tên tham số.

## Khi nào dùng

| Người dùng hỏi | Làm gì |
|---|---|
| «TikTok đang có trend gì», «hashtag nào đang lên», «nên làm video kiểu gì» | `hgtrendtt`. Họ đã nói bán gì và thứ đó khớp rõ một ngành trong danh sách ở dưới thì thêm `nganh`; không khớp rõ thì bỏ `nganh` (chỉ có bảng chung) và nói vậy |
| «Tuần này ngành … có gì mới», «theo dõi ngành giúp tôi» | `hgbantin` với `nganh` |
| Hỏi theo tuần / theo ngành mà chưa rõ ngành nào | Hỏi lại, đưa danh sách ngành cho họ chọn. Đừng tự chọn thay |
| Hỏi «trend» chung chung | `hgtrendtt` (không bắt buộc ngành). Bản tin tuần để ở «việc nên làm tiếp» |
| Nói rõ muốn cả hai | Hai lượt, cộng token cả hai |
| Trend ở nước khác | `hgtrendtt` với `quoc_gia`. Bản tin tuần chỉ có Việt Nam |
| Trend trên Shopee, Lazada, Tiki, Sendo, Zalo | HG Trend chưa có. Nói vậy, hỏi họ có muốn xem TikTok thay không |
| Trend trên YouTube, Facebook, Instagram, Tiểu Hồng Thư… | Không thuộc hai báo cáo này: `tim_cong_cu` với cụm «đang hot» + tên nền tảng |
| Chỉ hỏi «nhạc nào đang hot» | **Không chạy.** Nói HG Trend không có bảng xếp hạng nhạc; báo cáo trend chỉ đếm được trong mẫu vài chục video có bài nào lặp lại không (thường là không). Hỏi họ có muốn chạy báo cáo đó không, kèm giá |
| Đã có một món cụ thể / muốn tìm món để bán | «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`, ~27–115 token) / «Tìm hàng hot: TikTok Shop, Douyin, Google» (`hgtimhot`, ~27–153 token) |
| «Mỗi tuần gửi tôi bản tin» | HG Trend không tự gửi; mỗi lần xem là một lượt chạy trừ token. Chạy lượt này và nói họ nhắn lại khi muốn bản mới. **Không tự đặt lịch chạy lặp lại**; họ nói rõ muốn đặt lịch thì nêu giá mỗi lượt, số lượt mỗi tháng, tổng token và chờ đồng ý |

## Trước khi chạy

Danh sách ngành ở hai bảng dưới có **15 ngành**; tên có dấu phẩy là MỘT ngành («thời trang, phụ kiện» · «đồ ăn, đồ uống» · «tin tức, giải trí» · «thể thao, dã ngoại» · «công nghệ, điện tử») — nên gửi nguyên cụm; cửa cũng nhận một nửa («thời trang») và vài tên hay gọi («mỹ phẩm» = làm đẹp). Người dùng nói «thời trang» hay «phụ kiện» đều là ngành «thời trang, phụ kiện».

**Báo cáo trend TikTok** (`hgtrendtt`)

| Tham số | Bắt buộc | Ý nghĩa |
|---|---|---|
| `quoc_gia` | không | Mã nước 2 chữ — một trong: VN, US, FR, DE, IT, ES, GB, AR, AU, BR, CA, CO, EG, ID, IL, JP, KR, MY, MX, PH, SA, SG, ZA, TW, TH, TR, AE (mặc định VN) |
| `nganh` | không | Thêm bảng hashtag của một ngành — một trong: thời trang, phụ kiện · mẹ và bé · làm đẹp · giáo dục · đồ ăn, đồ uống · game · sức khoẻ · nhà cửa · đồ gia dụng · tin tức, giải trí · thú cưng · thể thao, dã ngoại · công nghệ, điện tử · du lịch · xe cộ |
| `so_video` | không | Số video hot liệt kê (mặc định 10) (từ 3 đến 25) |
| `chi_video_trong_nuoc` | không | Bỏ video của nước khác (mặc định false) |

- Hỏi trend ở một nước (Việt Nam hay nước khác): đặt `chi_video_trong_nuoc` = true ngay từ lượt đầu. Không đặt thì mẫu lẫn video nước khác, có lượt chiếm quá nửa, và các số đếm của HG gộp cả video nước ngoài. Chỉ để false khi người dùng nói rõ muốn xem cả video nước ngoài.
- `nganh` **chỉ thêm 3 hashtag của ngành đó**. Mẫu video và mọi số đếm vẫn là của mọi ngành — không có cách lọc video theo ngành.
- `so_video` giữ mặc định.

**Bản tin tuần** (`hgbantin`)

| Tham số | Bắt buộc | Ý nghĩa |
|---|---|---|
| `nganh` | có | Ngành hàng — một trong: thời trang, phụ kiện · mẹ và bé · làm đẹp · giáo dục · đồ ăn, đồ uống · game · sức khoẻ · nhà cửa · đồ gia dụng · tin tức, giải trí · thú cưng · thể thao, dã ngoại · công nghệ, điện tử · du lịch · xe cộ |
| `tu_khoa` | không | Tối đa 5 từ khoá tiếng Việt muốn theo dõi, cách nhau dấu phẩy. Bỏ trống = 5 từ mặc định của ngành |
| `xem_quang_cao_mau` | không | Thêm mẫu quảng cáo TikTok hiệu quả (nhiều nước, không chọn riêng được Việt Nam) (mặc định true) |

- `tu_khoa`: chỉ gửi khi người dùng tự nêu từ họ muốn theo dõi (tối đa 5). Không nêu thì bỏ trống: HG dùng 5 từ mặc định của ngành — là từ chung (kiểu «son», «serum»), không đại diện cả ngành.
- `xem_quang_cao_mau`: giữ mặc định (có mẫu quảng cáo, của nhiều nước). Chỉ đặt = false khi người dùng nói rõ không cần xem quảng cáo.

Giá: báo cáo trend TikTok **~22–29 token mỗi lượt**, bản tin tuần **~22–29 token mỗi lượt**. **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt của yêu cầu theo mức cao của khoảng giá. Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi; **dòng đầu của câu trả lời** nói đã chạy gì và lượt này tốn bao nhiêu. Tổng trên 200 token: **chưa chạy** — nêu số lượt, tổng token và **chờ đồng ý**.

**Dòng đầu của câu trả lời** (sau khi chạy) gồm ba ý, gọn trong một hai câu: đã chạy cho **cụm / link nào** (kèm từ đã dịch nếu có) · dữ liệu **lấy từ đâu** — người dùng có nhắc Shopee, Lazada, Tiki, Sendo, Zalo, kể cả chỉ là nơi họ đang bán, thì nói luôn «kết quả không có số liệu của Shopee» (đúng tên họ nhắc) · **lượt này tốn bao nhiêu** (số token đã trừ ghi trong kết quả; kết quả không ghi thì nêu giá ước tính bằng token; đừng tự đổi ra đồng). Ngay sau dòng này là câu mở trả lời thẳng.

Chỉ «chạy luôn» cho đúng việc người dùng hỏi rõ. **Hỏi trước** khi: bật phần tuỳ chọn tốn thêm mà họ chưa nói rõ cần · tự chạy thêm lượt (nơi khác, từ khoá khác, xem chi tiết) · thiếu thông tin bắt buộc hoặc phải đoán họ muốn gì · công cụ trừ token theo số kết quả hay có mức cao vượt ngưỡng. Một phần điều họ hỏi mà dữ liệu không trả lời được thì nói ngay ở dòng đầu. Họ **chỉ** hỏi thứ dữ liệu không có (số liệu riêng của một sàn chưa có, doanh thu một shop…) thì **không chạy**: nói chưa có và hỏi họ có muốn xem phần gần nhất không.

## Chạy

```
chay_cong_cu(ma="hgtrendtt", tham_so={"chi_video_trong_nuoc": true})
chay_cong_cu(ma="hgtrendtt", tham_so={"nganh": "làm đẹp", "chi_video_trong_nuoc": true})
chay_cong_cu(ma="hgbantin", tham_so={"nganh": "đồ gia dụng"})
chay_cong_cu(ma="hgbantin", tham_so={"nganh": "làm đẹp", "tu_khoa": "son tint, kem chống nắng, serum vitamin c"})
```

- Kết quả chỉ có `loi`, không có `ket_qua`: chưa trừ token. Sai tên tham số hay dạng giá trị thì sửa và gọi lại **đúng lượt đó** một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Có `ket_qua` là **đã trừ token**, kể cả khi thiếu phần. Phần nằm trong `phan_tam_thieu`: nói «lần này không lấy được». Danh sách rỗng mà không nằm trong `phan_tam_thieu`: nói «không thấy trong phần đã lấy». Không nói thành «không có».
- Mọi lượt chạy thêm sau khi đã có kết quả (chạy lại, đổi từ khoá, đổi công cụ, thêm phần tuỳ chọn): nêu giá và **chờ đồng ý**.

## Đọc kết quả

### Báo cáo trend TikTok (`hgtrendtt`)

| Trường | Là gì | Lưu ý |
|---|---|---|
| `bao_cao` | Nước và giờ lấy dữ liệu | Luôn ghi lại |
| `hashtag_dang_len` | 3 hashtag đứng đầu bảng 7 ngày của nước đó; có `nganh` thì thêm 3 hashtag đầu ngành. Mỗi cái: `hashtag`, `nganh`, `hang`, `so_bai`, `luot_xem`, `do_hot_tung_ngay`, `xu_huong_cuoi_ky` | Cả hai bảng nằm chung một danh sách: tách theo `nganh` («mọi ngành» là bảng chung), mỗi bảng có hạng 1–3 riêng. Chỉ **3 cái đầu mỗi bảng**, không phải mọi hashtag đang lên. `so_bai`, `luot_xem`: báo cáo không ghi của kỳ nào — nói «không ghi của kỳ nào», đừng gắn «trong 7 ngày» hay «hôm nay». `do_hot_tung_ngay` là điểm 0–100 từng ngày của riêng hashtag đó: chỉ để xem nó lên hay xuống qua các ngày, **không dùng để so hashtag này với hashtag kia** (so thì dùng `luot_xem`, `so_bai`). `xu_huong_cuoi_ky` so ngày cuối với **mức trung bình** các ngày trước đó trong bảng (chênh quá 20 % mới ghi tăng / giảm, còn lại là đi ngang): nói «ngày gần nhất cao hơn / thấp hơn / ngang mức trung bình mấy ngày trước», không nói «sẽ còn tăng». Ngày cuối có thể thấp hơn ngày sát trước mà nhãn vẫn ghi «đang tăng» — đừng viết «tăng liên tục». Hashtag đầu bảng có thể là chiến dịch của sàn hoặc của một nhãn hàng (tên có chữ kiểu «sale», «live», hoặc tên nhãn): nhận ra từ tên thì nói «theo tên thì giống hashtag chiến dịch — tôi đoán từ tên, báo cáo không ghi», đừng trình bày như một chủ đề nội dung |
| `video_dang_hot` | Mẫu video lấy từ trang «Dành cho bạn» lúc chạy: `mo_ta`, `tac_gia`, `luot_xem`, `tuong_tac`, `thoi_luong_giay`, `nhac`, `gan_gio_hang`, `quoc_gia_video`, `dang_luc`, `link` | **Không phải bảng xếp hạng.** Xem `dang_luc`: có video đăng từ nhiều tuần, nhiều tháng trước — nêu ngày đăng, đừng gọi là «video mới hôm nay». `luot_xem` của video là tổng từ ngày đăng (video cũ dễ đứng đầu), không phải lượt xem của hôm nay hay tuần này. `quoc_gia_video` khác nước đã chọn là video nước ngoài: không tính vào nhận định về thị trường trong nước. `tuong_tac` = (thích + bình luận + chia sẻ) chia lượt xem. Chú thích tiếng nước ngoài thì dịch. **Video nói về gì chỉ biết được ở các video được liệt kê** (các video còn lại của mẫu chỉ có trong số đếm): viết «trong … video được liệt kê, không video nào về mỹ phẩm», không viết thay cho cả mẫu. Có gửi `nganh` thì mẫu video **vẫn là của mọi ngành** — không gọi là «video của ngành …». Mẫu thường lẫn nhiều video giải trí: một video nhiều lượt xem **không cho biết món nào đang bán chạy** |
| `hg_nhan_xet` | Số HG đếm trên **cả mẫu** (`so_video_trong_mau` — bằng hoặc nhiều hơn số video được liệt kê): `video_cua_nuoc_nay`, `tuong_tac_o_giua`, `do_dai_video`, `hashtag_dung_nhieu_trong_video_hot`, `nhac_dung_nhieu`, `video_gan_gio_hang`, `video_quang_cao_tra_tien` | Là số đếm, dùng được — luôn kèm mẫu số («6 trong 11 video»). **Xem `video_cua_nuoc_nay` trước:** dạng «11/11» là mẫu chỉ gồm video của nước đã chọn. Dạng «11/26» (số trước nhỏ hơn số sau) là lượt chưa lọc: mọi số đếm ở ô này **gộp cả video nước ngoài** — nói đúng «11 trong 26 video là của nước đó», và không dùng các số đếm này làm điểm chung của riêng nước đó. Có gửi `nganh` thì các số này vẫn tính trên video của mọi ngành. `tuong_tac_o_giua` là số đứng giữa: viết «một nửa số video có tỉ lệ tương tác từ … trở lên», không gọi là «trung bình». `video_gan_gio_hang`, `video_quang_cao_tra_tien` dạng «0/18»: mẫu số là số video mà dữ liệu có ghi chuyện gắn giỏ hàng (nhỏ hơn cả mẫu) — nói «… trong 18 video có ghi». Hashtag kiểu #xuhuong, #fyp, #trending, #foryou là thẻ người đăng gắn để mong lên xu hướng, không phải chủ đề. Một hashtag hay bài nhạc lặp ở 2–3 video trong vài chục video **chưa phải trend**, có thể chỉ là mấy video của cùng một kênh — nói đúng «lặp ở … trong … video». Nhạc ghi «âm thanh gốc - …» là tiếng do chính kênh đó thu, không phải một bài nhạc |
| `phan_tam_thieu`, `ghi_chu` | Phần không lấy được; giới hạn dữ liệu | Nói lại cho người dùng |

### Bản tin tuần (`hgbantin`)

| Trường | Là gì | Lưu ý |
|---|---|---|
| `ban_tin` | Ngành và ngày lấy dữ liệu | Luôn ghi lại. Kết quả chỉ ghi ngày, không ghi giờ |
| `tu_khoa_nganh_tren_google` | Mức quan tâm trên Google ở Việt Nam của **từng từ theo dõi** (tối đa 5): `diem_4_tuan_gan_nhat`, `diem_trung_binh_12_thang`, `tuan_vua_qua_so_voi_4_tuan_truoc`, `xu_huong` | Chỉ là mấy từ đó, **không phải cả ngành** — nêu tên từng từ. Điểm 0–100 là mức tương đối, so được giữa các từ trong lượt này, không phải số lượt tìm. **Tên của các con số này là «mức quan tâm trên Google» (hoặc «điểm quan tâm») — gọi đúng tên đó ở mọi chỗ, kể cả câu mở; không viết «lượt tìm», «số người tìm», «lượng tìm kiếm».** `xu_huong` «đang lên» / «đang xuống» = 4 tuần gần nhất cao / thấp hơn trung bình 12 tháng của chính từ đó từ 30 %. `tuan_vua_qua_so_voi_4_tuan_truoc` là phép so khác (tuần vừa rồi với 4 tuần trước nó), có thể trái chiều với `xu_huong`: nêu số nào thì nói rõ so với gì. Các từ được chấm chung một thang, nên một từ rất rộng (kiểu «son») kéo điểm các từ còn lại xuống thấp. Từ có điểm dưới chừng 10: cả phần trăm tăng giảm lẫn nhãn «đang lên» / «đang xuống» đều kém chắc — nêu thì kèm điểm («điểm 2 so với 4, thang 100») và không lấy làm căn cứ chính để khuyên. Từ mang nhãn «quá ít người tìm để so»: đừng chép chữ đó; nói «mức quan tâm quá thấp so với các từ còn lại trong lượt này nên không so được lên hay xuống» — không có nghĩa là không ai quan tâm |
| `hashtag_tiktok_7_ngay` | 3 hashtag đầu ngành ở Việt Nam, bảng 7 ngày | Đọc như bảng hashtag ở trên |
| `tiktok_shop_ban_chay` | Món ở trang kết quả đầu TikTok Shop Việt Nam cho **MỘT từ** — ghi ở `tu_khoa` của khối này (HG chọn từ đang lên; không có từ nào đang lên thì lấy từ có điểm cao nhất): `so_mon_tim_thay`, `gia_dang_ban`, `mon_ban_chay_nhat` (mỗi món: `ten`, `shop`, `da_ban`, giá đang bán, `gia_goc`, `link`) | Nói rõ đây là món của từ nào và là món **trong … món ở trang kết quả đầu** (`so_mon_tim_thay`) — không phải «món bán chạy nhất ngành», không phải bảng xếp hạng cả sàn. `da_ban` = số đã bán sàn hiển thị, cộng dồn từ trước tới nay, không phải của tuần này. `gia_goc` = giá niêm yết gạch ngang, không phải giá khách trả. Khối `gia_dang_ban` có `thap_nhat`, `trung_binh`, `cao_nhat` tính trên `so_mon_tinh` món, sau khi HG bỏ món giá sốc (`bo_gia_soc`: giá đang bán dưới 10 % giá niêm yết, kiểu 1.000 đ để kéo khách) và món giá lệch hẳn khỏi số đông (`bo_gia_lech`). Nêu giá trung bình thì nói kèm tính trên mấy món; dưới 5 món thì nói thêm «quá ít món để coi là giá chung» |
| `quang_cao_tiktok_hieu_qua` | Mẫu quảng cáo TikTok 30 ngày: `thi_truong`, `tu_khoa`, `nhom`, `mau` (mỗi mẫu: `chu`, `thoi_luong_giay`, `khung`, `muc_tieu`) | **Của nhiều nước, không chọn riêng được Việt Nam**; tìm theo một từ tiếng Anh HG chọn cho ngành (ghi ở `tu_khoa` của khối này, có thể hẹp hơn cả ngành — nêu từ đó). Chỉ dùng để xem **hình thức**: dài bao nhiêu giây, khung dọc hay ngang, mục tiêu gì. Không viết «quảng cáo ở Việt Nam đang…». «Hiệu quả» là TikTok tự xếp, không kèm số tiền hay số đơn. Chữ quảng cáo tiếng nước ngoài thì dịch |
| `hg_nhan_xet` | Câu máy ghép sẵn | **Đừng chép** (máy viết «được tìm nhiều nhất»; đúng phải là «có mức quan tâm cao nhất trong … từ theo dõi»). Tự viết lại từ các số |
| `phan_tam_thieu`, `ghi_chu` | Phần không lấy được; giới hạn dữ liệu | Nói lại cho người dùng |

**Bản tin không so với tuần trước:** mỗi lượt là một ảnh chụp. Người dùng dán bản tin tuần trước vào thì so giúp; không có thì không viết «tăng so với tuần trước» cho hashtag hay món bán chạy.

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

Riêng với trend:

- **«Đang hot» là gì thì nói đúng thế:** hashtag = đứng đầu bảng 7 ngày; video = có trong mẫu trang «Dành cho bạn» lúc chạy. Không viết «hot nhất hôm nay», «trend của tuần» cho một video hay một bài nhạc.
- **Không đoán tương lai:** không viết «sẽ lên», «sắp thành trend», «làm theo là có đơn».
- **Được gợi ý, trong đúng phạm vi:** hai báo cáo này đủ để gợi ý **nên thử làm video kiểu nào** hoặc **nên để mắt tới từ khoá nào**; không đủ để khuyên nhập món nào — họ hỏi vậy thì nói bước sau (xem kỹ một món) mới trả lời được. Ý tưởng video là nhận định của bạn: chỉ ra video hay số đếm đỡ cho nó.
- Mẫu còn dưới chừng 10 video của nước đã chọn, hoặc không có gì lặp lại: chỉ liệt kê tham khảo và nói «chưa đủ để rút ra kiểu video nên làm».

**Phần cách viết** — người đọc là chủ shop đang bận, đọc trên điện thoại:

- **Dòng đầu nói giá lượt chạy** (như mục «Trước khi chạy»), **ngay sau đó là câu mở trả lời thẳng điều họ hỏi**, kèm một hai con số chính. Họ hỏi «nên hay không» thì câu mở nói luôn bạn nghiêng về phía nào, mở bằng «Theo tôi».
- **Mỗi con số, mỗi ý chỉ nêu một lần.** Số đã nêu ở câu mở thì bên dưới không nêu lại; phần số liệu chỉ thêm số chưa nêu. Chỉ đưa số giúp họ quyết; bảng chỉ dùng khi xếp từ 3 mục cạnh nhau. Câu trả lời cho một lượt chạy thường gọn trong 300–450 chữ — dài hơn là đang lặp.
- **Lời thường, không dùng chữ của máy.** Không viết tên trường. Số bán nói kèm kỳ đúng như bảng trên ghi («đã bán 12.000 cái từ trước tới nay», «trong tháng», hoặc «không ghi của kỳ nào») thay cho «cộng dồn»; «giá niêm yết (giá gạch ngang)» thay cho «giá gốc» (dễ nhầm với giá nhập); «người ta hay tìm kèm: …» thay cho «cụm gõ kèm»; «tôi mới xem được 4 trong 30 mẫu» thay cho «kết quả bị cắt». Điểm Google nói bằng so sánh trước, điểm để trong ngoặc, và **gọi đúng tên là «mức quan tâm trên Google»** — không gọi là «lượt tìm», «số người tìm»: «mức quan tâm trên Google 4 tuần gần đây chỉ bằng khoảng một phần tư mức trung bình cả năm (điểm 6 so với 22, thang 100)». Chữ và nhãn tiếng nước ngoài thì dịch.
- **Lưu ý về giới hạn dữ liệu gom vào MỘT dòng cuối** («Lưu ý khi đọc số: …»): mỗi ý một lần, chỉ ý dính tới con số bạn đã dùng. Riêng lưu ý làm đổi nghĩa con số ngay tại chỗ thì viết liền con số bằng vài chữ («109.000 đ, niêm yết 199.000 đ»; «12 ¥ một cái, chưa gồm phí về Việt Nam») và không nhắc lại ở cuối.
- **Kết bằng MỘT việc nên làm tiếp**, một câu; cần chạy thêm thì nêu giá và chờ họ đồng ý.

**Bố cục cho báo cáo trend TikTok:**

1. **Câu mở** — lúc này TikTok ở nước đó đang đẩy gì: hashtag đứng đầu bảng (tên, lượt xem) và một điểm chung đếm được của mẫu video trong nước (vd «6 trong 11 video của Việt Nam dài dưới 15 giây»). Lượt chưa lọc video trong nước thì nói rõ đó là số của mẫu lẫn cả video nước ngoài. Họ hỏi «nên làm video kiểu gì» thì mở bằng «Theo tôi» + một kiểu video kèm số đếm đỡ cho nó; chưa đủ thì nói «chưa đủ để gợi ý».
2. **Hashtag** — các hashtag đầu bảng: tên, lượt xem, số bài, ngày gần nhất cao hơn, thấp hơn hay ngang mức trung bình mấy ngày trước.
3. **Video đang được đẩy** — 3–5 video của nước đã chọn: video về gì (một câu), kênh, lượt xem, tỉ lệ tương tác, dài mấy giây, đăng ngày nào, link.
4. **Điểm chung đếm được** — số chưa nêu ở trên: độ dài, hashtag / nhạc lặp lại, bao nhiêu video gắn giỏ hàng; mỗi số kèm mẫu số.
5. **Ý tưởng nên thử** — chọn MỘT trong hai: nêu MỘT ý theo bạn (sát với thứ họ bán nếu họ đã nói, chỉ rõ dựa trên video hay số đếm nào), **hoặc** nói thẳng «chưa đủ để gợi ý kiểu video» và cần xem thêm gì. Đừng vừa nêu ý vừa nói chưa đủ.
6. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Với báo cáo này thường là: hashtag là 3 cái đầu bảng 7 ngày · video là mẫu … video trên trang «Dành cho bạn» lúc chạy, trong đó … video của nước đó, không phải bảng xếp hạng, không lọc theo ngành · chạy lại lúc khác sẽ ra mẫu khác.
7. **Việc nên làm tiếp** — một câu: thường là chép lời một video vừa nêu để xem họ mở đầu thế nào («Chép lời một video TikTok», `hgjs2p3p`, ~10 token), hoặc bản tin tuần của ngành họ bán (`hgbantin`, ~22–29 token) — lượt thêm, nêu giá và chờ họ đồng ý.

**Bố cục cho bản tin tuần:**

1. **Câu mở** — trong các từ theo dõi, từ nào đang lên, từ nào đang xuống (không có thì nói «không từ nào đang lên»; từ có điểm dưới chừng 10 mà nêu ở đây thì kèm luôn điểm); hashtag đứng đầu ngành; món đã bán nhiều nhất cho từ «…» trong các món ở trang kết quả đầu.
2. **Google** — từng từ: lên / xuống / đi ngang, nói bằng so sánh, điểm để trong ngoặc.
3. **TikTok** — 3 hashtag đầu ngành.
4. **TikTok Shop cho từ «…»** — 3–5 món: tên đúng, shop, đã bán bao nhiêu từ trước tới nay, giá đang bán (niêm yết trong ngoặc), link.
5. **Mẫu quảng cáo** (nếu có) — hình thức hay gặp trong mẫu, kèm «… trong … mẫu»; một câu trích đã dịch.
6. **Việc nên làm tuần này** — theo bạn, MỘT việc, dựa trên con số nào; không có gì lên xuống rõ thì nói «tuần này chưa thấy gì đổi rõ trong các từ theo dõi».
7. **Dòng lưu ý cuối** gồm: lấy lúc nào (kết quả không ghi giờ thì nói vậy) · đây là dữ liệu công khai HG Trend lấy lúc chạy · phạm vi của những con số đã dùng (theo cột «Lưu ý» ở bảng trên) · phần nào lần này không lấy được. Với bản tin này thường là: chỉ theo dõi … từ, không phải cả ngành · điểm Google là mức so giữa các từ trong lượt này, không phải số lượt tìm · món bán chạy là trong … món ở trang kết quả đầu TikTok Shop, số đã bán tính từ trước tới nay · hashtag là 3 cái đầu bảng 7 ngày của ngành · mẫu quảng cáo là của nhiều nước · bản tin không so với tuần trước.
8. **Việc nên làm tiếp** — một câu: thường là xem kỹ món hoặc từ đang lên bằng «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`, ~27–115 token), hoặc chạy lại bản tin với các từ sát hàng của họ — lượt thêm, nêu giá và chờ họ đồng ý.
