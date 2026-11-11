# hub-games

Game nặng của [Game Hub](https://poke5121999-art.github.io/survivor-web-hub/) (repo
`poke5121999-art/survivor-web-hub`), tách ra repo GitHub Pages riêng ngày 2026-11-10 vì gói Pages của hub
(~1,04 GB) sát trần 1 GB và deploy bị "Timeout reached".

- Mỗi game giữ nguyên cấu trúc cũ ở `games/<id>/`, chạy tại
  `https://poke5121999-art.github.io/hub-games/games/<id>/index.html`.
- Cùng origin `poke5121999-art.github.io` với hub, nên đăng nhập (localStorage `hub.session.v1`), save
  cục bộ và Supabase của hub dùng chung. Script chung của hub (`game-gate.js`, `session.js`,
  `supabase-config.js`, `supabase-auth.js`, `save-sync.js`) nạp bằng đường tuyệt đối
  `/survivor-web-hub/js/...`, không chép sang đây.
- Thẻ game, ảnh thumbnail và `data/games.js` vẫn ở hub; ở hub `games/<id>/index.html` chỉ còn trang
  chuyển hướng sang đây (giữ query/hash).
- Lịch sử trước khi tách nằm trong repo hub (commit 545c5b40 là bản cuối có các thư mục này).

Game ở đây: bazaar (Chợ Phiên), voiddiver (bản three.js cũ; thẻ hub trỏ sang repo voiddiver-webgl),
dredge, toc-do, survivor, kingfall, farmland.

Đổi một game: sửa trong `games/<id>/` của repo này rồi push `main`; nhớ tăng `rev` của game đó trong
`data/games.js` ở hub để trình duyệt lấy HTML mới.
