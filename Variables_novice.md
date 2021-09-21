### @explicitHints true

# Mega Jump: Blocks

## Step 1
**大ジャンプ**

## Step 2

``||player:現在の位置からテレポートする||``を``||player:チャットコマンドを入力した時||``に追加し、y座標（真ん中）を**100**にします。  

一度実行してみよう。

### ~ tutorialHint

```blocks
player.onChat("jump", function () { 
   player.teleport(pos(0,100,0))  
}) 
```

## Step 3
``||player:チャットコマンドを入力した時||``の**(+)**を押して、引数を追加し、``||player:現在の位置からテレポートする||``のy座標を``||variable: num1||``に変えます。  

実行して、好きな高さまでジャンプしてみよう！

### ~ tutorialHint

```blocks
player.onChat("jump", function (num1) {
    player.teleport(pos(0, num1, 0))
})
```


