### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Cattle

## Step 1
**羊を連れて行こう**  
エージェントを動かすと、羊がついて来るよ。  
まずは、用意されたプログラムを実行してみよう。  
実行すると、ブロックの数を数えずにエージェントを動かせることがわかるね！  
  
プログラムを追加して、エージェントを動かし、金の感圧板をふませよう。  
エージェントがたどる道はこのようになるよ。
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_1_5_1.png)

#### ~ tutorialhint 
```blocks
player.onChat("sheep", function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
})
```


```template
player.onChat("sheep", function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})

``` 
