### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
**カベにそって歩き、岩場をさがそう**  
エージェントの下のブロックが氷塊の間、以下の処理をずっとくり返す。  
　・エージェントの右にブロックがあれば、前に１ブロック移動する。  
　　そうでなければ、右に１ブロック移動する。  
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_4_1.png)

#### ~ tutorialhint 
```blocks
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
    }
})
```




```ghost
player.onChat("1", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
    }
})
```
