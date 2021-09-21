### @explicitHints true
# Tutorial

## Step 1
コードを使って持続可能な家を建てよう。用意してあるコードを使ってもいいですよ。


```template

player.onChat("fd", function () { 
    agent.move(FORWARD, 1)
})

player.onChat("up", function () {
    agent.move(UP, 1)
})

player.onChat("tp", function () {
    agent.teleportToPlayer()
})

player.onChat("t", function () {
    agent.turn(LEFT_TURN)
})

player.onChat("sq", function (size) {
    agent.move(UP, 1)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < size - 1; index++) {
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(LEFT_TURN)
    }
})

```

```ghost

player.onChat("jump", function () {

    agent.setItem(GRASS, 1, 1)

    if (!(false)) {
        while (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
            agent.collectAll()
        }
    }
    agent.setAssist(PLACE_ON_MOVE, false) 
})

```