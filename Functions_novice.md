### @explicitHints true

# Agent Fun Functions: Blocks

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
``||player:次のアイテムが使われた時||``を追加して、アイテムを**ブレイズロッド**にします。  
その中に``||player:チャットコマンドを実行する||``を3つ追加します。  
それぞれ、**carrot**、**chicken**、**snowball**を実行するようにします。  

### ~ tutorialHint

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
    player.runChatCommand("carrot")
    player.runChatCommand("chicken")
    player.runChatCommand("snowball")
})
```

## Step 3

完成したら実行して、ブレイズロッドを使ってみよう。
