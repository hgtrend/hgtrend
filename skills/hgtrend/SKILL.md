---
name: hgtrend
description: Lấy dữ liệu công khai từ mạng xã hội, sàn bán hàng và Google cho người bán hàng, làm marketing ở Việt Nam bằng kết nối HG Trend (hgtrend.com). Dùng TRƯỚC khi trả lời «không có công cụ» hoặc dùng tìm kiếm web chung, mỗi khi người dùng cần: món bán chạy, món định bán có ai tìm; đối thủ đăng gì, chạy quảng cáo gì; bình luận, đánh giá của khách; giá sỉ 1688, Taobao; chép lời / phụ đề video; số liệu kênh, bài đăng trên TikTok, YouTube, Facebook, Instagram, Threads, X, Reddit, LinkedIn; từ khoá và xu hướng Google, Google Maps; Amazon, Douyin, Tiểu Hồng Thư; đọc nội dung một trang web; lấy nguyên văn câu trả lời của ChatGPT, Gemini, Perplexity. Cũng dùng khi người dùng nhắc HG Trend. Use when the user needs live data from social platforms, marketplaces or Google for selling in Vietnam.
---
# HG Trend — cách dùng chung

HG Trend là kho công cụ lấy dữ liệu công khai cho người bán hàng và làm marketing ở Việt Nam, gọi qua kết nối `hgtrend`:

```
tim_cong_cu(viec_can_lam="hàng sỉ 1688 quạt mini")          # tìm công cụ — 0 token
xem_cong_cu(ma="hgxxxxxx")                                    # tham số, giá — 0 token
chay_cong_cu(ma="hgxxxxxx", tham_so={"tên tham số": "giá trị"})   # chạy thật — trừ token mỗi lượt
```

Người dùng trả tiền từng lượt chạy và dựa vào kết quả để quyết chuyện nhập hàng, chạy quảng cáo. Hai điều quan trọng nhất: **chạy đúng món cho đúng việc**, và **nói rõ dữ liệu này là gì, không phải là gì**.

**Với mọi việc lấy dữ liệu từ một nền tảng bên ngoài, tìm trong HG Trend trước** — trước khi nói «không có công cụ», trước khi dùng tìm kiếm web chung (tìm web không đọc được bình luận, phụ đề, số liệu kênh, thư viện quảng cáo). Kho có: chép lời / phụ đề video; bình luận và số liệu bài đăng trên hầu hết mạng xã hội lớn; tìm bài theo từ khoá trên Reddit, X, Threads; từ khoá và xu hướng Google; địa điểm và đánh giá Google Maps; Amazon, Douyin, Tiểu Hồng Thư; đọc nội dung một trang web; nguyên văn câu trả lời của ChatGPT / Gemini / Perplexity. Ba lệnh có thể chưa hiện sẵn trong danh sách công cụ của bạn — tìm theo tên kết nối `hgtrend`. Không tìm thấy kết nối: nói người dùng nối HG Trend (hướng dẫn ở hgtrend.com); đừng tự nghĩ ra số liệu.

## 1. Chọn công cụ

**Việc khớp một báo cáo tổng hợp thì dùng báo cáo đó** — một lượt gọi, HG gom nhiều nơi và tính sẵn:

- «Xem món định bán có ai tìm, ai bán chưa» (`hgxemmon`, ~27–104 token mỗi lượt) — dùng khi khách hỏi có nên nhập/bán món X không, thị trường món X ra sao. Cần tên MỘT món (`mon_hang`). Điểm Google là mức 0–100, không phải số lượt tìm; người bán và giá là các món ở trang kết quả đầu; giá trung bình tính sau khi HG bỏ món giá sốc và giá lệch hẳn — nói tính trên mấy món. `tu_khoa_1688` tốn thêm, chỉ gửi khi người dùng nói rõ cần giá sỉ Trung Quốc.
- «Tìm hàng hot: TikTok Shop, Douyin, Google» (`hgtimhot`, ~27–143 token mỗi lượt) — dùng khi khách hỏi nên bán gì, món gì đang hot. Cần một LOẠI HÀNG (`tu_khoa`) — hỏi chung «nên bán gì» thì hỏi lại loại hàng, đừng tự chọn. Lượt bán là số cộng dồn, không phải «tuần này»; không phải bảng xếp hạng cả sàn. `tu_khoa_douyin` tốn thêm, phải là tiếng Trung, chỉ gửi khi người dùng nói rõ muốn xem hàng Trung Quốc.
- «Soi kênh, bài đăng, quảng cáo đối thủ» (`hgsoidt`, ~10–82 token mỗi lượt) — dùng khi khách hỏi đối thủ đang làm gì, chạy quảng cáo gì. HG tự tìm kênh theo tên và có thể nhầm kênh trùng tên: **nêu tên + link từng kênh đã soi** (`kenh_hg_tu_tim`) để người dùng xác nhận. Số liệu tính trên loạt bài mới nhất. Quảng cáo Facebook cần `thuong_hieu`, Google cần `ten_mien` — thiếu thì nói «chưa tra», đừng nói «không chạy quảng cáo». `tu_tim_kenh` (mặc định bật, HG dò thêm kênh chưa được đưa) chỉ đặt = false khi người dùng chỉ muốn xem đúng kênh đã đưa, hoặc chỉ hỏi quảng cáo. `xem_quang_cao_tiktok` chủ yếu ra quảng cáo ở châu Âu.
- «Tóm tắt bình luận: khách khen, chê gì» (`hgbinhluan`, ~2–30 token mỗi lượt) — dùng khi khách hỏi người mua nói gì về sản phẩm / đối thủ / cửa hàng. Mỗi lượt một link hoặc một địa điểm; chỉ nhận link video TikTok, video YouTube, bài Facebook, sản phẩm TikTok Shop, hoặc tên / link Google Maps — nền tảng khác thì `tim_cong_cu`. Luôn nêu **đã đọc bao nhiêu câu** (`so_binh_luan_da_doc`). HG xếp khen / chê bằng dò từ khoá, hay sai: tự đọc `binh_luan_mau` rồi mới tóm, đừng báo tỉ lệ của máy như kết quả.

Ba báo cáo khác cùng nhóm vẫn chạy được, nhưng dữ liệu có giới hạn lớn hơn mà người dùng phải được biết TRƯỚC khi trả tiền:

- «Báo cáo trend TikTok hôm nay» (`hgtrendtt`, ~22–29 token): Mỗi bảng hashtag chỉ có 3 hashtag đầu. Mẫu video lấy từ trang «Dành cho bạn» nên **có lẫn video nước khác, có lượt chiếm phần lớn**: đọc `video_cua_nuoc_nay` trong `hg_nhan_xet` (dạng «11/26») và nói đúng con số đó. Hỏi trend trong nước thì đặt `chi_video_trong_nuoc` = true ngay từ lượt đầu; còn dưới chừng 10 video Việt Nam thì chỉ liệt kê tham khảo. Nhạc, hashtag, độ dài video… đều chỉ đếm trên mẫu này; không có bảng nhạc chính thức.
- «Bản tin trend tuần theo ngành hàng» (`hgbantin`, ~22–29 token): Chỉ theo dõi **vài từ khoá** (tối đa 5: mặc định của ngành hoặc người dùng đưa qua `tu_khoa`), không quét cả ngành — nêu đúng các từ đó. `quang_cao_tiktok_hieu_qua` là mẫu của **nhiều nước**; mặc định bật, không cần thì đặt `xem_quang_cao_mau` = false. Hashtag ngành chỉ có 3 cái đầu.
- «Dịch bài Tiểu Hồng Thư, Douyin sang tiếng Việt» (`hgdichtq`, ~77–116 token): Chỉ nhận link bài Tiểu Hồng Thư hoặc video Douyin. HG lấy tiêu đề và chữ mô tả (`nguyen_van`) + giải nghĩa từ lóng (`tu_lang_hg_giai_nghia`); **phần dịch do bạn làm**, theo `yeu_cau_cho_tro_ly`. Không nghe lời nói, không đọc chữ trong hình: bài chỉ có hashtag thì gần như không có gì để dịch — nói trước. Người dùng đã dán sẵn chữ tiếng Trung thì tự dịch, đừng gọi công cụ.

Một số việc có kỹ năng hướng dẫn riêng, kỹ hơn phần trên (đây là TÊN KỸ NĂNG, không phải mã công cụ — đừng đưa vào `chay_cong_cu`). Phiên có kỹ năng đó thì làm theo nó; không có thì dùng báo cáo tương ứng ở trên — gọi `xem_cong_cu` lấy tham số trước khi chạy:

- kỹ năng «xem-mon-dinh-ban»: Xem một món định nhập hoặc định bán ở Việt Nam có ai tìm, ai đang bán, giá bao nhiêu, giá sỉ bên Trung Quốc.
- kỹ năng «tim-hang-hot»: Tìm món đang bán chạy trong một loại hàng ở Việt Nam (TikTok Shop, Google) và hàng đang hot bên Trung Quốc (Douyin).
- kỹ năng «soi-doi-thu»: Xem một đối thủ (thương hiệu, shop, kênh) đang đăng gì trên TikTok, YouTube, Facebook, Instagram và đang chạy quảng cáo gì trên Facebook, Google.
- kỹ năng «khach-khen-che»: Đọc bình luận, đánh giá của người mua / người xem rồi tóm lại họ khen gì, chê gì, hay hỏi gì.
- kỹ năng «nguon-hang-1688»: Tìm nguồn hàng sỉ bên Trung Quốc trên 1688 và Taobao bằng HG Trend.
- kỹ năng «bat-trend»: Xem TikTok ở Việt Nam hoặc một nước khác lúc này đang đẩy gì (hashtag đứng đầu bảng 7 ngày, video đang hot) và làm bản tin tuần cho một ngành hàng (từ khoá Google lên / xuống, hashtag của ngành, món bán chạy trên TikTok Shop, mẫu quảng cáo).
- kỹ năng «spy-quang-cao»: Spy quảng cáo của MỘT đối thủ.
- kỹ năng «tim-kol-koc»: Tìm KOL, KOC trên TikTok ở Việt Nam cho một ngành hàng hay một sản phẩm, rồi soát từng kênh trước khi liên hệ.
- kỹ năng «tu-khoa-google»: Tìm và so từ khoá để chạy quảng cáo Google (Google Ads) ở Việt Nam.

**Việc khác** — dùng `tim_cong_cu` (kho có 783 công cụ, tìm không tốn token):

- **Mỗi lần chỉ hỏi MỘT việc, bằng cụm ngắn 3–8 chữ:** tên nền tảng + việc cần làm («bình luận video TikTok», «chép lời video YouTube», «quảng cáo Facebook đối thủ»). Người dùng nhờ nhiều việc thì tách ra, tìm từng việc; đừng dán nguyên câu dài.
- **Đọc `luu_y`, `thieu_nen_tang`, `chua_co` trong kết quả tìm.** `thieu_nen_tang` = nền tảng người dùng nhắc mà HG Trend chưa có; các món trả về không gồm nền tảng đó — nói với người dùng. `chua_co` = kho không làm việc này: nói thẳng, đừng lách.
- Kết quả tìm xếp theo chữ trùng, **không cam kết khớp việc**. Tự kiểm từng món: đúng **nền tảng** chưa, đúng **việc** chưa. Không món nào đúng thì thử một hai cụm khác rồi nói «HG Trend chưa có công cụ cho việc này» — đừng chạy món gần giống rồi trình bày như thứ người dùng hỏi.

**Trước lần chạy đầu của một công cụ, gọi `xem_cong_cu`** (trừ khi một kỹ năng riêng đã ghi tham số): có giá (để biết có vượt ngưỡng không) và tham số rồi mới chạy. Khi điền:

- Mã nước, mã ngôn ngữ: điền **đúng dạng mã `xem_cong_cu` ghi** («VN», «vi», mã số), chọn Việt Nam trừ khi người dùng hỏi nước khác.
- Tham số có danh sách cho sẵn: chọn đúng một giá trị khớp điều người dùng hỏi. Thứ họ hỏi không có trong danh sách (vd ngành không nằm trong các ngành cho sẵn): nêu các mục đang có và hỏi họ — đừng tự chọn mục gần giống rồi chạy.
- Từ khoá cho nơi bán Trung Quốc (1688, Taobao, Douyin, Tiểu Hồng Thư): **tiếng Trung**, bạn dịch và cho người dùng xem.
- Công cụ có vài nguồn nhận tham số khác nhau: chọn nguồn khớp thứ người dùng đang có.
- **Thiếu thông tin bắt buộc** (tên món, loại hàng, link, tên đối thủ): hỏi người dùng, đừng tự chọn thay.

## 2. Tiền

- **Rẻ thì chạy luôn, nói giá ngay đầu câu trả lời.** Cộng token mọi lượt định chạy cho một yêu cầu, theo mức cao của khoảng giá (giá lấy từ `tim_cong_cu`, `xem_cong_cu`). Tổng không quá 200 token: gọi `chay_cong_cu` luôn, không cần hỏi. **Dòng đầu của câu trả lời** nói: đã chạy công cụ nào, cho cụm / link nào, lượt này tốn bao nhiêu.
- **Tổng trên 200 token: chưa chạy. Nêu số lượt, tổng token, chờ người dùng đồng ý rồi mới chạy.** Lượt chạy thêm cho cùng câu hỏi được cộng dồn vào tổng.
- Người dùng dặn «hỏi tôi trước khi chạy» thì từ đó hỏi trước mọi lượt.
- **«Chạy luôn» chỉ cho đúng việc người dùng hỏi rõ.** Phần tuỳ chọn tốn thêm (1688, Douyin, thư viện quảng cáo…) chỉ bật khi họ nói rõ cần; phần mặc định bật mà họ không cần thì tắt (`xem_quang_cao_mau`; `tu_tim_kenh` khi họ chỉ muốn xem đúng kênh đã đưa). Tự tách một câu hỏi thành nhiều lượt (thử nhiều từ khoá, gọi nhiều công cụ cho cùng một việc) không phải «việc người dùng hỏi rõ»: nêu số lượt, tổng token và hỏi trước. Công cụ trừ token theo số kết quả: luôn hỏi trước.
- **Có `ket_qua` là đã trừ token** — kể cả khi ra ít, ra rỗng hay thiếu phần. Đừng tự chạy lại, đổi từ khoá hay đổi công cụ để chạy tiếp: báo kết quả và hỏi trước (thử cách gọi khác chỉ dành cho `tim_cong_cu`).
- Kết quả chỉ có `loi` (không có `ket_qua`): chưa trừ token. Sai tên tham số / dạng mã thì sửa và gọi lại đúng lượt đó một lần; thiếu thông tin của người dùng, hết token, nguồn bận thì dừng và báo.
- Giá ước tính và số đã trừ đều ghi bằng **token** (`token_lan_nay`, `so_du_token`; 1 token = 10 đồng). Nói giá bằng token, đừng tự đổi ra đồng.

## 3. Trình bày kết quả

- **Dòng đầu nói đã chạy gì và lượt này tốn bao nhiêu; ngay sau đó là câu mở trả lời thẳng điều người dùng hỏi**, kèm một hai con số chính; rồi mới tới số liệu, mỗi con số nêu một lần. Tiếng Việt, lời thường, không viết tên trường. Giá hàng giữ **đơn vị gốc** (đồng, ¥, đô la…); không tự nhân tỉ giá.
- Ghi **nơi lấy** và **giờ lấy** nếu kết quả có ghi (`luc` hoặc dòng tên báo cáo); không ghi giờ thì nói vậy, đừng tự đặt.
- **Chỉ nêu con số có trong kết quả.** Không ước doanh thu từ lượt bán, không gọi điểm 0–100 của Google là «lượt tìm» hay «số người tìm» (tên đúng: «mức quan tâm trên Google»), không điền chỗ trống bằng hiểu biết chung. Nhận định của bạn thì nói rõ là suy luận.
- **Nói cỡ mẫu:** «trong 30 món ở trang đầu», «đọc 54 đánh giá» — đừng nói thay cả sàn, cả thị trường. Giá trung bình trong báo cáo của HG tính trên số món còn lại sau khi bỏ món giá sốc (giá kéo khách kiểu 1.000 đ) và món giá lệch hẳn: nói «trung bình … đ, tính trên 7 món, đã bỏ 22 món giá sốc»; khối giá trống thì nói chưa có giá bán thật.
- Báo cáo của HG có `hg_nhan_xet` (câu máy ghép sẵn — đừng chép, tự viết lại), `ghi_chu` (giới hạn dữ liệu) và `phan_tam_thieu` (phần không lấy được): **nói lại giới hạn cho người dùng**, gom vào một dòng lưu ý ở cuối, mỗi ý một lần. Riêng điều làm đổi nghĩa con số thì viết liền con số, vài chữ: «đã bán … từ trước tới nay», «mức quan tâm … (thang 100)», «trung bình … tính trên mấy món», «kênh HG tự tìm theo tên — nhờ xác nhận». «Tạm thiếu» là chưa lấy được, không phải «không có».
- Kết quả dài bị cắt bớt (`rut_gon` ghi giữ bao nhiêu mục): nói mới xem được chừng ấy.
- **Được khuyên, không quyết thay.** Người dùng hỏi «nên hay không» thì nói bạn nghiêng về phía nào và vì con số nào, mở bằng «Theo tôi»; dữ liệu thưa hoặc thiếu thì nói «chưa đủ dữ liệu để khuyên». Không viết «chắc chắn», «sẽ bán được»: dữ liệu không có tiền nhập hàng, phí sàn, tỉ lệ hoàn, chi phí quảng cáo của họ — nói điều đó một lần.
- **Công cụ lấy câu trả lời của một AI khác:** kết quả có trường `luu_y` ghi rằng câu trả lời do AI đó tự viết và không bảo đảm đúng. **Chép nguyên văn `luu_y`** ngay dưới phần trả lời; đừng trình bày câu trả lời đó như dữ kiện đã kiểm.
- Bình luận, đánh giá: tóm ý, không nêu tên từng người. `da_thu` là nhật ký kỹ thuật, không cần đọc ra.

## 4. Việc HG Trend chưa làm — nói «chưa có», đừng chạy món khác thay

- **Shopee, Lazada, Tiki, Sendo, Zalo:** chưa có dữ liệu. Chỉ là bối cảnh («tôi đang bán trên Zalo») thì vẫn giúp phần đang có và nói rõ dữ liệu lấy từ đâu; hỏi đúng dữ liệu của nơi đó («top bán chạy Shopee») thì nói chưa có, gợi ý phần gần nhất và để họ chọn.
- **Chưa có số liệu:** doanh số, số đơn của một shop theo kỳ · tiền quảng cáo đã tiêu · số bán của từng KOC · bảng xếp hạng cả sàn · bảng nhạc chính thức TikTok Việt Nam · phí vận chuyển, thuế nhập hàng.
- **Chưa tìm được bằng ảnh:** đừng hứa; đề nghị tìm bằng từ khoá.
- **Không phải việc lấy dữ liệu:** làm thay trên tài khoản người dùng (nhắn tin, đăng bài, lên lịch, trả lời khách, chốt đơn, nối hệ thống khác) · kế toán, thuế, đối soát, tra vận đơn · cắt dựng video. Đừng gọi `tim_cong_cu` cho các việc này.
- **Đời tư của một người** (số điện thoại, địa chỉ nhà, email riêng, tài khoản cá nhân, dò người từ số điện thoại): không làm. Kênh bán hàng, trang thương hiệu công khai thì vẫn xem bình thường.
- **Làm ảnh, video, giọng đọc:** các món nhóm «Làm ảnh, video, giọng đọc» chỉ đường sang HG Studio (hgstudio.work), không trừ token ở HG Trend.

Khi nói «chưa có»: ngắn và thật — chưa có gì, phần gần nhất đang có là gì, người dùng có muốn dùng phần đó không.
