# 子詳細

## イントロダクション

子詳細は、子フォームが閲覧モードで対応するコンポーネントです。ラベルやタイトルコンポーネントと比較して、子詳細は現在のテーブルからより多くのデータを表示でき、関連テーブルのデータ情報も構成して表示することができます。これにより、多層の関係データをネストされた形式で明確に示します。

## 使用説明

### 多対多の関係フィールドの子詳細

![20240822225058](https://static-docs.nocobase.com/20240822225058.png)

この機能は、多層の関係フィールドのネスト表示をサポートします。例：注文/商品/在庫、注文/商品/供給者。

![20240822225231](https://static-docs.nocobase.com/20240822225231.png)

### 一対一の関係フィールドの子詳細

![20240822230215](https://static-docs.nocobase.com/20240822230215.png)

## フィールド設定項目

### 並び順の規則設定

多対多の関係データの表示順序を調整できます。

![20240822230359](https://static-docs.nocobase.com/20240822230359.png)

![20240822230422](https://static-docs.nocobase.com/20240822230422.png)

### フィールドコンポーネント

[フィールドコンポーネント](/handbook/ui/fields/association-field)：ドロップダウン選択、データセレクターなど、他の関係フィールドコンポーネントに切り替えます。

### リンク規則
:::info{title=ヒント}
NocoBase v1.3.17-beta 以上のバージョンが必要です。
:::

![20240906090603_rec_](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20240906090603_rec_.gif)

詳細については [リンク規則](/handbook/ui/blocks/block-settings/linkage-rule) を参照してください。
