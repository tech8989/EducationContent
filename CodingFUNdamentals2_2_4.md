### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Iron

## Step 1
**鉄鉱石をあつめよう**  
エージェントの下のブロックが鉄鉱石ブロックでない間、前へ進ませよう。  
ただし、進む前にエージェントの前にブロックがあるか確認して、ある場合はこわさせよう。  
エージェントが鉄鉱石ブロックの上まで来たら、鉄鉱石ブロックをこわして、ひろわせよう。
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_2_3.png)

#### ~ tutorialhint 
```blocks
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != IRON_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        agent.move(FORWARD, 1)
    }
    agent.destroy(DOWN)
    agent.collectAll()
})
```

```ghost
player.onChat("4", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != IRON_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the iron ore!")
    agent.destroy(DOWN)
    agent.collectAll()
})
```