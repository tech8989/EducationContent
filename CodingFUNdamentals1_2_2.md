### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move along the turtle tracks & destroy obstacles!

## Step 1

``||agent: エージェントに前を破壊させる||``で木をこわし、``||agent: エージェントに全てひろわせる||`` で、こわした木を拾わせよう。

また、``||loops:くりかえし||``を使うようにしよう。
``||loops:くりかえし||``を使うと、囲まれた部分の処理を指定した回数くり返すことができるよ。

#### ~ tutorialhint 
```blocks
player.onChat("3", function () {
    for (let index = 0; index < 8; index++) {
        agent.destroy(FORWARD)
        agent.collectAll()
        agent.move(FORWARD, 1)
    }
})
``` 

```ghost
player.onChat("path", function () {
    for (let index = 0; index < 4; index++) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.destroy(FORWARD)
        agent.collectAll()
    }
})
``` 