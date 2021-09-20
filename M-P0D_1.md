### @explicitHints true

# M-P0D_1 「くりかえし」を使おう① 

## Step 1		 	
**「くりかえし」を使おう① **

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0D_1.png)

## Step 2		 	
**エージェントを自分の位置に呼ぼう**  
・``||player:チャットコマンドを入力した時||``の中に``||agent:エージェントを西向きにテレポートさせる||``を入れよう。  
・チャットコマンドを"tp"に変えよう。

### ~ tutorialHint
```blocks
player.onChat("tp", function () {
    agent.teleport(pos(0, 0, 0), WEST)
})
```

## Step 3		 	
**エージェントを自分の位置に呼ぼう**  
・ダイヤモンドブロックの上で、チャットコマンド"tp"を実行しよう。  
・エージェントが自分の所に来たかな？

## Step 4		 	
**エージェントを3ブロック前にすすませよう①**  
・新しく``||player:チャットコマンドを入力した時||``を追加して、**f1**に変えよう。  
・``||agent:エージェントを前に移動させる||``を入れて、歩数を**(3)**に変えよう。

### ~ tutorialHint
```blocks
player.onChat("f1", function () {
    agent.move(FORWARD, 3)
})
```

## Step 5		 	
**エージェントを3ブロック前にすすませよう① **  
・チャットコマンド"f1"を実行しよう。  
・エージェントが3ブロック前に進んだかな？

## Step 6		 	
**エージェントを3ブロック前にすすませよう②**  
・新しく``||player:チャットコマンドを入力した時||``を追加して、**f2**に変えよう。  
・``||agent:エージェントを前に移動させる||``を"3つ"追加しよう。

### ~ tutorialHint
```blocks
player.onChat("f2", function () {
    agent.move(FORWARD, 1)
    agent.move(FORWARD, 1)
    agent.move(FORWARD, 1)
})
```

## Step 7		 	
**エージェントを3ブロック前にすすませよう②**  
・チャットコマンド"f2" を実行しよう。  
・エージェントが3ブロック前に進んだかな？

## Step 8		 	
**エージェントを3ブロック前にすすませよう③**  
・新しく``||player:チャットコマンドを入力した時||``を追加して、**f3**に変えよう。  
・``||agent:エージェントを前に移動させる||``を追加しよう。  
・``||loops:くりかえし||``を追加して、「エージェントを前に移動させる」をかこもう。  
・「くりかえし」の回数を**(3)**に変えよう。

### ~ tutorialHint
```blocks
player.onChat("f3", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 1)
    }
})
```

## Step 9		 	
**エージェントを3ブロック前にすすませよう③**  
・チャットコマンド"f3" を実行しよう。  
・エージェントが3ブロック前に進んだかな？
