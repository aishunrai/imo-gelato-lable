# AppSheet 製造ラベル印刷（分離版）

既存の `gelato.html` と `gelato-label.lbx` は現場で使用中のため変更しません。
このフォルダは、AppSheet の製造DBから Brother Smooth Print を起動するための独立した導線です。

## ラベルテンプレート

P-touch Editorで62 mm × 29 mmのテンプレートを作り、ファイル名を
`gelato-appsheet-v1.lbx` とします。次のオブジェクト名を設定します。

- 製造日（テキスト）: `DATE`
- フレーバー（テキスト）: `FLAVOR`
- 担当者（テキスト）: `STAFF`
- ロットID（QRコード）: `LOT`

この新しいテンプレートだけをSmooth Printへ追加し、既存テンプレートは上書きしません。

## AppSheetから渡すURL

個人名やロット情報をWebサーバーへ送らないよう、値は `?` ではなく `#` 以降へ渡します。

```text
https://aishunrai.github.io/imo-gelato-lable/appsheet-print/#date=2026-09-28&flavor=ピスタチオ&staff=担当者名&lot=LOT-ID&copies=1
```

## 導入順序

1. このフォルダをGitHub Pagesへ追加する
2. 新しい `.lbx` をP-touch Editorで作る
3. テスト端末のSmooth Printへ新しいテンプレートを追加する
4. AppSheetのテストデータで1枚印刷する
5. 文字切れ、QR読取、プリンター設定を確認してから現場端末へ展開する


