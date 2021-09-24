### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Spiral

## Step 1
**金ブロックをあつめよう　その2**  
エージェントの前が金ブロックでない間、エージェントを動かそう。  
前にブロックがある場合は向きを変え、それ以外の場合は、前に進むようにしよう。  
最後に、金ブロックをこわして、ひろうのを忘れないようにしよう！

#### ~ tutorialhint 
```blocks
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != GOLD_BLOCK) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.turn(LEFT_TURN)
        } else {
            agent.move(FORWARD, 1)
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```
```ghost
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```