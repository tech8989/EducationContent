### @explicitHints true

# M-P0D_2 「くりかえし」を使おう② 

```template
player.onChat("tp", function () {
    agent.teleport(pos(0, 0, 0), WEST)
})
```

## Step 1  
**「くりかえし」を使おう②**  
ダイヤモンドブロックの上に、tpコマンドでエージェントを呼んでから始めよう。

![img](https://teck89.xsrv.jp/tech89/course/minecraft_EE/img/M-P0D_2.png)

## Step 2  
**エージェントの向きを変えてすすませよう①**  
・新しく``||player:チャットコマンドを入力した時||``を追加して、**t1**に変えよう。

## Step 3  
**エージェントの向きを変えてすすませよう①**  
チャットコマンド"t1"に次の処理を追加しよう。  
・``||agent:エージェントを前に移動させる||``を追加して、歩数を**(3)**に変えよう。  
・``||agent:エージェントの向きを左に変える||``を追加しよう。  
・``||agent:エージェントを前に移動させる||``を追加して、歩数を**(3)**に変えよう。  
・``||agent:エージェントの向きを左に変える||``を追加しよう。

### ~ tutorialHint
```blocks
player.onChat("t1", function () {
    agent.move(FORWARD, 3)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 3)
    agent.turn(LEFT_TURN)
})
```

## Step 4  
**エージェントの向きを変えてすすませよう①**  
・チャットコマンド"t1"を実行しよう。  
・エージェントがエメラルドブロックで左に曲がって、移動したかな？

## Step 5  
**エージェントの向きを変えてすすませよう②**  
・新しく``||player:チャットコマンドを入力した時||``を追加して、**t2**に変えよう。

## Step 6  
**エージェントの向きを変えてすすませよう②**  
チャットコマンド"t2"に次の処理を追加しよう。  
・``||agent:エージェントを前に移動させる||``を追加して、歩数を**(3)**に変えよう。  
・``||agent:エージェントの向きを左に変える||``を追加しよう。  
・``||loops:くりかえし||``を追加して、上の2つの処理をかこもう。  
・「くりかえし」の回数を**(2)**に変えよう。

### ~ tutorialHint
```blocks
player.onChat("t2", function () {
    for (let index = 0; index < 2; index++) {
        agent.move(FORWARD, 3)
        agent.turn(LEFT_TURN)
    }
})
```

## Step 7  
**エージェントの向きを変えてすすませよう②**  
・チャットコマンド"t2"を実行しよう。  
・エージェントがエメラルドブロックで左に曲がって、移動したかな？
