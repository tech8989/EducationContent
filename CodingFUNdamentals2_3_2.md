### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Deep Stone 

## Step 1
**うまった石を見つけよう**  
用意されたコードには、5か所間違いがあるので、修正しよう。  
エージェントにさせたい正しい動きは次のとおり。  
・エージェントの下のブロックが金ブロックでない間、  
　　下のブロックをこわさせ、１ブロック下に移動させる  
　　もし目の前のブロックが石なら、  
　　メッセージを送信して、前のブロックをこわして、ひろわせる。
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_3_2.png)

#### ~ tutorialhint 
```blocks
player.onChat("dig", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != GOLD_BLOCK) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == STONE) {
            player.say("Found the stone!")
            agent.destroy(FORWARD)
            agent.collectAll()
        }
    }
})
```



```template
player.onChat("dig", function () {
    while (agent.inspect(AgentInspection.Block, LEFT) == AIR) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
            if (agent.inspect(AgentInspection.Block, FORWARD) != GRASS) {
                player.say("Found the stone!")
                agent.destroy(FORWARD)
                agent.collectAll()
        }
    }
})
```

