### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to collect all the garbage!

## Step 1
全てのゴミをこわして拾おう。

#### ~ tutorialhint 
```blocks
player.onChat("4", function () {
    for (let index = 0; index < 5; index++) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.collectAll()
    }
    agent.move(FORWARD, 2)
    for (let index = 0; index < 2; index++) {
        agent.move(RIGHT, 1)
        agent.destroy(FORWARD)
        agent.collectAll()
    }
    agent.move(FORWARD, 4)
    agent.destroy(FORWARD)
    agent.collectAll()
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