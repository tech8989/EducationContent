### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1


# CODING TUTORIALS: シーケンス 中級

## Step 1
ブロックを並べてカベを作り、幅1ブロックの道を作ります。  
そのためのチャットコマンドを３つ作ります。

![agent build path](https://teck89.xsrv.jp/tech89/course/minecraft_EE/img/sequencing_intermediate.png)


## Step 2
1つ目のチャットコマンド：エージェントを自分の位置へ戻そう。

```ghost
player.onChat("farm", function () {
    agent.teleportToPlayer()
    agent.move(FORWARD, 1)
    agent.turn(RIGHT)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.setItem(GRASS, 1,1)
    
})

``` 

#### ~ tutorialhint

```block
player.onChat("tp", function () {
    agent.teleportToPlayer()
})

``` 

## Step 3
2つ目のチャットコマンド：道の右側のカベを作ろう。

``||agent: エージェントにブロックを自分のスロットに設定させる||``ブロックを使って、  
エージェントに材料となるブロックを64個持たせよう。

## Step 4
2つ目のチャットコマンド：道の右側のカベを作ろう。

``||agent: エージェントに設定を追加||``ブロックで、「動きながら置く」を真にしよう。  
これにより、エージェントが動いた時、動く前にいた場所にブロックが置かれるようになります。


## Step 5
2つ目のチャットコマンド：道の右側のカベを作ろう。

エージェントを次のように動かして、ブロックを並べよう。  
　・前に4ブロック移動する。  
　・向きを左に変える。  
　・前に5ブロック移動する。  
　・向きを右に変える。  
　・前に5ブロック移動する。  

## Step 6
2つ目のチャットコマンド：道の右側のカベを作ろう。

エージェントを次のように動かして、もう一方のカベを作り始める位置へ移動します。  
　・「動きながら置く」を偽にする。  
　・向きを左に変える。  
　・前に2ブロック移動する。  
　・向きを左に変える。   
　・前に1ブロック移動する。  

#### ~ tutorialhint

```block
player.onChat("side1", function () {
    agent.setItem(STONE, 64, 1)
    agent.setAssist(PLACE_ON_MOVE, true)
    agent.move(FORWARD, 4)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 5)
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, 5)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 2)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
})

```

## Step 7
3つ目のチャットコマンド：道の左側のカベを作ろう。

``||agent: エージェントにブロックを自分のスロットに設定させる||``ブロックを使って、  
エージェントに材料となるブロックを64個持たせよう。

## Step 8
3つ目のチャットコマンド：道の左側のカベを作ろう。

``||agent: エージェントに設定を追加||``ブロックで、「動きながら置く」を真にしよう。  

## Step 9
3つ目のチャットコマンド：道の左側のカベを作ろう。

エージェントを次のように動かして、ブロックを並べよう。  
　・前に6ブロック移動する。  
　・向きを左に変える。  
　・前に5ブロック移動する。  
　・向きを右に変える。  
　・前に3ブロック移動する。  

#### ~ tutorialhint

```block
player.onChat("side2", function () {
    agent.setItem(STONE, 64, 1)
    agent.setAssist(PLACE_ON_MOVE, true)
    agent.move(FORWARD, 6)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 5)
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, 3)
})

```
## Step 10
広場の中央あたりで、1つ目のチャットコマンドを実行する。  
次に2つ目のチャットコマンドを実行する。  
最後に3つ目のチャットコマンドを実行する。  
道はできたかな？