### @explicitHints true

# M-P0F 「変数」を使おう 

## Step 1		 	
**「変数」を使おう **  
変数を使って、掘れたダイヤモンドの数を数えよう!

![img](https://teck89.xsrv.jp/MEE_tutorial/img/M-P0F.png)



## Step 2		 	
**エージェントを東向きに呼び出そう**  
・``||player:チャットコマンドを入力した時||``のコマンドを”**tp**”に変えよう。  
・チャットコマンド”tp”に``||agent:エージェントを西向きにテレポートさせる||``を追加し、方角を[**東**]に変えよう。

### ~ tutorialHint
```blocks
player.onChat("tp", function () {
    agent.teleport(pos(0, 0, 0), EAST)
})
```

## Step 3		 	
**掘った数を数えるチャットコマンドを作ろう**  
・新しく``||player:チャットコマンド||``を入力した時を追加して、”**count**”に変えよう。  
・``||loops:くりかえし||``を追加し、回数を(**20**)回に変えよう。 

## Step 4		 	
**高さ2ブロックで掘らせよう**  
・「くりかえし」の中に次の処理を追加しよう。  
・``||agent:エージェントに前を破壊させる||``  
・``||agent:エージェントに前を破壊させる||``を追加して、方向を[**上**]に変えよう。  
・``||agent:エージェントに全てひろわせる||``  
・``||agent:エージェントを前に移動させる||`` 

### ~ tutorialHint

```blocks
player.onChat("count", function () {
    for (let index = 0; index < 20; index++) {
        agent.destroy(FORWARD)
        agent.destroy(UP)
        agent.collectAll()
        agent.move(FORWARD, 1)
    }
})
```

## Step 5		 	
**掘ったダイヤモンドの数を入れる変数を作ろう**  
・``||variables:変数||``**cnt**を作ろう。  
・「チャットコマンド”count”を入力した時」の一番はじめに、``||variables:変数cntを0にする||``を追加しよう。 

### ~ tutorialHint

```blocks
let cnt = 0
player.onChat("count", function () {
    cnt = 0
    for (let index = 0; index < 20; index++) {
        agent.destroy(FORWARD)
        agent.destroy(UP)
        agent.collectAll()
        agent.move(FORWARD, 1)
    }
})
```

## Step 6		 	
**掘ったダイヤモンド鉱石の数を数えよう**  
・``||logic:もし真なら||``を「くりかえし20回」の中の一番はじめに追加し、条件を<``||agent:エージェントにどんなブロックか前を確認させる||`` = ``||blocks:ダイヤモンド鉱石||``>に変えよう。  
・「もし~なら」の中に、``||variables:変数cntを1だけ増やす||``を追加しよう。

### ~ tutorialHint

```blocks
let cnt = 0
player.onChat("count", function () {
    cnt = 0
    for (let index = 0; index < 20; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {
            cnt += 1
        }
        agent.destroy(FORWARD)
        agent.destroy(UP)
        agent.collectAll()
        agent.move(FORWARD, 1)
    }
})
```

## Step 7		 	
**掘ったダイヤモンドブロックの数を数えよう**  
・「もし~なら」の下に、「もし~なら」を複製して追加しよう。  
・2つ目の「もし~なら」の条件を「エージェントにどんなブロックか”**上**”を確認させる」に変えよう。

### ~ tutorialHint

```blocks
let cnt = 0
player.onChat("count", function () {
    cnt = 0
    for (let index = 0; index < 20; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {
            cnt += 1
        }
        if (agent.inspect(AgentInspection.Block, UP) == DIAMOND_ORE) {
            cnt += 1
        }
        agent.destroy(FORWARD)
        agent.destroy(UP)
        agent.collectAll()
        agent.move(FORWARD, 1)
    }
})
```

## Step 8		 	
**掘ったダイヤモンドブロックの数を表示しよう**  
・「くりかえし20回」の下に、``||player:メッセージを送信する||``を追加し、メッセージを``||text:文字列をつなげる||``に変えよう。  
・つなげる1つ目の文字列を``||変数cnt||``に、2つ目の文字列を”**個あった！**”に変えよう。

### ~ tutorialHint
```blocks
let cnt = 0
player.onChat("count", function () {
    cnt = 0
    for (let index = 0; index < 20; index++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {
            cnt += 1
        }
        if (agent.inspect(AgentInspection.Block, UP) == DIAMOND_ORE) {
            cnt += 1
        }
        agent.destroy(FORWARD)
        agent.destroy(UP)
        agent.collectAll()
        agent.move(FORWARD, 1)
    }
    player.say("" + cnt + "個あった！")
})
```


## Step 9		 	
**ダイヤモンドを掘ろう**  
・チャットコマンド”count”を実行しよう  
　⇒とれたダイヤモンドの数を数えられたら成功だ！

