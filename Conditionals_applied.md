### @explicitHints true
### @hideIteration true 

# Tutorial

## Step 1
特定の作物を食べるモブをスポーンさせよう。  
プレイヤーが歩いた時、黒板で指示された作物を植えます。
そして、その作物が植わっている場合、黒板で指示された動物をスポーンさせます。


```ghost
player.onTravelled(WALK, function () {
    blocks.place(CARROTS, pos(0, 0, 0))
    if (blocks.testForBlock(CARROTS, pos(0, 0, 0))) {
        mobs.spawn(HORSE, pos(0, 0, 0))
    }
})
player.onChat("jump", function () {
	
})
```