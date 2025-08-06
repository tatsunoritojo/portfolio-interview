# ポートフォリオ管理システム 使用方法

このシステムにより、画像とテキストを簡単に変更してポートフォリオを更新できます。

## フォルダ構造

```
portfolio_data/
├── config.json          # 設定ファイル（テキスト管理）
├── descriptions/         # 将来の拡張用
└── images/              # 画像フォルダ
    ├── qr_attendance/   # QRコード出席管理システムの画像
    ├── shift_scheduler/ # シフトスケジューラーの画像
    └── portfolio_site/  # ポートフォリオサイトの画像
```

## 画像の追加・変更方法

### 1. 画像ファイルの配置

各プロジェクトの画像を対応するフォルダに配置してください：

**QRコード出席管理システム** (`images/qr_attendance/`)
- `main.jpg` - メイン画像（300px高さ推奨）
- `qr_scan.jpg` - QRコード読み取り画面
- `attendance_check.jpg` - 出席確認画面
- `student_register.jpg` - 生徒登録画面
- `monthly_report.jpg` - 月次レポート画面
- `admin_settings.jpg` - 管理者設定画面
- `dashboard.jpg` - ダッシュボード画面

**シフトスケジューラー** (`images/shift_scheduler/`)
- `main.jpg` - メイン画像
- `oauth.jpg` - OAuth認証画面
- `calendar_fetch.jpg` - カレンダーデータ取得画面
- `shift_settings.jpg` - シフト設定画面
- `calculation_result.jpg` - 計算結果画面
- `csv_export.jpg` - CSV出力画面

**ポートフォリオサイト** (`images/portfolio_site/`)
- `main.jpg` - メイン画像
- `landing.jpg` - ランディングページ
- `projects.jpg` - プロジェクト紹介画面
- `skills.jpg` - スキル表示画面
- `mobile.jpg` - モバイル表示画面

### 2. 推奨画像サイズ

- **メイン画像**: 幅制限なし × 300px高さ
- **機能画像**: 200px × 112px（16:9比率）
- **ファイル形式**: JPG, PNG, WebP対応

## テキストの変更方法

`config.json`ファイルを編集して、各画像の説明文を変更できます。

### 設定例

```json
{
  "projects": {
    "qr_attendance": {
      "sub_images": [
        {
          "image": "images/qr_attendance/qr_scan.jpg",
          "title": "QRコード読み取り機能",
          "description": "ここに新しい説明文を入力してください。"
        }
      ]
    }
  }
}
```

## 更新手順

1. **画像の更新**: 対応するフォルダに画像ファイルを配置
2. **テキストの更新**: `config.json`の`title`と`description`を編集
3. **ブラウザで確認**: HTMLファイルをブラウザで開き直して確認

## 注意事項

- 画像ファイル名は`config.json`の設定と一致させてください
- 画像が存在しない場合は、デフォルトのプレースホルダーが表示されます
- ブラウザのキャッシュにより、画像が更新されない場合はスーパーリロード（Ctrl+F5）してください

## トラブルシューティング

**画像が表示されない場合**
1. ファイル名が`config.json`の設定と一致しているか確認
2. 画像ファイルが正しいフォルダに配置されているか確認
3. 画像ファイルが破損していないか確認

**テキストが更新されない場合**
1. `config.json`の JSON 形式が正しいか確認
2. ブラウザのキャッシュをクリアして再読み込み