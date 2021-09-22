### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Bamboo Hideaway

## Step 1
**砂場に竹を植えよう**  
次は、砂場の4辺に、3個ずつ竹を植えよう。  
ここでは、``||loops:くりかえし||`` の中に、``||loops:くりかえし||``を入れたプログラムを作ろう。

#### ~ tutorialhint
```blocks
player.onChat("3", function () {
    agent.setItem(BAMBOO, 64, 1)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 3; index++) {
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})
```
 
```ghost
player.onChat("bamboo", function () {
    for (let index = 0; index < 3; index++) {
        agent.setItem(BAMBOO, 64, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
})
```

