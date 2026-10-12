# Template 20/10: "Bó hoa bí mật" 🌸

Trang web một file (`index.html`), chạy được trên GitHub Pages, ít ảnh nhưng nhiều bất ngờ.
**Nhạc đã được nhúng sẵn trong file** và có sẵn 6 ảnh minh họa, nên tải lên là xem được ngay.

## Người xem sẽ gặp gì

1. **Thiệp 3D**: một tấm thiệp hồng đóng kín, chạm vào thì bìa thiệp lật mở và nhạc bắt đầu. Nếu người xem không biết phải chạm, **thiệp tự mở sau 5 giây** (đổi số giây hoặc tắt bằng `autoOpenSeconds` trong `CONFIG`).
2. **Trang đầu**: 1 ảnh chính trong khung vòm, nhãn tròn xoay "Chúc mừng ngày Phụ nữ Việt Nam", số ngày bên nhau (hoặc đếm ngược tới 20/10).
3. **Khung hình**: 4 thẻ ảnh, chạm để lật sang mặt sau đọc lời nhắn viết tay.
4. **Bó hoa bí mật**: 6 bông hoa gom thành một bó có giấy gói và nơ hồng, chạm vào từng bông để nó nở ra một bất ngờ khác nhau:
   - Bông 1: **Lời chúc** (gõ chữ dần, có nút "Lời chúc khác")
   - Bông 2: **Ảnh cào**, phải cào lớp phủ bằng ngón tay mới thấy ảnh
   - Bông 3: **Phiếu đặc quyền**, bấm "Dùng phiếu" thì đóng dấu "Đã nhận"
   - Bông 4: **Hũ lý do**, mỗi lần rút ra một lý do ngẫu nhiên
   - Bông 5: **Tâm trạng hôm nay**, chọn một tâm trạng sẽ có lời đáp riêng
   - Bông 6 (vàng, nằm giữa phía trên): **Lá thư**, bị khóa cho tới khi mở đủ 5 bông kia
5. **Hồi âm**: người nhận chọn biểu tượng, viết vài dòng rồi gửi thẳng vào khung chat Zalo của bạn.
6. **Lời kết** và nút về đầu trang.

Tổng chỉ cần **6 ảnh**: 1 ảnh chính, 4 ảnh thẻ lật, 1 ảnh cào.

## Cấu trúc thư mục (chỉ cần index.html và images)

```
tên-repo/
├── index.html
└── images/
    ├── anh-chinh.jpg        (ảnh chính ở trang đầu, nên là ảnh dọc)
    ├── anh-1.jpg ... anh-4.jpg   (4 thẻ lật)
    └── bat-ngo.jpg          (ảnh trong bông hoa cào)
```

Thư mục `images/` đã có sẵn 6 ảnh minh họa pastel mình tự vẽ (bó hoa, đồng cỏ, khinh khí cầu, bàn trà, vòng hoa trái tim, hộp quà), nên trang xem được ngay. Đây là tranh vẽ, không phải ảnh chụp, và dùng thoải mái, không vướng bản quyền.

**Thay bằng ảnh thật của bạn:** đặt ảnh mới vào `images/` với đúng tên file cũ (`anh-chinh.jpg`, `anh-1.jpg` đến `anh-4.jpg`, `bat-ngo.jpg`) để ghi đè, hoặc đổi đường dẫn trong `CONFIG`. Ảnh nên cắt dọc tỉ lệ 3:4 (ảnh `bat-ngo.jpg` tỉ lệ 4:5). Thiếu ảnh nào thì chỗ đó hiện khung hoa tạm.

## Nhạc

- Bản nhạc mặc định là giai điệu hộp nhạc mình tự soạn (khoảng 50 giây, tự lặp lại), đã nằm trong `index.html`. Dùng thoải mái, không vướng bản quyền.
- Muốn dùng bài hát của bạn: bỏ file vào thư mục `music/` (ví dụ `music/bai-hat.mp3`), rồi trong `CONFIG` sửa `musicSrc: "music/bai-hat.mp3"` và `musicTitle`. Nhớ chọn bài bạn có quyền dùng, vì repo public thì ai cũng tải được file.
- File `music/nhac.mp3` đi kèm chỉ là bản sao của bài nhúng sẵn, không cần upload.

## Chỉnh nội dung

Mở `index.html`, tìm khối `CONFIG` ở đầu phần `<script>` thứ hai (ngay sau đoạn dữ liệu nhạc rất dài):

| Muốn đổi | Sửa ở |
|---|---|
| Chế độ mặc định | `mode: "ban"` hoặc `"me"` |
| Thiệp tự mở sau mấy giây | `autoOpenSeconds: 5` (đặt `0` để tắt) |
| Nhạc | `musicSrc`, `musicTitle` |
| Ngày bên nhau | `since: "2025-03-14"` (chế độ `me`: ngày sinh của bạn) |
| Zalo nhận hồi âm | `zalo: "0912345678"` (số điện thoại hoặc ID Zalo) |
| Tên ảnh, nhãn thẻ | `heroPhoto`, `film`, `bloomPhoto` |
| Lời chúc, phiếu, lý do, thư, lời đáp | trong `modes.ban` hoặc `modes.me` |

Trong chữ: `{to}` là người nhận, `{To}` là người nhận viết hoa chữ đầu, `{from}` là người gửi.

## Hồi âm qua Zalo

Khi bạn điền `zalo`, nút ở cuối trang đổi thành **Gửi qua Zalo**. Khi người nhận bấm:
1. Lời nhắn được chép vào bộ nhớ tạm (kèm biểu tượng tâm trạng và tên người nhận).
2. Trang mở khung chat Zalo của bạn (`https://zalo.me/số-điện-thoại`).
3. Người nhận chỉ việc **dán** vào khung chat rồi bấm gửi.

Lưu ý:
- Link Zalo không hỗ trợ điền sẵn nội dung, nên bước dán là bắt buộc. Trang có sẵn nút "Mở lại khung chat Zalo" phòng khi trình duyệt chặn cửa sổ mới.
- Người nhận cần có Zalo. Nếu bạn dùng số điện thoại, tài khoản của bạn cần cho phép người khác tìm bằng số điện thoại (Cài đặt Zalo, phần Quyền riêng tư).
- Nếu không điền `zalo`, nút sẽ mở khung chia sẻ trên điện thoại (hoặc chép lời nhắn trên máy tính) để người nhận tự chọn nơi gửi.
- Những lời đã viết cũng được lưu trong trình duyệt của người nhận (`localStorage`), bạn không xem được phần này.

## Đổi tên người nhận và Zalo bằng link (không cần sửa code)

```
https://tên-bạn.github.io/tên-repo/?to=Lan&from=Minh&zalo=0912345678
https://tên-bạn.github.io/tên-repo/?mode=me&to=mẹ&from=Bin&zalo=0912345678
```

Nhiều bạn nam có thể dùng chung một trang, mỗi người tự tạo link với tên và số Zalo của mình. Chỉ nhận số điện thoại hoặc ID Zalo, các giá trị khác bị bỏ qua. Số điện thoại nằm trong link nên ai có link cũng thấy được.

## Đưa lên GitHub Pages

1. Tạo repo mới (Public), ví dụ `20-10`.
2. **Add file → Upload files**, kéo thả `index.html` và thư mục `images`, rồi **Commit changes**.
3. **Settings → Pages**: Branch chọn `main`, thư mục `/ (root)`, bấm **Save**.
4. Chờ 1–2 phút, link có dạng `https://tên-bạn.github.io/20-10/`.

## Lưu ý

- Nhạc chỉ tự phát được khi người xem đã chạm vào trang. Nếu thiệp tự mở sau 5 giây mà người xem chưa chạm, trình duyệt sẽ chặn nhạc, và trang nhắc họ chạm nút nhạc ở góc trên để bật. Đó là quy định của trình duyệt, không tránh được.
- Nên nén ảnh dưới 500KB mỗi ảnh. Tên file phân biệt chữ hoa chữ thường.
- Các bản trước vẫn còn: `phien-ban-cuon-truyen.html` (nhiều ảnh, cuộn dọc) và `phien-ban-don-gian.html`.
