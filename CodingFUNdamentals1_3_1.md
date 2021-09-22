### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Locate the cub!

## Step 1
エージェントに高さ2ブロックの穴をほらせて、壁の向こうに行こう。  
  
``||agent:エージェントの前にブロックがあるか確認||``させて、真：(正しい)なら  
「``||agent:ブロックを破壊||``して``||agent:移動||``」を``||loops:くりかえす||``
 

#### ~ tutorialhint  
プレイヤーが通れるように、上のブロックをこわすのを忘れないで！

```blocks
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.destroy(UP)
    }
})
```

```template
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
    	
    }
})
```



```ghost
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.destroy(UP)
    }
})

``` 