### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Hazing 

## Step 1
**ベルがなるしかけを作ろう**  
トリップワイヤーフックの間に、トリップワイヤーを置こう。  
エージェントの前にブロックがないなら、下へ置いて前に移動をくりかえす  
下にトリップワイヤーを置くために、1ブロック上に移動するのを忘れないようにしよう。

#### ~ tutorialhint

```blocks
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    agent.move(UP, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.place(DOWN)
})

``` 
```ghost
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```