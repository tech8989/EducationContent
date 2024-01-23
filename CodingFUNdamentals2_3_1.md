### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Locating stone 

## Step 1
**月の石を見つけよう**  
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_2_3_1.png)
用意されたコードには、３か所間違いがあるので、修正しよう。  
エージェントにさせたい正しい動きは次のとおり。  
　・エージェントを左に4ブロック移動させる。下をこわさせる。1ブロック下に移動させる。  
　・もし目の前のブロックが石なら、メッセージを送信して、前をこわして、ひろわせる。  
　・目の前のブロックが石でないなら、メッセージを送信する。  
　・エージェントを1ブロック上に移動させる。  
　・上の動きすべてを４回くり返す。  


#### ~ tutorialhint 
```blocks
player.onChat("stone", function () {
    for (let index = 0; index < 4; index++) {
        agent.move(LEFT, 4)
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == STONE) {
            player.say("Found the stone!")
            agent.destroy(FORWARD)
            agent.collectAll()
        } else {
            player.say("No stone here!")
        }
        agent.move(UP, 1)
    }
})
```

```template
player.onChat("stone", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(RIGHT, 4)
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) != STONE) {
            player.say("Found the stone!")
            agent.destroy(FORWARD)
            agent.collectAll()
        } else {
            player.say("No stone here!")
        }
        agent.move(UP, 1)
    }
})
```