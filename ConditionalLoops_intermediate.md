### @explicitHints true

# Build a Bridge: Blocks

## Step 1
**エージェントに金ブロックから金ブロックまで、橋をかけさせよう**

まずは、``||player:チャットコマンドを入力した時||``に、``||agent:エージェントにブロックを設定させる||``を追加し、**樫の木材**を**64**個持たせます。

## Step 2
``||agent:エージェントを前に移動させる||``を``||agent:エージェントにブロックを設定させる||``の下に追加します。

## Step 3
``||loops:もし～ならくりかえし||``を``||agent:エージェントを前に移動させる||``の下に追加します。

## Step 4
``||loops:もし～ならくりかえし||``の条件に``||logic:～ではない||``を入れ、さらにその中に``||agent:エージェントにブロックがあるか前を確認させる||``を入れます。  
そして、確認する向きを**下**に変えます。

## Step 5
``||agent:エージェントに前へ置かせる||``ブロックを``||loops:もし～ならくりかえし||``に追加し、置く位置を**下**にします。

## Step 6
``||agent:エージェントを前に移動させる||``を``||agent:エージェントに下へ置かせる||``の下に追加します。

### ~ tutorialHint

```blocks
player.onChat("build", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, DOWN))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Step 7
完成したら、実行して橋をかけよう。

```ghost
agent.teleportToPlayer()
```
