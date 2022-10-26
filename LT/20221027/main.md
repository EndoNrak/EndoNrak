---
marp: true
theme: gaia
class: invert
header: クラウド初心者だけどテトリス評価サービスを作ってる話
footer: EndoNrak@github
---

# 自己紹介

---

## テトリス評価サービスとは

![bg left:30%](images/tetris_play.png)
技術チャレンジ部「tetris で python を学ぼう」
作成コードを本番環境で試行できる

---

### 現行システム問題

![bg right:59%](images/%E8%A9%95%E4%BE%A1%E3%82%B5%E3%83%BC%E3%83%90_%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0%E5%9B%B3.JPG)

1. サーバが落ちるとサービス提供できなくなる（高田さん起きて！）
2. 落ちても運営側がすぐに気づけない
3. リクエストが増えるとさばけなくなる（そんな日が来てほしい）

---

# クラウドサービス化構想

問題の解決

＋クラウドサービス作ってみたい欲

＋高田さんを救いたい思い

## →AWS でテトリス評価サービス作る？？？

イメージは atcoder のテトリス版？

![bg blur:10px 30%](images/aws.png)

---

# クラウドシステム設計どうすればいいかわからなすぎ問題

1. 要件定義せねば
2. AWS のサービス多すぎ、選択肢多すぎ
3. システム構成考えたところでそれでいいのか分からなすぎ

---

## 要件定義

![bg 60%](images/%E8%A6%81%E4%BB%B6%E5%AE%9A%E7%BE%A9.JPG)

---

### AWS のお勉強 ひたすら AWS ブラックベルト

![bg 60%](images/%E3%83%96%E3%83%A9%E3%83%83%E3%82%AF%E3%83%99%E3%83%AB%E3%83%88.JPG)

---

# システム構成のレビュー

やさしい大学時代の友人に感謝...

---

# 完成したシステム構成図

![height:500](images/%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0%E6%A7%8B%E6%88%90%E5%9B%B3.JPG)

---

## いざ実装

- リソース定義は terraform
- バックエンドは python Django で（tetris で python を学ぼうだし、、）
  →https://github.com/seigot/tetris_score_server
- フロントエンドは flutter（クロスプラットフォームで強そう、スマホアプリも作ってみたいかも、、、）
  →https://github.com/seigot/tetris_score_server_frontend
- DB はコスパを考えて dynamodb
- 評価実行は ECS

---

## 開発の日々

![bg 80%](images/%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%AB%E3%83%AC%E3%83%B3%E3%83%80%E3%83%BC.JPG)

---

## 評価フォームページ

![bg 45%](images/%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%83%9A%E3%83%BC%E3%82%B8.JPG)

---

## 評価結果ページ

![bg 45%](images/%E7%B5%90%E6%9E%9C%E3%83%9A%E3%83%BC%E3%82%B8.JPG)

---

# 最後に

もうちょいでリリース出来そうです
おたのしみに。。。。
