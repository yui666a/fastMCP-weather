# FastMCP Weather

このプロジェクトは、FastMCPを使用して天気情報を取得するためのMCPサーバーです。National Weather Service (NWS) APIを使用して、天気予報とアラート情報を提供します。

## 設定方法

`~/Library/Application Support/Claude/claude_desktop_config.json` に以下の設定を追加します。

```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "/Users/yui666a/Projects/fastMCP-weather/weather",
        "run",
        "weather.py"
      ]
    }
  }
}
```

## 機能

- 特定の州のアクティブな天気アラートの取得
- 指定された緯度・経度の天気予報情報の取得

## 利用可能なツール

### get_alerts

特定の州のアクティブな天気アラートを取得します。

**パラメータ:**

- `state`: 州の略称（例：CA, NY, TX）

### get_forecast

指定された緯度・経度の天気予報を取得します。

**パラメータ:**

- `latitude`: 緯度（例：37.7749）
- `longitude`: 経度（例：-122.4194）

## 依存関係

- FastMCP
- httpx

## セットアップ

1. 仮想環境を作成し、アクティベートします：

  ```bash
  python -m venv .venv
  source .venv/bin/activate  # Unix/macOS
  ```

2. 依存関係をインストールします：

```bash
pip install -r requirements.txt
```

## 使用方法

サーバーを起動するには：

```bash
python weather.py
```

## 注意事項

- このサーバーは National Weather Service API を使用しています
- APIリクエストには適切なUser-Agentヘッダーが必要です
- エラーが発生した場合は、適切なエラーメッセージが返されます

