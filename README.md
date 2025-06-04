# Colab-LLM-memory-api

Flask を使った対話記憶管理 API サービスです。  
Gemini API はあくまでデモであり、このサービスの目的は、任意の LLM（大規模言語モデル）が記憶機能を持てるようにすることです。

---

## 機能概要


- 対話履歴の追加
- 類似対話の検索
- 統計情報の取得
- ヘルスチェック

- Gemini API（デモ）と連携し、過去の対話記憶を活用した応答生成が可能
- 複数ユーザー対応（user_id による識別）

---

## クイックスタート

1. `colab_memory.ipynb` を GitHub リポジトリまたはローカルから Google Colab にアップロードします。  
2. ノートブック内の `your_ngrok_authtoken` を自分の ngrok トークンに変更します。  
3. ランタイムタイプを **T4 GPU** に設定します。  
4. 「すべて実行（Run all）」を選択してノートブックを一括実行します。  

これだけで、API サーバーの起動から対話メモリの利用までが簡単に体験できます。

---

## API エンドポイント

| パス            | メソッド | 説明      |
| ------------- | ---- | ------- |
| `/api/health` | GET  | ヘルスチェック |
| `/api/stats`  | GET  | 統計情報の取得 |
| `/api/query`  | POST | 類似対話の検索 |
| `/api/add`    | POST | 対話履歴の追加 |

---

使用例
```
# 対話履歴の追加
add_conversation_to_memory("こんにちは！", "こんにちは。何かお手伝いできますか？", user_id="user123")

# 類似対話の検索
query_memory_for_similar_conversations("あなたの名前は？", user_id="user123", top_k=2)
```
