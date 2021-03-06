### @explicitHints true

# M-P0E 「条件文」を使おう 

```template
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(LEFT_TURN)
})
```

## Step 1		 	
**「条件文」を使おう **  
「条件文」を使うと、条件によって実行する処理を変えることができるよ。

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0E.png)

## Step 2		 	
**エージェントに前のブロックをこわしながら進ませよう**  
・新しく``||player:チャットコマンドを入力した時||``を追加して、”**break**”に変えよう。  
・チャットコマンド”break”の中に``||loops:くりかえし||``を追加しよう。  
・「くりかえし」の回数を(**20**)に変えよう。  

### ~ tutorialHint
```blocks
player.onChat("break", function () {
    for (let index = 0; index < 20; index++) {    }
})
```

## Step 3		 	
**エージェントに前のブロックをこわしながら進ませよう**  
・チャットコマンド”break”の「くりかえし」の中に、次の処理を追加しよう。  
・``||agent:エージェントに前を破壊させる||``  
・``||agent:エージェントに全てひろわせる||``  
・``||agent:エージェントを前に移動させる||``  

### ~ tutorialHint
```blocks
player.onChat("break", function () {
    for (let index = 0; index < 20; index++) {
            agent.destroy(FORWARD)
            agent.collectAll()        	
	     agent.move(FORWARD, 1)
    }
})
```

## Step 4		 	
**条件を追加しよう**  
・``||logic:もし真なら||``を追加して、「エージェントに前を破壊させる」と「エージェントに全てひろわせる」を囲もう。  
・「もし真なら」の条件<**真**>を``||agent:エージェントにブロックがあるか前を確認させる||``に変えよう。  

### ~ tutorialHint
```blocks
player.onChat("break", function () {
    for (let index = 0; index < 20; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
```

## Step 5		 	
**真っすぐなコースで実行しよう**  
・ワールドの真っすぐなコースの金ブロックにエージェントを呼び、”break”を実行してみよう。  
　⇒エージェントがダイヤモンドブロックをこわして拾い、感圧板の上まで移動できれば、成功だ！  


## Step 6		 	
**条件を追加して、右に曲がるプログラムを作ろう**  
・「くりかえし」の中の最初に新しく``||logic:もし真なら||``を追加しよう。

## Step 7
**前のブロックが岩盤の場合、右に曲がろう**  
・「もし真なら」の条件に＜``||logic:0=0||``＞を追加しよう。  
・最初の**0**を``||agent:エージェントにどんなブロックか前を確認させる||``に、2個目の**0**を ``||blocks:岩盤||``に変えよう。  
・その中に``||agent:エージェントの向きを左に変える||``を追加し、方向を「**右**」に変えよう

### ~ tutorialHint

```blocks
player.onChat("break", function () {
    for (let index = 0; index < 20; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == BEDROCK) {
            agent.turn(RIGHT_TURN)
        }

        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})

```

## Step 9		 	
**曲がったコースで実行しよう**  
・ワールドの曲がったコースの金ブロックにエージェントを呼び、”break”を実行してみよう。  
　⇒エージェントがダイヤモンドブロックをこわして拾い、感圧板の上まで移動できれば、成功だ！