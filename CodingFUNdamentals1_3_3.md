### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1


# Higher Ground!

## Step 1
高さ10ブロックの塔を作ろう  
・エージェントに樫の木材を64個持たせよう。  
・エージェントの前と左右にオークの木材を置いて、上に移動する処理を10回くり返そう。  
![img](https://teck89.xsrv.jp/MEE_tutorial/img/fun_1_3_1.png)
#### ~ tutorialhint 
```blocks
player.onChat("3", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    for (let index = 0; index < 10; index++) {
        agent.place(FORWARD)
        agent.place(LEFT)
        agent.place(RIGHT)
        agent.move(UP, 1)
    }
})
```

## Step 2
登れるようにはしごを作るよ  
・エージェントにはしごを64個持たせよう。  
・エージェントを下に移動して、前にはしごを置く処理をくり返そう。


#### ~ tutorialhint 
```blocks
player.onChat("3", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    for (let index = 0; index < 10; index++) {
        agent.place(FORWARD)
        agent.place(LEFT)
        agent.place(RIGHT)
        agent.move(UP, 1)
    }
    agent.setItem(LADDER, 64, 1)
    for (let index = 0; index < 10; index++) {
        agent.move(DOWN, 1)
        agent.place(FORWARD)
    }
})
```

```ghost
player.onChat("tower", function () {
    agent.move(FORWARD, 1)
    agent.setItem(LADDER, 64, 1)
    for (let index = 0; index < 10; index++) {
        agent.place(FORWARD)
        agent.move(UP, 1)
    }
    agent.move(DOWN, 10)
})

``` 

