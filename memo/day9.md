# 座学
#### スタックマシン続き
- x86-64の命令スタック
  - `push n`: nをスタックにプッシュ
  - `pop rdi`: rdiにスタックトップを格納してpop
  - `add|sub|imul rax rdi` raxとrdiを+,-,*した結果をraxに格納
  - `idiv rdi` raxをrdiで割った結果をraxに格納
  - `cqo`: raxに入っている64bit値を128bitに引き伸ばしてrdxとraxにセット

#### 最適化コンパイラ
- x86-64のアセンブリは冗長に見える
  - pushしてpopするのは直接movすればよい
- 今のところはOK
  - 後々、生成されたアセンブリを見て特定のパターンを別の命令列に置き換えることもできる
  - いわゆる最適化(コンパイラには最適化オプションがあったりする)
  - 最初からアセンブリ生成と最適化を一緒にやると混乱する
  - 早すぎる最適化はすべての悪の元凶

#### step5 四則演算できる言語の作成
- step4で出力できるようになったアセンブリを使って実際に計算を実行する部分の実装
# 実装
- parserを使えるように必要部分を改変
- x86-64アセンブリ実装(四則演算)
# 感想
- a