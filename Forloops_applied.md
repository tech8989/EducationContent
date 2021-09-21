### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1


# CODING TUTORIALS: Forループ 応用編

## Step 1

コードを利用して、自由にピクセルアートを作ろう！
一度の命令で、全部作らなくても大丈夫。
一列ずつ作ってみてもいいよ！

```ghost
player.onChat("run", function () {
	
    agent.setItem(GRASS,1,1)
    agent.place(FORWARD)
    agent.move(FORWARD, 1)
    agent.turn(TurnDirection.Left)
    agent.teleportToPlayer()
    agent.destroy(FORWARD) 
})


``` 
#### ~ tutorialhint
エージェントの向きを変えたり、自分のところに戻したりするプログラムを作っておくと
作業しやすいよ。

例）エンダーマンの作り方：全部黒でうめた後、目を置いているよ。
```block
player.onChat("black", function () {
    agent.setItem(BLACK_WOOL, 64, 1)
    for (let index = 0; index < 8; index++) {
        for (let index = 0; index < 8; index++) {
            agent.move(FORWARD, 1)
            agent.place(DOWN)
        }
        agent.move(BACK, 8)
        agent.move(RIGHT, 1)
    }
    agent.move(FORWARD, 5)
    agent.move(LEFT, 1)
    for (let index = 0; index < 2; index++) {
        agent.destroy(DOWN)
        agent.setItem(WOOL, 64, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.destroy(DOWN)
        agent.setItem(MAGENTA_WOOL, 64, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.destroy(DOWN)
        agent.setItem(WOOL, 64, 1)
        agent.place(DOWN)
        agent.move(LEFT, 3)
    }
})

```
