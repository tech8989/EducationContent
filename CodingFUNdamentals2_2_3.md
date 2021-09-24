### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Reach magma

## Step 1
**マグマブロックを見つけよう**  
エージェントを1ブロック前に進めよう。  
その後、エージェントの下のブロックがマグマブロックでない間、下へ進ませよう。  
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_2_2.png)

#### ~ tutorialhint 
```blocks
player.onChat("run", function () {
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != MAGMA_BLOCK) {
        agent.move(DOWN, 1)
    }
})

```
```ghost
player.onChat("magma", function () {
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != MAGMA_BLOCK) {
        agent.move(DOWN, 1)
    }
})
```
