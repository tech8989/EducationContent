### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1


# CODING TUTORIALS: シーケンス 初級

## Step 1
エージェントを動かすためのチャットコマンドを4つ作ります。  
４つ作ったらエージェントをいろいろ動かしてみよう。

## Step 2
1.エージェントを自分の位置へ戻そう。

```ghost
player.onChat("farm", function () {
    agent.teleportToPlayer()
    agent.move(FORWARD, 1)
    agent.turn(RIGHT)
    
})

``` 

#### ~ tutorialhint

```block
player.onChat("tp", function () {
    agent.teleportToPlayer()
})

``` 

## Step 3
2.エージェントを前に1ブロック移動させよう。

#### ~ tutorialhint

```block
player.onChat("fd", function () {
    agent.move(FORWARD, 1)
})

``` 

## Step 4
3.エージェントの向きを左に変えよう。

#### ~ tutorialhint

```block
player.onChat("lt", function () {
    agent.turn(LEFT_TURN)
})

``` 


## Step 5
4.エージェントの向きを右に変えよう。

#### ~ tutorialhint

```block
player.onChat("rt", function () {
    agent.turn(RIGHT_TURN)
})

```
