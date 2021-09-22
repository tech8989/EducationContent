### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true
### @explicitHints 1


# Make the area pretty!

## Step 1
**まわりにタンポポを植えよう**  
最後に、広場のまわりにタンポポを植えよう。  
1つの辺は14ブロックだよ。

#### ~ tutorialhint 
エージェントにタンポポを持たせるのを忘れないようにしよう。

```blocks
player.onChat("4", function () {
    agent.setItem(YELLOW_FLOWER, 64, 1)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 14; index++) {
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})
``` 

```ghost
player.onChat("flower", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 14; index++) {
            agent.setItem(YELLOW_FLOWER, 64, 1)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})

``` 