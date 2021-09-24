### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Locate the Sample! 

## Step 1
**青氷を見つけよう**  
エージェントの下のブロックが青氷でない間、  
下のブロックをこわして、下へ進ませよう。  
その後、下にある青氷をこわして、ひろわせよう。
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_2_1.png)

#### ~ tutorialhint 
```blocks
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != BLUE_ICE) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
    }
    agent.destroy(DOWN)
    agent.collectAll()
})
```

```ghost 
player.onChat("ice", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != ICE) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
    }
    agent.destroy(DOWN)
    agent.collectAll()
    
})
```
