### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Track Down the Rover 

## Step 1
**探査機をさがそう**  
用意されたコードには、4か所間違いがあるので、修正しよう。  
エージェントにさせたい正しい動きは次のとおり。  
・エージェントの前のブロックがクォーツブロックでない間は、以下の処理をずっとくり返す。  
　・もしエージェントの下のブロックが金ブロックなら、エージェントの向きを右に変える。  
　・もしエージェントの下のブロックが鉄ブロックなら、エージェントの向きを左に変える。  
　・エージェントを前に１ブロック移動させる。  
・メッセージを送信する。
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_3_3.png)

#### ~ tutorialhint 
```blocks
player.onChat("rover", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != BLOCK_OF_QUARTZ) {
            if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_BLOCK) {
            agent.turn(RIGHT_TURN)
        }
            if (agent.inspect(AgentInspection.Block, DOWN) == IRON_BLOCK) {
            agent.turn(LEFT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the rover!")
})
```

```template
player.onChat("rover", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != BLOCK_OF_QUARTZ) {
            if (agent.inspect(AgentInspection.Block, UP) == GOLD_BLOCK) {
            agent.turn(LEFT_TURN)
        }
            if (agent.inspect(AgentInspection.Block, RIGHT) == IRON_BLOCK) {
            agent.turn(RIGHT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the rover!")
})
```
