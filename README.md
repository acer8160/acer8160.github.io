# acer8160.github.io — Your Metronome ブランドサイト

iPhone アプリ **Your Metronome** の公式ランディングページ（日英）。
GitHub Pages の **org サイト**として `https://acer8160.github.io/` のルートで配信する。

## 目的

指名検索（「Your Metronome」）とSNSからの着地点を確保する。記事型 SEO メディアではなく、
**1枚のブランド着地点**であることが設計の意図（2026-07-26 オーナー承認）。

## 構成

| パス | 内容 |
|---|---|
| `index.html` | 日本語ランディングページ（ルート） |
| `en/index.html` | 英語ランディングページ |
| `assets/{ja,en}/*.png` | App Store スクショを 600px 幅へ縮小したもの |
| `assets/icon.png` | アプリアイコン（favicon / OGP 兼用） |
| `demo/index.html` + `demo/practice-video.mp4` | 練習動画録画（v1.1.0）のデモ。App Store フィーチャー申請の補足資料用 |
| `robots.txt` / `sitemap.xml` | クロール用 |
| `.nojekyll` | Jekyll 処理を無効化 |

## `demo/` の扱い

App Store Connect の **Featuring Nomination（補足資料 URL）** から直リンクで参照される前提のページ。
アプリ本体リポの [`docs/store/featuring-nomination.md`](https://github.com/KaedeYamazaki/my-metronome-app/blob/develop/docs/store/featuring-nomination.md) が正本。

- **LP からは導線を張らない**（未公開機能を LP に載せない方針を崩さないため）。
  `meta robots=noindex,nofollow` を入れ、`sitemap.xml` にも追加しない。
- **`robots.txt` で Disallow にしない**。クロールを止めると `noindex` 自体が読まれない。
- 動画は アプリ本体の焼き込みモジュールが書き出した原本そのまま（無編集・再エンコードなし）。

## 既存の legal サイトとの関係

**別リポジトリ `acer8160/legal` はそのまま**（`https://acer8160.github.io/legal/`）。
org サイト（本リポ）とプロジェクトサイト（legal）は共存するため、
アプリ内 `constants/paywall.ts` の規約・プライバシー URL は**変更不要**。

> ⚠️ 本リポに独自ドメインを設定すると `legal` も同ドメイン配下へ移動する。
> その場合 `acer8160.github.io/legal/*` はリダイレクトされるが、アプリ側 URL の見直しを検討すること。

## 素材の更新元

スクショの原本は アプリ本体リポの `tools/store-screenshots/out/{ja,en}/`。
文言の原本は `docs/store/app-store-listing.md`（概要）と `docs/store-assets/COPY.md`。
**アプリ側を更新したらこちらも追随させる**（二重管理になっている点は認識のうえ許容）。

## 既知の TODO

- [ ] v1.1.0（動画録画）承認後に「弾く姿を動画に残す / Capture how you play」セクションと
      `02-record.png` を追加する。**現状は v1.0.0 の実機能のみ記載**（未提供機能を載せない方針）
- [ ] 独自ドメインの要否をオーナー判断（指名検索を本気で取るなら推奨）
- [ ] Google Search Console に登録してサイトマップ送信 + 指名検索の実データを見る
