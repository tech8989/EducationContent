### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move along the turtle tracks!

## Step 1
カメが通ったあとをたどって、門にたどりつくように、エージェントを移動させよう。  
``||agent: エージェントを前に移動 ||`` ブロック の『前』を『右』や『左』に変えて、移動してみよう。




```ghost
player.onChat("tracks", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
for (let index = 0; index < 4; index++) {
    	
 }
``` 