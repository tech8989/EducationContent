### @explicitHints true

# M-P0C 座標をおぼえよう③

## Step 1  
座標をおぼえよう③  
３次元にブロックを置いてみよう。  

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0C.png)

座標について、テック８９先生に聞きましたか？

## Step 2 
**自分の北側にブロックで３×３×３の立方体を作ろう**  
・``||player:チャットコマンドを入力した時||``のチャットコマンドを**put**に変え、``||blocks:ブロックを並べる||``を入れよう。  
・並べるブロックを**[金ブロック]**に、範囲の始まりを**(~-1,  ~2, ~-5)**に、範囲の終わりを**(~1,  ~0, ~-3)**に変えよう。

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0C_1.png)

### ~ tutorialHint
「範囲の始まり」や「範囲の終わり」は対角線上の端っこ同士ならどこでもいいよ。

```blocks
player.onChat("put", function () {
    blocks.fill(
    GOLD_BLOCK,
    pos(-1, 2, -5),
    pos(1, 0, -3),
    FillOperation.Replace
    )
})
```

## Step 3 
**やってみよう**  
１．大きさを変えてみよう。  
２．形を変えてみよう。

### ~ tutorialHint
``||blocks:ブロックを並べる||``で一度に並べられるブロックの数は32,768個までと決まってます。

