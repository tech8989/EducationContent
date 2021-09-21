### @explicitHints true

# CODING TUTORIALS: シーケンス 応用編

## Step 1
レッドストーンを使った回路を完成させよう。  
ボタンとレッドストーンパウダーを置いて、ボタンを押したら、ランプがつくようにしよう。　　

![agent build path](https://teck89.xsrv.jp/MEE_tutorial/img/sequencing_applied.png)


```ghost
player.onChat("run", function () {
    agent.teleport(world(0, 0, 0), NORTH)
    agent.turn(LEFT_TURN)
    agent.teleportToPlayer()
    agent.setItem(WOODEN_BUTTON, 1, 1)
    agent.place(DOWN)
    agent.move(FORWARD, 1)
    agent.move(DOWN, 1)
    agent.setItem(REDSTONE_WIRE, 64, 1)
    agent.setAssist(PLACE_ON_MOVE, true)
    agent.move(FORWARD, 8)
    agent.move(RIGHT, 1)
})

``` 
#### ~ tutorialhint

```block
player.onChat("run", function () {
    agent.teleport(pos(0, 0, 0), NORTH)
    agent.setItem(WOODEN_BUTTON, 1, 1)
    agent.place(DOWN)
    agent.move(FORWARD, 1)
    agent.move(DOWN, 1)
    agent.setItem(REDSTONE_WIRE, 64, 1)
    agent.setAssist(PLACE_ON_MOVE, true)
    agent.move(FORWARD, 8)
    agent.move(RIGHT, 1)
})

```
