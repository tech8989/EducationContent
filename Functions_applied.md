### @explicitHints true

# House Functions: Blocks

## Step 1
**家を建てよう** 

![agent build path](https://teck89.xsrv.jp/MEE_tutorial/img/functions_expert.png)

## Step 2
**カベを作る関数を作ろう**

新しい``||functions:関数||``**walls**を作成します。 


## Step 3
**カベを作る関数を作ろう**

``||functions:関数||``**walls**に``||agent:エージェントにブロックを設定させる||``を追加し、ブロックを**アカシアの木材**に、個数を**64**個に変えます。

## Step 4
**カベを作る関数を作ろう**

``||loops:くりかえし||``を``||agent:エージェントにブロックを設定させる||``の下に追加し、回数を**3**にします。  
``||agent:エージェントを前に移動させる||``を``||loops:くりかえし||``の中に追加し、方向を**上**に変えます。

## Step 5
**カベを作る関数を作ろう**

``||agent:エージェントを上に移動させる||``の下に別の``||loops:くりかえし||``を追加します。  
さらにその中に、``||loops:くりかえし||``を追加します。  
※両方とも回数は**4**のままにする。


## Step 6
**カベを作る関数を作ろう**

一番内側の``||loops:くりかえし||``の中に``||agent:エージェントに前へ置かせる||``を追加し、方向を**下**にします。  
その下に、``||agent:エージェントを前に移動させる||``を追加します。


## Step 7
**カベを作る関数を作ろう**

一番内側の``||loops:くりかえし||``の下に、``||agent:エージェントの向きを左に変える||``を追加し、方向を**右**に変えます。

これで、``||functions:関数||``**walls**の完成です。

### ~ tutorialHint

```blocks
function walls () {
    agent.setItem(PLANKS_ACACIA, 64, 1) 
    for (let index = 0; index < 3; index++) { 
        agent.move(UP, 1) 
        for (let index = 0; index < 4; index++) { 
            for (let index = 0; index < 4; index++) { 
                agent.place(DOWN) 
                agent.move(FORWARD, 1) 
            } 
            agent.turn(RIGHT_TURN) 
        } 
    } 
}) 
```

## Step 8
**屋根を作る関数を作ろう**

新しい``||functions:関数||``**roof**を作ります。   


## Step 9
**屋根を作る関数を作ろう**

``||functions:関数||``**roof**に``||agent:エージェントにブロックを設定させる||``を追加し、ブロックを**レンガハーフブロック**に、個数を**64**個に変えます。  
その下に、``||agent:エージェントを前に移動させる||``を追加し、方向を**上**に変えます。

## Step 10
**屋根を作る関数を作ろう**

``||agent:エージェントを上に移動させる||``の下に別の``||loops:くりかえし||``を追加します。  
さらにその中に、``||loops:くりかえし||``を追加します。  

両方とも回数を**5**に変えます。

## Step 11
**屋根を作る関数を作ろう**

一番内側の``||loops:くりかえし||``の中に``||agent:エージェントに前へ置かせる||``を追加し、方向を**下**にします。  
その下に、``||agent:エージェントを前に移動させる||``を追加します。

## Step 12
**屋根を作る関数を作ろう**

一番内側の``||loops:くりかえし||``の下に、``||agent:エージェントを前に移動させる||``を追加します。  
方向を**後ろ**に、歩数を**5**に変えます。

さらにその下に、もう一つ``||agent:エージェントを前に移動させる||``を追加し、方向を**右**に変えます。

これで、``||functions:関数||``**roof**の完成です。

### ~ tutorialHint

```blocks
function roof () {
    agent.setItem(BRICKS_SLAB, 64, 1) 
    agent.move(UP, 1) 
    for (let index = 0; index < 5; index++) { 
        for (let index = 0; index < 5; index++) { 
            agent.place(DOWN) 
            agent.move(FORWARD, 1) 
        } 
        agent.move(BACK, 5) 
        agent.move(RIGHT, 1) 
    } 
}) 
```

## Step 13
最後に家を建てるチャットコマンドを作ります。  
``||player:チャットコマンドを入力した時||``を追加し、その中に次の2つを追加します。  
　・``||functions:呼び出し walls||``  
　・``||functions:呼び出し roof||``

### ~ tutorialHint

```blocks
player.onChat("house", function () {
    walls()
    roof()
})
function walls () {
    agent.setItem(PLANKS_ACACIA, 64, 1) 
    for (let index = 0; index < 3; index++) { 
        agent.move(UP, 1) 
        for (let index = 0; index < 4; index++) { 
            for (let index = 0; index < 4; index++) { 
                agent.place(DOWN) 
                agent.move(FORWARD, 1) 
            } 
            agent.turn(RIGHT_TURN) 
        } 
    } 
}) 
function roof () {
    agent.setItem(BRICKS_SLAB, 64, 1) 
    agent.move(UP, 1) 
    for (let index = 0; index < 5; index++) { 
        for (let index = 0; index < 5; index++) { 
            agent.place(DOWN) 
            agent.move(FORWARD, 1) 
        } 
        agent.move(BACK, 5) 
        agent.move(RIGHT, 1) 
    } 
})
```

## Step 14

完成したら、家を建てるチャットコマンドを実行してみよう。

```ghost

agent.teleportToPlayer()

```