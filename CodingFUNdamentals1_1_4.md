### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move up to the gold plate!

## Step 1
エージェントに青い道をたどらせて、金の感圧板をふませよう。  
同時に、オレンジの道の先にある感圧板を自分でふもう。  
どちらも10秒以内にふむことができれば、**クリア**だよ！

```ghost
player.onChat("last", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
```  