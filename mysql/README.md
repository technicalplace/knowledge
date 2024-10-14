### default_generatedとは

- default_generatedは、MySQL 8.0で導入された新しい属性で、カラムのデフォルト値が「生成された」ものであることを示しています。
具体的には、CURRENT_TIMESTAMPやCURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMPのように、デフォルト値が動的に生成される場合にこの属性が付与されます。

- default_generatedの意味
  動的デフォルト値: default_generatedは、カラムのデフォルト値が静的な値（例えば、固定の数値や文字列）ではなく、動的に生成されることを示します。CURRENT_TIMESTAMPはその典型例です。
  自動更新: ON UPDATE CURRENT_TIMESTAMPのように、行が更新されるたびに自動的に値が更新される設定がある場合にも、この属性が付与されます。