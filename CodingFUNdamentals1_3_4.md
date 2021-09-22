### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Separated Family!

## Step 1
氷同士を橋でつないで、ホッキョクグマを真ん中の島に集めよう。
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_1_3_2.png)

```ghost
player.onChat("family", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }
})

``` 