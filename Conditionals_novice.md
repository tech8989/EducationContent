### @explicitHints true

# Agent Maze: Blocks

## Step 1
**迷路を進もう** 
 
``||loops: ずっと||``を追加し、``||logic:もし真なら||``を入れます。 

### ~ tutorialHint
``||loops:ずっと||``中にいれた処理は、プログラムを止めるまで、ずっとくり返されます。


## Step 2
``||logic:もし真なら||``の条件を（"**<真>**"の部分）を``||agent:エージェントにブロックがあるか前を確認させる||``に変えます。  
``||logic:もし～なら||``の中に``||agent:エージェントの向きを左に変える||``を入れます。

## Step 3
``||logic:もし～なら||``の**(+)**を押し、``||logic: でなければ||``を表示します。  
``||logic: でなければ||``の下に``||agent:エージェントを前に移動させる||``を追加します。

### ~ tutorialHint

この**もし～なら、でなければ**をif else文と言い、このように条件によって、
処理を分ける方法をプログラミングでは**分岐制御**と言います。

```blocks
loops.forever(function () {
    if (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.turn(LEFT_TURN)
    } else {
        agent.move(FORWARD, 1)
    }
})
```

## Step 4

実行して、エージェントの動きを確認しよう。
 