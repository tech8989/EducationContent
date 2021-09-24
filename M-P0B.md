### @explicitHints true

# M-P0B 座標を覚えよう②　

## Step 1
座標を覚えよう②

座標を使って床やカベを作ろう

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0B.png)

## Step 2
**自分の北側にブロックを一列並べよう**  
・``||player:チャットコマンドを入力した時||``のチャットコマンドを**put**に変え、``||blocks:ブロックを並べる||``を入れよう。  
・並べるブロックを**[樫の木材]**に、範囲の始まりを**(~-2,  ~0, ~-3)**に、範囲の終わりを**(~2,  ~0, ~-3)**に変えよう。

### ~ tutorialHint

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0B_1.png)

「範囲の始まり」と「範囲の終わり」は逆にしてもいいよ。

```blocks
player.onChat("put", function () {
    blocks.fill(
    PLANKS_OAK,
    pos(-2, 0, -3),
    pos(2, 0, -3),
    FillOperation.Replace
    )
})

```


## Step 3
**自分の西側にブロックを一列並べよう**  
・「ブロックを並べる」の下に、もう一つ``||blocks:ブロックを並べる||``を入れよう。  
・並べるブロックを**[樫の木材]**に、範囲の始まりを**(~-3,  ~0, ~-2)**に、範囲の終わりを**(~-3,  ~0, ~2)**に変えよう。

### ~ tutorialHint

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0B_2.png)

```blocks
player.onChat("put", function () {
    blocks.fill(
    PLANKS_OAK,
    pos(-2, 0, -3),
    pos(2, 0, -3),
    FillOperation.Replace
    )
    blocks.fill(
    PLANKS_OAK,
    pos(-3, 0, -2),
    pos(-3, 0, 2),
    FillOperation.Replace
    )
})

```

## Step 4
**自分の北側と西側にブロックを一列並べよう**  
・チャットコマンド"put"を実行してみよう。  
　⇒自分の北側と西側にブロックを並べられたかな？

## Step 5
**自分の北側に3×3の床を作ろう**  
・``||player:チャットコマンドを入力した時||``を追加し、チャットコマンドを**put2**に変えよう。  
・その中に``||blocks:ブロックを並べる||``を追加し、並べるブロックを**[樫の木材]**に、範囲の始まりを**(~-1,  ~0, ~-5)**に、範囲の終わりを**(~1,  ~0, ~-3)**に変えよう。

### ~ tutorialHint
![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0B_3.png)

```blocks
player.onChat("put2", function () {
    blocks.fill(
    PLANKS_OAK,
    pos(-1, 0, -5),
    pos(1, 0, -3),
    FillOperation.Replace
    )
})

```

## Step 6
**自分の北側に3×3の床を作ろう**  
・チャットコマンド”put2”を実行してみよう。  
　⇒自分の北側に3×3の床を作れたかな？


## Step 7
**自分の北側に3×3のカベを作ろう**  
・``||player:チャットコマンドを入力した時||``を追加し、チャットコマンドを**put3**に変えよう。  
・その中に``||blocks:ブロックを並べる||``を追加し、並べるブロックを**[樫の木材]**に、範囲の始まりを**(~-1,  ~2, ~-3)**に、範囲の終わりを**(~1,  ~0, ~-3)**に変えよう。

### ~ tutorialHint
![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0B_4.png)

モード  
　置き換え・・・・ブロックを指定したブロックに置き変える。  
　中空・・・・・・囲んだ座標の面だけを置き換え、中は消去する。  
　アウトライン・・囲んだ座標の面だけを置き換える。中はそのまま。  
　維持・・・・・・囲んだ座標内の空気ブロックのところだけ置き換える。  
　破壊・・・・・・指定したブロックで置き換え、置き換えたブロックはアイテム化する。  

```blocks
player.onChat("put3", function () {
    blocks.fill(
    PLANKS_OAK,
    pos(-1, 2, -3),
    pos(1, 0, -3),
    FillOperation.Replace
    )
})

```
## Step 8
**自分の北側に3×3のカベを作ろう**  
・チャットコマンド"put3"を実行してみよう。  
　⇒自分の北側に3×3のカベを作れたかな？

## Step 9
**やってみよう**  
1．自分のイニシャルの床を作ろう  
2．自分のイニシャルのカベを作ろう  
先に方眼紙にイニシャルを書いてみて、座標を考えよう

### ~ tutorialHint

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0B_5.png)
