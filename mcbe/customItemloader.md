(かなり簡潔に説明します...)
プラグイン導入後、以下のコマンドを実行、空のリソースパック致します...
今回に関しましては、「packname」として説明を実施致します。
```
/rsc create packname
```
実行後、以下のコマンドを実行、作成致しましたリソースパックへアイテムを追加致します。
```
/rsc additem [pack_name] [item_name] [namespace]
```
↓例...
```
/rsc additem packname tapioka tapioka:tapioka
```
アイテム追加後、以下のコマンドにてリソースパックをzip化致します...
```
/rsc makepack packname
```
リソースパックzip化後、サーバーへ導入を実施致します為、リソースパックを以下のディレクトリへ移動致します。
```
[PocketMine]\plugin_data\CustomItemLoader\resource_packs\packname.mcpack
↓
[PocketMine]\resource_packs\packname.mcpack
```

「resource_packs.yml」の文末へ以下の文字列を追加致します...(インデント注意...)
```
   - packname.mcpack
```

<hr>

以下のファイルをファイルエディタにて開きます。
```
[PocketMine]\plugin_data\CustomItemLoader\config.yml
```
文末へ以下の文章を適切に編集、追加致します...(インデント注意)
```
items:
  [item_name]:
    id: 1001
    meta: 0
    namespace: [namespace]
    name: [item_name]
    allow_off_hand: false
    max_stack_size: 64
    texture: [item_name]
```

サーバーを起動、giveコマンドにて、(/give ????? 1001)アイテムは正常に追加致します事を確認します。
