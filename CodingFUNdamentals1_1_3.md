### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move up to the gold plate!

## Step 1
エージェントを**上下**に移動して、金の感圧板をふませよう
#### ~ tutorialhint 
``||agent:エージェントを前に移動||`` の「前」の部分は変えることができるよ。 
   
エージェントに金の感圧板をふませるにはどう移動すれば、いいかな？

```ghost
player.onChat("up", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

```  