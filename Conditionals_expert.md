### @explicitHints true

# Agent Pyramid: Blocks

## Step 1
**ピラミッドを作ろう**
![agent build path](https://teck89.xsrv.jp/MEE_tutorial/img/conditionals_expert.png)
## Step 2
**エージェントを自分の位置にもどすチャットコマンドを作ろう**

``||player:チャットコマンドを入力した時||``を追加し、``||agent:エージェントを自分の位置にもどす||``を入れます。

### ~ tutorialHint 

```blocks
player.onChat("tp" function (){ 
    agent.teleportToPlayer()
}) 
```
## Step 3
**エージェントの向きを変えるチャットコマンドを作ろう**

``||player:チャットコマンドを入力した時||``を追加し、``||agent:エージェントの向きを左に変える||``を入れます。

### ~ tutorialHint 

```blocks
player.onChat("t", function () {
    agent.turn(TurnDirection.Left)
})
```

## Step 4
**ピラミッドを作るチャットコマンドを作ろう**

``||player:チャットコマンドを入力した時||``を追加し、"**(+)**"を押して引数を1つ追加します。  
チャットコマンドを"**p**"、引数（変数）の名前を``||variable:size||``にします。

### ~ tutorialHint 
この引数が、ピラミッドの一番下の段の1辺の長さになります。

```blocks
player.onChat("p", function (size) { 
}) 
```

## Step 5
**ピラミッドを作るチャットコマンドを作ろう**

``||player:チャットコマンドを入力した時||``に``||logic:もし真なら||``を追加します。  
条件に``||logic: 0<0||``を追加し、"<"を"**>**"に、左の0を``||variable:size||``にします。

### ~ tutorialHint 

```blocks
player.onChat("p", function (size){ 
    let size = 0 
    if (size > 0) { 
    } 
}) 
```

## Step 6
**ピラミッドを作るチャットコマンドを作ろう**

``||agent:エージェントにブロックを設定させる||``を``||logic:もし～なら||``に追加し、ブロックを**砂岩**に、個数を``||math: 0×0||``に変えます。  
``||math: 0×0||``の両方の0を``||variable:size||``にします。


### ~ tutorialHint 

```blocks
player.onChat("p", function (size){ 
    let size = 0 
    if (size > 0) { 
        agent.setItem(SANDSTONE, size * size, 1) 
    } 
}) 
```

## Step 7
**ピラミッドを作るチャットコマンドを作ろう**

``||agent:エージェントの設定を追加||``を``||agent:エージェントにブロックを設定させる||``の下に追加し、**1.動きながら置く**を**真**にします。


## Step 8
**ピラミッドを作るチャットコマンドを作ろう**

``||loops:くりかえし||``を``||agent:エージェントの設定を追加||``の下に追加し、くりかえし**4**回にします。  
その中に``||agent:エージェントを前に移動させる||``を入れます。  
移動するブロック数に``||math: 0-0||``を追加し、``||variable:size||``-1ブロック移動するように変えます。

## Step 9
**ピラミッドを作るチャットコマンドを作ろう**  

``||loops:くりかえし||``の中の一番下に、``||agent:エージェントの向きを左に変える||``を入れます。


### ~ tutorialHint

```blocks
player.onChat("p", function (size) { 
    if (size > 0) { 
        agent.setItem(SANDSTONE, size * size, 1) 
        agent.setAssist(PLACE_ON_MOVE, true) 
 
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, size - 1)
            agent.turn(LEFT_TURN)
        }

    } 
}) 
```

## Step 10
**ピラミッドを作るチャットコマンドを作ろう**

``||agent:エージェントを前に移動させる||``を``||loops:くりかえし||``の下に追加し、**上**に移動するように変えます。

## Step 11
**ピラミッドを作るチャットコマンドを作ろう**

``||agent:エージェントの設定を追加||``を``||agent:エージェントを上に移動させる||``の下に追加し、**1.動きながら置く**を**偽**にします。

## Step 12
**ピラミッドを作るチャットコマンドを作ろう**

``||agent:エージェントを前に移動させる||``を``||agent:エージェントの設定を追加||``の下に追加します。

## Step 13
**ピラミッドを作るチャットコマンドを作ろう**

``||variable:変数sizeを1だけ増やす||``を``||agent:エージェントを前に移動させる||``の下に追加し、**1**を**-2**に変えます。


## Step 14
**ピラミッドを作るチャットコマンドを作ろう**

``||player:チャットコマンドを実行する||``を``||変数sizeを-2だけ増やす||``の下に追加します。

## Step 15
**ピラミッドを作るチャットコマンドを作ろう**

``||player:チャットコマンドを実行する||``の**jump**の部分に``||text:文字列をつなげる||``を入れます。  
そして、前の文字列には、"**p **"を、後ろの文字列には``||variable:size||``を入れます。  

"**p**"の後ろに半角スペースを忘れないようにしましょう。

### ~ tutorialHint

```blocks
player.onChat("p", function (size) { 
    if (size > 0) { 
        agent.setItem(SANDSTONE, size * size, 1) 
        agent.setAssist(PLACE_ON_MOVE, true) 
 
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, size - 1)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1) 
        agent.setAssist(PLACE_ON_MOVE, false) 
        agent.move(FORWARD, 1) 
        size += -2
        player.runChatCommand("p" + size)) 
    } 
}) 
```
``||player:チャットコマンドを実行する||``を使うと、マインクラフトでチャットコマンドを入力して実行するように、  
プログラムからチャットコマンドを実行することができます。  
ここでは、ピラミッドを1段作った後、自分自身を実行し、次の段を作っています。  
このように、自分自身を実行する処理を**再帰呼び出し**と言います。


## Step 16
広場の中央当たりで、エージェントを自分の位置にもどして、ピラミッドを作りましょう。  
チャットコマンドの後に、引数（size)をつけるのを忘れないようにしましょう。  

チャットコマンドの入力例）p 8


