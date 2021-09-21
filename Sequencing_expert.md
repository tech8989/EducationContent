### @explicitHints true

# CODING TUTORIALS: シーケンス 上級 

## Step 1
ヤマネコのフェンスを作ろう。

![agent build path](https://teck89.xsrv.jp/MEE_tutorial/img/sequencing_expert.png)


## Step 2
``||player: チャットコマンドを入力した時||``に、
高度なブロックにある「ビルダー」から、``||builder:テレポート||``を追加しよう。
テレポート先を``||positions: ワールド||``座標にして、「-695,9,880」に変更しよう。


#### ~ tutorialhint
ゲーム設定で「座標を表示」をONにしよう。　
「-695,9,880」がどの場所か確認できるよ。

```ghost
player.onChat("run", function () {
    builder.teleportTo(world(0, 0, 0))
    builder.face(WEST)
    builder.turn(LEFT_TURN)
    builder.tracePath(OAK_FENCE)
})
player.onChat("run", function () {
    mobs.spawn(OCELOT, randpos(
    world(-698, 9, 872),
    world(-715, 0, 879)
    ))
})

``` 


## Step 3
``||builder:ビルダー 西に向ける||``を追加しよう。


## Step 4
``||builder:ビルダー 前に移動する||``を追加して、21ブロック前に進ませよう。



## Step 5
``||builder:ビルダー 方向転換||``を追加して、右に向けよう。


## Step 6
続けて、次のように動かそう。  
　・9ブロック前に進む。  
　・右に向く。  
　・21ブロック前に進む。  
　・右に向く。  
　・9ブロック前に進む。  

## Step 7
フェンスを置こう。  
``||builder:ブロックを使って印をつけた場所から軌跡をなぞる||``を使うと今通ってきた道に、指定したブロックを置けます。


#### ~ tutorialhint

```block
player.onChat("1", function () {
    builder.teleportTo(positions.createWorld(-695, 9, 880))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
})

```

## Step 8
フェンスを作ったら、ヤマネコをスポーンさせよう。

``||mobs: 生き物を出現させる||``ブロックを追加し、座標を``||positions: ランダムに座標を選ぶ||``にしよう。  
フェンスの内側にスポーンさせたいので、座標Aをワールド座標「-698,9,872」に座標Bをワールド座標「-715,9,878」に変えよう。


## Step 9
同じようにして、ヤマネコをもう1匹とオオカミを2匹スポーンさせよう！

#### ~ tutorialhint

```block
player.onChat("1", function () {
    builder.teleportTo(positions.createWorld(-695, 9, 880))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
    mobs.spawn(OCELOT, randpos(
    positions.createWorld(-698, 9, 872),
    positions.createWorld(-715, 9, 878)
    ))
    mobs.spawn(OCELOT, randpos(
    positions.createWorld(-698, 9, 872),
    positions.createWorld(-715, 9, 878)
    ))
    mobs.spawn(WOLF, randpos(
    positions.createWorld(-698, 9, 872),
    positions.createWorld(-715, 9, 878)
    ))
    mobs.spawn(WOLF, randpos(
    positions.createWorld(-698, 9, 872),
    positions.createWorld(-715, 9, 878)
    ))
})

```