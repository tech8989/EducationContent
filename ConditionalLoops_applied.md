### @explicitHints true
### @hideIteration true 

# Tutorial

## Step 1
エージェントが自動的に畑を作るように、プログラムしよう。

ダイヤブロックまではニンジンを、その後はジャガイモを植えよう。

### ~ tutorialHint
``` block
player.onChat("run", function () {
    agent.setItem(CARROTS, 64, 1)
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != GOLD_BLOCK) {
        if (agent.inspect(AgentInspection.Block, DOWN) == FARMLAND) {
            agent.place(DOWN)
        } else if (agent.inspect(AgentInspection.Block, DOWN) == DIAMOND_BLOCK) {
            agent.setItem(POTATOES, 64, 1)
        }
        agent.move(FORWARD, 1)
    }
})

```

```ghost
agent.teleportToPlayer()
agent.turn(LEFT_TURN)
agent.setAssist(PLACE_ON_MOVE, false)
agent.till(FORWARD)
for (let index = 0; index < 4; index++) {
	
}
while (!(agent.inspect(AgentInspection.Block, FORWARD) == GRASS)) {
}

```