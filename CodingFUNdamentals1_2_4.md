### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to collect all the garbage!

## Step 1
**チャレンジ問題　ゴミを全て拾おう**  
砂浜にたくさんのゴミが落ちているよ。  
全てのゴミを拾って、子ガメを海にかえそう！

#### ~ tutorialhint 
次の図のような道を通ってみよう。  
``||agent: エージェントに前を破壊させる||`` の『前』を『右』や『左』に変えて、  
エージェントの右や左のブロックも破壊できるよ。
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_1_2_1.png)

```blocks
player.onChat("run", function () {
    for (let index = 0; index < 22; index++) {
        agent.destroy(FORWARD)
        agent.destroy(RIGHT)
        agent.destroy(LEFT)
        agent.collectAll()
        agent.move(FORWARD, 1)
    }
    agent.move(LEFT, 4)
    for (let index = 0; index < 14; index++) {
        agent.destroy(BACK)
        agent.destroy(RIGHT)
        agent.destroy(LEFT)
        agent.collectAll()
        agent.move(BACK, 1)
    }
})


```

```ghost
player.onChat("garbage", function () {
    for (let index = 0; index < 4; index++) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.destroy(FORWARD)
        agent.collectAll()
    }
})
```