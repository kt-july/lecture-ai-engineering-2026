# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：glossary_search_glossary
- STEP 2 の [tool call]：glossary_search_glossary({'query': '3レベル'})
- STEP 3 の [tool call]：fetch_fetch({'url': 'https://modelcontextprotocol.io/'})
- STEP 4 の [tool call]：aws_aws___search_documentation({'topics': ['general'], 'search_phrase': 'Amazon S3 バージョニング 概要'}) / aws_aws___search_documentation({'topics': ['general'], 'search_phrase': 'Using versioning in S3 buckets'})
- 気づき・疑問：ファイル（app/mcp_servers.json）に数行書き足すだけで、自作サーバーだけでなく公開サーバーや外部サーバー（AWS）のツールも簡単にエージェントへ追加できることが分かった。一方で、外部サーバーには質問内容が送信されるため、信頼できる提供元か確認することが大切だと学んだ。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎 
- やったこと：エージェント側のファイルは一切いじらず、サーバー側の `app/mcp_server.py` に `server.tool()(tools.get_lecture_summary)` の1行だけを書き足した。
- 結果：- ツールの一覧に `glossary_get_lecture_summary` が自動で増えた。
-「第2回では何を学びますか?」と質問すると、追加したツールが呼ばれて、第2回（ファインチューニングと 　LoRA）の内容が正しく返ってきた。
- テスト（`uv run pytest -q`）を実行し、`21 passed` でエラーなくすべて合格した。
- 気づき・疑問：ージェント側を書き換えなくても、サーバー側で道具を1つ増やすだけでAIが自動的に見つけ　て使ってくれるのがとても便利だと実感した。
