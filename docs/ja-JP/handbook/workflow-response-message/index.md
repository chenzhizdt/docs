# 応答メッセージ

<PluginInfo name="workflow-response-message" link="/handbook/workflow-response-message" commercial="true"></PluginInfo>

応答メッセージノードは、特定のタイプのプロセスにおいて、操作を提出したクライアントに対してカスタマイズされたメッセージをフィードバックするために使用されます。

:::info{title=ヒント}
現在、同期モードの「操作前イベント」と「カスタム操作イベント」タイプのワークフローでの使用がサポートされています。
:::

## 使用マニュアル

### ノードの作成

サポートされているワークフロータイプでは、プロセス内の任意の位置に「応答メッセージ」ノードを追加できます。プロセス内のプラス（「+」）ボタンをクリックして、「応答メッセージ」ノードを追加してください：

![ノードの追加](https://static-docs.nocobase.com/eac2b3565e95e4ce59f340624062ed3d.png)

応答メッセージは、リクエスト全体の過程で配列の形で存在し、プロセスが任意の応答メッセージノードに到達すると、新しいメッセージが配列に追加されます。サーバーが応答内容を送信する際には、すべてのメッセージがクライアントにまとめて送信されます。

### ノードの設定

メッセージ内容全体はテンプレート文字列であり、変数を挿入することができます。ノード設定内でこのテンプレート内容を自由に構成できます：

![ノードの設定](https://static-docs.nocobase.com/d5fa5f4002d50baf3ba16048818fddfc.png)

プロセスがこのノードに到達すると、テンプレートが解析され、メッセージ内容の結果が生成されます。上記の設定では、変数「ローカル変数 / すべての製品をループ / ループオブジェクト / 製品 / タイトル」は、実際のプロセス内で特定の値に置き換えられます。例えば：

```
製品「iPhone 14 Pro」の在庫が不足しています
```

![メッセージ内容](https://static-docs.nocobase.com/06bd4a6b6ec499c853f0c39987f63a6a.png)

### プロセス設定

応答メッセージのステータス提示は、プロセスの成功または失敗の状態に基づいて決定されます。任意のノードの実行が失敗すると、全体のプロセスも失敗と見なされます。この場合、メッセージ内容は失敗状態でクライアントに返され、通知されます。

プロセス内で積極的に失敗状態を定義する必要がある場合は、「終了ノード」を使用し、失敗状態として設定できます。このノードに到達すると、失敗状態でプロセスを終了し、メッセージを失敗状態でクライアントに返します。

全体のプロセスが失敗状態を生成せず、正常に終了した場合、メッセージ内容は成功状態としてクライアントに返されます。

:::info{title=ヒント}
プロセス内で複数の応答メッセージノードが定義されている場合、実行されたノードはメッセージ内容を配列に追加し、最終的にクライアントに返される際にはすべてのメッセージ内容がまとめて通知されます。
:::

### 使用シーン

#### 「操作前イベント」プロセス

「操作前イベント」プロセスでは、応答メッセージを使用してプロセス終了後にクライアントに対応するメッセージフィードバックを送信できます。具体的な詳細は[操作前イベント](../workflow/triggers/pre-action.md)を参照してください。

#### 「カスタムアクションイベント」プロセス

同期モードの「カスタムアクションイベント」では、応答メッセージを使用してプロセス終了後にクライアントに対応するメッセージフィードバックを送信できます。具体的な詳細は[カスタムアクションイベント](../workflow/triggers/custom-action.md)を参照してください。
