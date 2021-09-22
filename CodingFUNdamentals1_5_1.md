### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Chicken Coup

## Step 1
**柵（さく）を高くしよう**  
エージェントに鉄格子を２段分高くしてもらおう。  
1つの辺に9つの鉄格子を置き、それを4回くり返すと1段できるね。  
さらに、それを2回くり返すと2段分の鉄柵を置けるので、``||loops:くりかえし|`` ブロックは3つ必要になるよ。


#### ~ tutorialhint
鉄柵64個では足りないことに注意しよう！
```blocks
player.onChat("1", function () {
    for (let index = 0; index < 2; index++) {
        agent.setItem(IRON_BARS, 64, 1)
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 9; index++) {
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
```

```ghost
player.onChat("chicken", function () {
    for (let index = 0; index < 2; index++) {
        agent.setItem(IRON_BARS, 1, 1)
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 9; index++) {
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})

``` 