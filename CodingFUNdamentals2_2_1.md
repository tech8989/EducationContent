### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
**クレーターを見つけよう  **  
もし、下のブロックが空気ブロックだったら、  
「Crater found!(クレーターを見つけた！)というメッセージを送信しよう。
#### ~ tutorialhint 
```blocks
player.onChat("crater", function () {
    while (agent.detect(AgentDetection.Block, DOWN)) {
        agent.move(FORWARD, 1)
    }
    if (agent.inspect(AgentInspection.Block, DOWN) == AIR) {
        player.say("Crater found!")
    }
})
```
こっちのプログラムでもいいよ
```blocks
player.onChat("crater", function () {
    while (agent.detect(AgentDetection.Block, DOWN)) {
        agent.move(FORWARD, 1)
    }
    player.say("Crater found!")
})
```
```template
player.onChat("crater", function () {
            player.say("Crater found!")
})
```
```ghost
player.onChat("1", function () {
    while (agent.detect(AgentDetection.Block, DOWN)) {
        agent.move(FORWARD, 1)
    }
    if (agent.inspect(AgentInspection.Block, DOWN) == AIR) {
        player.say("Crater found!")
    }
})
```