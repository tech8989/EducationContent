### @explicitHints true


# CODING TUTORIALS: Forループ 初級

## Step 1
**動物をスポーンさせよう**  

``||player:次のアイテムが使われた時||`` を追加し、骨に変えよう。


```ghost
player.onItemInteracted(IRON_SHOVEL, function() {
    
    for (let i = 0; i < 5; i++) {
        mobs.spawn(CHICKEN, pos(0, 0, 0))
    }
})

``` 

## Step 2

``||loops: くりかえし||`` を``||player:次のアイテムが使われた時||``の中に追加し、回数を**6**にしよう。

## Step 3

``||mobs: 生き物を出現させる||`` を``||loops: くりかえし||``の中に追加し、ゾンビホースが6頭スポーンするようにしよう。



## Step 4

同じようにして、骨を使った時、スケルトンホースが4頭スポーンするようにしよう。

## Step 5

できたら、チェストの中にある骨を使って、実行してみよう。

### ~ tutorialhint

```block

player.onItemInteracted(BONE, function () {
    for (let index = 0; index < 6; index++) {
        mobs.spawn(ZOMBIE_HORSE, pos(0, 0, 0))
    }
    for (let index = 0; index < 4; index++) {
        mobs.spawn(SKELETON_HORSE, pos(0, 0, 0))
    }
})

``` 