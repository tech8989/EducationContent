### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Repair the Rover 

## Step 1
**探査機をなおそう**  
用意されたコードには、4か所間違いがあるので、修正しよう。  
エージェントにさせたい正しい動きは次のとおり。  
・エージェントの前のブロックが空気でない間、以下の処理をずっとくり返す。  
　・エージェントを右に１ブロック移動させる。  
　・もしエージェントの前のブロックがラピスラズリブロックなら、  
　　右に１ブロック移動させ、向きを左に変え、右に１ブロック移動させる。  
・メッセージを送信する  
・エージェントにレッドストーンブロックを持たせ、前に置かせる。  
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_3_4.png)

#### ~ tutorialhint 
```blocks
player.onChat("repair", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != AIR) {
        agent.move(RIGHT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == LAPIS_LAZULI_BLOCK) {
            agent.move(RIGHT, 1)
            agent.turn(LEFT_TURN)
            agent.move(RIGHT, 1)
        }
    }
    player.say("Found the break!")
    agent.setItem(REDSTONE_BLOCK, 1, 1)
    agent.place(FORWARD)
})
```

```template
player.onChat("repair", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) == AIR) {
        agent.move(RIGHT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == LAPIS_LAZULI_BLOCK) {
            agent.move(RIGHT, 1)
            agent.turn(RIGHT_TURN)
            agent.move(LEFT, 1)
        }
    }
    player.say("Found the break!")
    agent.setItem(GRASS, 1, 1)
    agent.place(FORWARD)
})
```