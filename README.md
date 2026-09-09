# Itadakimasu — Everyday Japan Eats（日本の食を海外向けに紹介するサイト）

英語で、日本の日常の食事・食品・食文化を紹介する静的サイトです。
サーバー不要。HTMLファイルをそのまま GitHub Pages で公開できます。

## フォルダの中身

```
index.html              トップページ（記事一覧）
about.html              サイトについて
articles/               記事（1本＝1ファイル）
  japanese-breakfast.html
  konbini-guide.html
  onigiri.html
css/style.css           見た目の設定（全ページ共通）
images/                 写真を入れる場所（いまは空）
```

## 記事を1本ふやす手順

1. `articles/` の中の既存ファイルを1つコピーして、名前を変える（例：`miso-soup.html`）
2. `<title>`、見出し、本文を書き換える
3. `index.html` のカード（`<article class="card">` のかたまり）を1つコピーして、リンク先とタイトルを新しい記事に変える

## 写真を入れる手順

1. 写真を `images/` に入れる（ファイル名は英数字で。例：`breakfast-01.jpg`）
2. 記事の中の `<div class="photo">Photo: ...</div>` を、次のように書き換える

```html
<figure>
  <img src="../images/breakfast-01.jpg" alt="A weekday breakfast: rice, miso soup and a fried egg">
  <figcaption>A Tuesday breakfast at home.</figcaption>
</figure>
```

### 見出し横の小さな写真（朝ごはん記事の「ご飯」「味噌汁」など）

記事の中の次の部分を探して、`Photo: rice` の行を `<img>` に置き換える。

```html
<div class="item-photo"><img src="../images/rice.jpg" alt="A bowl of white rice"></div>
```

写真は正方形に切り抜かれて表示されるので、真ん中に料理が来るように撮ると収まりがよい。

※ 写真は自分で撮ったものだけを使う。ネットから拾った画像は使わない。

## 公開のしかた（GitHub Pages）

GitHub にこのフォルダをプッシュし、リポジトリの Settings → Pages で
「Deploy from a branch」→ `main` / `/ (root)` を選ぶと、数分後に公開されます。
