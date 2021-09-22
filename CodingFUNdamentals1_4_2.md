### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Bamboo Border

## Step 1
**まわりに竹を植えよう**  
まずは、用意されたプログラムを実行してみよう。  
その後、プログラムを修正して、広場の4辺に竹を植えよう。  

#### ~ tutorialhint 
``||loops: くりかえし ||`` ブロックを2つ以上使おう。  
プログラムは何度動かしてもいいよ。  

```template
player.onChat("bamboo", function () {
    agent.setItem(BAMBOO, 64, 1)
    for (let index = 0; index < 16; index++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})
```