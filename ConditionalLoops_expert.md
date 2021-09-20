### @explicitHints true

# Spiral Activity: Blocks


## Step 1
**金ブロックから金ブロックまで、エージェントを移動させます**

``||player:チャットコマンドを入力した時||``に、``||loops:もし～ならくりかえし||``を追加します。

## Step 2
``||loops:もし～ならくりかえし||``の条件に``||logic:0=0||``を入れ、**=**を**≠**にします。  
**≠**の左側に``||agent:エージェントにどんなブロックか確認させる||``を入れます。  
右側には``||blocks:ブロック||``を入れ、**金ブロック**に変えます。

## Step 3
``||logic:もし～なら、でなければ||``を``||loops:もし～ならくりかえし||``に追加します。  
条件を``||agent:エージェントにブロックがあるか前を確認させる||``にします。

## Step 4
``||logic:もし～なら、でなければ||``の**もし**の下に、``||agent:エージェントの向きを左に変える||``を追加します。  
**でなければ**の下に、``||agent:エージェントを前に1ブロック移動させる||``を追加します。

### ~ tutorialHint

```blocks
player.onChat("spiral", function () { 
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) { 
        if (agent.detect(AgentDetection.Block, FORWARD)) { 
            agent.turn(LEFT_TURN) 
        } else { 
            agent.move(FORWARD, 1) 
        } 
    } 
}) 
```

## Step 5
完成したら、実行してエージェントを動かそう。


```ghost
agent.teleportToPlayer()
```

