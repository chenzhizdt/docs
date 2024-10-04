上記の基本的な使用説明をもとに、「注文提出」のシナリオを例に挙げます。ユーザーが注文を提出する際、選択したすべての製品の在庫を確認する必要があります。もし選択した製品の中に在庫が不足しているものがあれば、その注文の提出を中止し、適切な警告メッセージを表示します。すべての製品の在庫が十分であれば、注文データが正常に生成されます。

他のステップは説明の中で同様ですが、1つの注文が複数の商品に関連するため、データモデリング時に「注文」 <-- m:1 -- 「注文詳細」 -- 1:m --> 「製品」の多対多の関係を追加する必要があります。また、「操作前イベント」ワークフローに「ループ」ノードを追加し、各製品の在庫が十分であるかを確認します：

![例_ループ検査フロー](https://static-docs.nocobase.com/8307de47d5629595ab6cf00f8aa898e3.png)

ループの対象は提出された注文データの「注文詳細」配列です：

![例_ループ対象設定](https://static-docs.nocobase.com/ed662b54cc1f5425e2b472053f89baba.png)

ループプロセス内の条件判断ノードは、現在のループ製品オブジェクトの在庫が十分であるかどうかを判断するために使用されます：

![例_ループ内の条件判断](https://static-docs.nocobase.com/4af91112934b0a04a4ce55e657c0833b.png)

他の設定は基本的な使用の設定と同様で、最終的に注文を提出する際に、いずれかの製品の在庫が不足している場合、注文の提出が中止され、適切な警告メッセージが表示されます。テスト時には、1つの注文内で複数の製品を提出し、その中の1つの製品の在庫が不足し、もう1つの製品の在庫が十分である場合、返された応答メッセージを見ることができます：

![例_提出後の応答メッセージ](https://static-docs.nocobase.com/dd9e81084aa237bda0241d399ac19270.png)

応答メッセージには、最初の製品「iPhone 15 Pro」の在庫不足については提示されていませんが、2つ目の製品「iPhone 14 Pro」の在庫不足についてのみ提示されています。これはループ中に最初の製品の在庫が十分であったために中止されず、2つ目の製品が在庫不足であったために注文の提出が中止されたためです。
