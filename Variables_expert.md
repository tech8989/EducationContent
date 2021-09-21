### @explicitHints true

# Letter Printing: Blocks

## Step 1
** 文字を描こう **

## Step 2
変数を3つ作ります。それぞれ、word1、word2、word3と言う名前にします。  
そして、``||loops:最初だけ||``に``||variables:変数word1を0にする||``を入れ、**0**の部分を高度なブロックの``||text:文字列||``にある**(" ")**にします。  
その中に、"MINE"書きます。

## Step 3
ステップ1で作った``||variables:変数word1を～にする||``を複製し、``||variables:word2||``に"CRAFT"を書きます。  
さらに、もうひとつ複製し、``||variables:word3||``に、"ABCDEFGHIJ"を入れます。

### ~ tutorialHint

```blocks
let word2 = ""
let word1 = ""
word1 = "MINE"
word2 = "CRAFT"
let word3 = "ABCDEFGHIJ"

```

## Step 4
**チャットコマンドを作ろう**

新しい変数positionを作り、``||player:プレイヤーの位置||``を入れます。

## Step 5
**チャットコマンドを作ろう**

``||blocks:文字を描く||``で、なめらかな砂岩ブロックを使って、``||variables:position||``の位置から``||variables:word1||``を描きます。  

## Step 6
**チャットコマンドを作ろう**

``||blocks:文字を描く||``で、紫のウールを使って、``||variables:word2||``を描きます。  
描き始める場所を``||positions:(~0, ~0, ~0)+(~0, ~0, ~0)||``を使って、``||variables:position||``+(~0, **~7** ~0)の位置にします。

## Step 7
**チャットコマンドを作ろう**

``||blocks:文字を描く||``を追加し、ブロックをラピスラズリにします。  
描く文字を``||text: 文字列をつなげる||``を使って、``||variables:word1||``と``||variables:word2||``をつなげた文字列にします。  
また、描き始める場所を``||variables:position||``+(~0, **~14** ~0)の位置にします。

### ~ tutorialHint

```blocks
player.onChat("1", function () {
    position = player.position()
    blocks.print(
    word1,
    SMOOTH_SANDSTONE,
    position,
    WEST
    )
    blocks.print(
    word2,
    PURPLE_WOOL,
    positions.add(
    position,
    pos(0, 7, 0)
    ),
    WEST
    )
    blocks.print(
    "" + word1 + word2,
    LAPIS_LAZULI_BLOCK,
    positions.add(
    position,
    pos(0, 14, 0)
    ),
    WEST
    )
})

```

## Step 8
**プレイヤーが飛んだ時、文字を描こう**

``||player:プレイヤーが歩いた時||``を追加し、**飛んだ時**に変えます。   
また、``||blocks:文字を描く||``を追加し、ブロックを**カボチャ**に、描き始める場所を**(0, 2, 5)**にします。  


## Step 9
**プレイヤーが飛んだ時、文字を描こう**

描く文字を``||text: 文字列の0番目の文字||``にします。  
**this**を``||variables:word3||``に、**0**を``||math:ランダムな数字を選択||``にします。  
``||math:ランダムな数字を選択||``の数字を**0**から**9**にします。

### ~ tutorialHint

```blocks
player.onTravelled(FLY, function () {
    let word3 = ""
    blocks.print(
    word3.charAt(randint(0, 9)),
    PUMPKIN,
    pos(0, 2, 5),
    WEST
    )
})
```

## Step 10

作成したチャットコマンドを入力したり、南を向いて、後ろに飛んでみよう。
