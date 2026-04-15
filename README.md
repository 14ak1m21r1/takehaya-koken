# 自己実現活動公開研究会 2026

東京学芸大学附属竹早小学校「自己実現活動公開研究会」の公式サイトです。

## デプロイ方法

1. このリポジトリを GitHub に push
2. Settings → Pages → Source を `main` ブランチ `/（root）` に設定
3. 数分後に `https://<username>.github.io/<repo名>/` で公開されます

## 更新ガイド

### 研究主題を確定する

`index.html` の以下の部分を編集：

```html
<!-- 「研究主題（仮）」→「研究主題」に変更 -->
<p class="label">研究主題</p>
<p class="text">確定した研究主題をここに</p>
<!-- noteの行を削除 -->
```

### 公開日程を更新する

PC用テーブル（`<table class="sched-table">`）とモバイル用カード（`<div class="sched-cards">`）の **両方** を更新してください。

テーブル行の例：
```html
<tr>
  <td class="round-num">1</td>
  <td class="date-col">6月16日（月）</td>
  <td>3年1組「○○○」 担当：△△</td>
  <td class="status-col"><span class="badge badge-open">受付中</span></td>
</tr>
```

カードの例：
```html
<div class="sched-card">
  <div class="card-round">1</div>
  <div class="card-body">
    <p class="card-date">6月16日（月）</p>
    <p class="card-content">3年1組「○○○」 担当：△△</p>
    <span class="badge badge-open">受付中</span>
  </div>
</div>
```

### ステータスバッジの種類

| クラス | 表示 | 用途 |
|-------|------|------|
| `badge-open` | 緑ベタ | 受付中 |
| `badge-soon` | 緑枠 | 近日公開 |
| `badge-tbd` | グレー | 調整中 |

### 申込フォームのリンクを設定する

`index.html` 内の `href="#"` を Microsoft Forms 等の URL に差し替え：

```html
<a href="https://forms.office.com/r/xxxxx" class="btn-primary">
```

同様に CTA セクションの `btn-cta` も差し替えてください。

## ファイル構成

```
├── index.html    … サイト本体（HTML/CSS/JS 1ファイル完結）
├── .nojekyll     … GitHub Pages の Jekyll 処理をスキップ
└── README.md     … このファイル
```

## OGP画像を設定する場合

リポジトリに `ogp.png`（1200×630px推奨）を追加し、`index.html` の `<head>` 内に以下を追記：

```html
<meta property="og:image" content="https://<username>.github.io/<repo>/ogp.png">
```
