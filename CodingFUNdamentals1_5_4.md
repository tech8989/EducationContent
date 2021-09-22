### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Clear the Foliage!

## Step 1
**草むらをきれいにしよう**  
エージェントは前に移動しながら、8個のブロック（草）をこわさないといけないよ。  
草の下をこわせば、全てこわれるので、上をこわす必要はないよ。  
草の列は16あるよ。2列こわす処理を8回くり返して、全ての草をとりのぞこう！  
ヒント）次のように進もう。赤い丸の位置では右に、黄色い丸の位置では左に向きを変える。
![img](https://teck89.xsrv.jp/tech89/course/minecraft_EE/img/fun_1_5_2.png)

#### ~ tutorialhint 
```blocks
player.onChat("4", function () {
    for (let index = 0; index < 8; index++) {
        for (let index = 0; index < 8; index++) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        }
        for (let index = 0; index < 2; index++) {
            agent.move(FORWARD, 1)
            agent.turn(RIGHT_TURN)
        }
        for (let index = 0; index < 8; index++) {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        }
        for (let index = 0; index < 2; index++) {
            agent.move(FORWARD, 1)
            agent.turn(LEFT_TURN)
        }
    }
})

```

```ghost
player.onChat("foliage", function () {
    for (let index = 0; index < 8; index++) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        for (let index = 0; index < 2; index++) {
            agent.move(FORWARD, 1)
            agent.turn(RIGHT_TURN)
        }
    }
})
``` 