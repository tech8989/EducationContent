### @explicitHints true

# Modifying Agent Fun Functions: Blocks

## Step 1
チャットコマンド**carrot**、**chicken**、**snowball**があらかじめ用意されています。

```template
player.onChat("carrot", function () {
    agent.setItem(CARROTS, 64, 1)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 5; index++) {
            agent.till(FORWARD)
            agent.move(FORWARD, 1)
            agent.place(DOWN)
        }
        agent.move(BACK, 5)
        agent.move(RIGHT, 2)
    }
})
player.onChat("chicken", function () {
    for (let index = 0; index < 15; index++) {
        mobs.spawn(CHICKEN, pos(0, 0, 0))
    }
})
player.onChat("snowball", function () {
    for (let index = 0; index < 15; index++) {
        mobs.spawn(SNOWBALL_PROJECTILE_MOB, pos(0, 10, 0))
    }
})
```

## Step 2
**チャットコマンドcarrotをtorchesに変えよう**

``||player:チャットコマンドを入力した時||``の**carrot**を**torches**に変えます。  
そして、``||agent:エージェントにスロットに設定させる||``のニンジンを**たいまつ**に、64個を**32**個に変えます。

## Step 3
**チャットコマンドcarrotをtorchesに変えよう**

内側の``||loops:くりかえし||``の回数を**5**から**4**に変更して、12本のたいまつを置くようにします。  

## Step 4
**チャットコマンドcarrotをtorchesに変えよう**

``||agent:エージェントに前を耕させる||``を削除します。  
``||agent:エージェントを後ろに移動させる||``の歩数を**5**から**4**に修正します。

これで、修正完了です。

### ~ tutorialHint

```blocks
player.onChat("torches", function () {
    agent.setItem(TORCHES, 32, 1)
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 1)
            agent.place(DOWN)    	

        }
        agent.move(BACK, 4)
        agent.move(RIGHT, 2)
    }
})
```

## Step 5
次は、``||player:次のアイテムが使われた時||``を追加します。  
そして、アイテムを**トライデント**に変え、``||player:チャットコマンドを実行する||``を3つ追加します。  
それぞれ、**torches**、**chicken**、**snowball**を実行するように変えます。  
修正したら実行して、トライデントを使ってみよう。

### ~ tutorialHint

```blocks
player.onItemInteracted(TRIDENT, function () { 
    player.runChatCommand("torches") 
    player.runChatCommand("chicken") 
    player.runChatCommand("snowball") 
})
```
## Step 6
**chicken**や**snowball**のコードも違うことが起きるように、修正してみよう！   
修正できたら、チャットコマンドを実行してみよう！

