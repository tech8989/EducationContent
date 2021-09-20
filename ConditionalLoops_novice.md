### @explicitHints true

# Agent Destroy Passage: Blocks


## Step 1
**金ブロックから金ブロックまで、カベをこわして道を作ります**  

``||player:チャットコマンドを入力した時||``に、``||loops:もし～ならくりかえし||``を追加します。


## Step 2
``||agent:エージェントに確認させる||``を``||loops:もし～ならくりかえし||``の条件に入れます。


## Step 3
次の処理を``||loops:もし～ならくりかえし||``の中にいれます。  
　・``||agent:エージェントに前を破壊させる||``  
　・``||agent:エージェントに前に1ブロック移動させる||``  
　・``||agent:エージェントに上を破壊させる||``  


### ~ tutorialHint

```blocks
player.onChat("destroy", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.destroy(UP)
    }
})
```
## Step 4
完成したら、実行してみよう。

```ghost
agent.teleportToPlayer()
```
