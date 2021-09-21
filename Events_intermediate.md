### @explicitHints true

# Fun with Events: Blocks

## Step 1
``||player: プレイヤーが歩いた時||`` ブロックを追加します。

## Step 2
``||player: プレイヤーが歩いた時||``に``||mobs:生き物を出現させる||`` ブロックを追加します。  
``||mobs:生き物を出現させる||`` ブロックの生き物を``||mobs: 飛び道具||`` ブロックに変えて**ロケット花火**を選びます。  

## Step 3
``||mobs:生き物を出現させる||`` ブロックのy座標を10に変えます。  

## Step 4
``||player:プレイヤーが歩いた時||``の処理を``||loops:くりかえし||``ブロックで**25回**くり返すようにします。  

### ~ tutorialHint

```blocks
player.onTravelled(WALK, function () {
    for (let index = 0; index < 25; index++) {
        mobs.spawn(FIREWORKS_ROCKET, pos(0, 10, 0))
    }
})
```

## Step 5
``||blocks:ブロックが破壊された時||``ブロックを追加し、**樫の木材** ブロックを選びます。

## Step 6
``||mobs:生き物を出現させる||``ブロックを``||blocks:ブロックが破壊された時||``に追加し、y座標を10に変えます。
 
## Step 7
``||blocks:ブロックが破壊された時||``に``||loops:くりかえし||``を追加し、 ニワトリを**25回**スポーンさせるようにします。

### ~ tutorialHint

```blocks
blocks.onBlockBroken(PLANKS_OAK, function () { 
    for (let index = 0; index < 25; index++) { 
        mobs.spawn(CHICKEN, pos(0, 10, 0)) 
    } 
}) 
```
## Step 8
``||player:次のアイテムが使われた時||``を追加し、アイテムを**金のリンゴ**に変えます。

## Step 9
``||player:次のアイテムが使われた時||``に``||mobs: apply to||`` ブロックを追加し、効果を**飛行**, durationを**10**、amplifierを**5**にします。

### ~ tutorialHint
durationは効果の持続時間、amplifierは効果の強さです。

## Step 10
``||mobs: apply to||`` ブロックの対象を``||mobs:すべての生き物||``（ニワトリ）に変えます。

### ~ tutorialHint

```blocks
player.onItemInteracted(GOLDEN_APPLE, function () { 
    mobs.applyEffect(LEVITATION, mobs.entitiesByType(CHICKEN), 10, 5) 
}) 
```

## Step 11
プログラムを実行して、すべてのイベントを動かしてみよう。

