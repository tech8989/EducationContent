### @explicitHints true

# Bat Cave: Blocks

## Step 1
** どうくつを作り、コウモリをたくさん出そう **

## Step 2
``||player:チャットコマンドを入力した時||``に、``||player:メッセージを送信する||``を追加し、メッセージを「どうくつを掘って」にします。


## Step 3
``||gameplay:ゲーム内の時刻を変更する||``を``||player:メッセージを送信する||``の下に追加し、時刻を**日中**にします。


## Step 4
``||blocks:ブロックを並べる||``を``||gameplay:ゲーム内の時刻を変更する||``の下に追加します。  
そして、並べるブロックを**空気**に、範囲の始まりを**(~-1, ~0, ~-1)**に、範囲の終わりを**(~1, ~2, ~1)**に変えます。


## Step 5
``||loops:くりかえし||``で、``||blocks:ブロックを並べる||`` を囲みます。
そして、くり返す回数を**50**回にします。

### ~ tutorialHint

```blocks
player.onChat("cave", function () {
    player.say("Dig a cave")
    gameplay.timeSet(gameplay.time(DAY))
    for (let index = 0; index < 50; index++) {
        blocks.fill(
        AIR,
        pos(-1, 0, -1),
        pos(1, 2, 1),
        FillOperation.Replace
        )
    }
})
```

## Step 6
新しい変数``||variables:位置||``を追加します。  
そして、``||variables:変数位置を～にする||``をくりかえしの下に追加し、値を``||player:プレイヤーの位置||``にします。

## Step 7
さらに、``||variables:変数位置を～にする||``の下に以下の処理を追加します。

　・メッセージを「コウモリが来る前に10秒で外に出て」を送信する。  
　・``||loops: 一時停止||``を使って、**10**秒(10,000ミり秒)停止する。  
　・メッセージを「コウモリに気をつけて!」を送信する。  
　・ゲーム内の時刻を**夕暮れ**にする。  

## Step 8
最後に、``||loops:くりかえし||``を追加し、``||mobs:生き物を出現させる||``を入れます。  
コウモリを**200**匹を座標``||variables:位置||``に、スポーンさせます。

実行したら、エージェントがいる壁に向かって走ってどうくつを掘ろう。

### ~ tutorialHint
```blocks
let batcave: Position = null
player.onChat("cave", function () {
    player.say("どうくつを掘って")
    gameplay.timeSet(gameplay.time(DAY))
    for (let index = 0; index < 50; index++) {
        blocks.fill(
        AIR,
        pos(-1, 0, -1),
        pos(1, 2, 1),
        FillOperation.Replace
        )
    }
    batcave = player.position()
    player.say("コウモリが来る前に10秒で外に出て")
    loops.pause(10000)
    player.say("コウモリに気をつけて!")
    gameplay.timeSet(gameplay.time(DUSK))
    for (let index = 0; index < 200; index++) {
        mobs.spawn(BAT, batcave)
    }
})
```

