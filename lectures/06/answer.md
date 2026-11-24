# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：
- STEP 2 の [tool call]：
- STEP 3 の [tool call]：
- STEP 4 の [tool call]：
- 気づき・疑問：

  演習
- STEP 1 のツールの名前：glossary_search_glossary
- STEP 2 の [tool call]：fetch_fetch({'url': 'https://modelcontextprotocol.io/'})
- STEP 3 の [tool call]：aws_aws___search_documentation({'search_phrase': 'Amazon S3 バージョニング 概要', 'topics': ['general']})
- STEP 4 の [tool call]：aws_aws___search_documentation({'search_phrase': 'Using versioning S3 developer guide', 'topics': ['general']})
- 気づき・疑問：
  1. AIの自律的な再検索：STEP 3 で日本語キーワードを使って意図したドキュメントがヒットしなかった際、プログラムの指示ではなくAI自身の判断で検索ワードを英語に切り替えて STEP 4 で再検索していた点がエージェントらしい挙動だと感じた。
  2. ツール名の重複ルール：複数サーバー間の名前被りを防ぐため、クライアント側が「サーバー名_元のツール名」と機械的に結合しているため、`fetch_fetch` や `aws_aws___...` のようにプレフィックスが重なる仕様になっていることがわかった。
  3. トークン消費の増加：接続するMCPサーバーやツールが増えるほど、AIに渡すツールの説明文（スキーマ）が増えるため、入力トークン数も比例して大きく増加（2,179 → 11,257 tokens）することが確認できた。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎 / 実装 / 発展
- やったこと：
- 結果：
- 気づき・疑問：
