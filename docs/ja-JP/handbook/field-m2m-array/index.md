# 多対多（配列）

<PluginInfo name="field-m2m-array"></PluginInfo>

## イントロダクション

データテーブル内で配列フィールドを使用し、ターゲットテーブルの複数のユニークキーを保存することで、ターゲットテーブルとの多対多の関連を確立します。例えば、記事とタグの2つのエンティティがあり、1つの記事は複数のタグに関連付けることができます。記事テーブルでは、タグテーブルに対応するレコードのIDを配列フィールドに保存します。

:::warning{title=注意}

- 標準の [多対多](../data-modeling/collection-fields/associations/m2m/index.md) 関係を確立するためには、中間テーブルを使用することを推奨します。この方法はできるだけ避けてください。
- 現在、配列フィールドで確立された多対多の関連において、PostgreSQLを使用している場合のみ、ターゲットテーブルのフィールドを用いてソーステーブルデータをフィルタリングすることができます。例として、タグテーブルの他のフィールド（タイトルなど）を利用して記事をフィルタリングします。
:::

### フィールド設定

![多対多（配列）フィールド設定](https://static-docs.nocobase.com/202407051108180.png)

## パラメータ説明

### ソースコレクション

ソーステーブル、つまり現在のフィールドが存在するテーブルです。

### ターゲットコレクション

関連付けるターゲットテーブルです。

### 外部キー

配列フィールドで、ソーステーブル内にターゲットテーブルのターゲットキーを保存するフィールドです。

配列フィールドタイプの対応関係：

| NocoBase | PostgreSQL | MySQL  | SQLite |
| -------- | ---------- | ------ | ------ |
| `set`    | `array`    | `JSON` | `JSON` |

### ターゲットキー

ソーステーブルの配列フィールドに保存される値に対応するフィールドで、ユニーク性が求められます。
