# AWSのすべてをコードで管理する方法〜その理想と現実〜

## CloudFormantion (Terraform じゃないよねやっぱ)

CloudFormation によって今後のインフラの効率性変わる

## 1 Infrastructure as code を理解する

テンプレートはリソースを定義するもの
何回実行しても更新されない

aws cliは処理を定義するので実行回数ごとに更新される

cloud formantion 自体の追加料金なし

スタックのリソース状態を記述(リソースの記載する順序は関係ない)

- tempalte
  - Parameters 使う
  - Resources 使う
  - Outputs 使う

全ては対応していない

クラウドフォーメーション 入門 で検索

## CLI

web console だと cloudformantion の実行そのものに再現性がない

web console は論外

aws cli の実行は

create-stack, update-stack ではなく deploy を使うべき

deploy は作成も更新もできる

チェンジセット をかならず使う

デプロイ時に --no-execute-changeset フラグを使って、チェンジセット作成までで止める

cli は terraform のほうが洗練されている

実行は CLI 実行結果は GUI で確認すると素敵

## スタック分割

1. どのリソースがどのリソースに参照されるか確認する

2. template と script をリソースごとに分ける

参照関係の解決方法

- クロススタック参照
- ダイナミック参照
- シェルで頑張る

