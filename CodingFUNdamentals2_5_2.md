### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Planet visit

## Step 1
**レッドストーンをあつめよう**  
  
エージェントがレッドストーン鉱石をすべて集めるコードを３つの中から1つ選んで、実行しよう。  
**1回しか挑戦できない**ので、コースとコードよく見て慎重に選ぼう！  
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_5_2.png)
コースは上のようになっているよ。  

```template
player.onChat("1", function () {
    for (let index = 0; index < 28; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 8; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 24; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
player.onChat("2", function () {
    for (let index = 0; index < 10; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 4; index++) {
                agent.move(FORWARD, 1)
                agent.setItem(PLANKS_OAK, 1, 1)
                agent.place(DOWN)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_ORE) {
            agent.turn(RIGHT_TURN)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE) {
            agent.turn(LEFT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found Ore Deposit!")
})
```
```ghost
player.onChat("1", function () {
    for (let index = 0; index < 28; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 8; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 24; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
player.onChat("2", function () {
    for (let index = 0; index < 10; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 4; index++) {
                agent.move(FORWARD, 1)
                agent.setItem(PLANKS_OAK, 1, 1)
                agent.place(DOWN)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_ORE) {
            agent.turn(RIGHT_TURN)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE) {
            agent.turn(LEFT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found Ore Deposit!")
})
```
