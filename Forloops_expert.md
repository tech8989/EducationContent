### @explicitHints true

# CODING TUTORIALS: Forループ 上級

## Step 1
**家をたてよう**

はじめに、``||player: チャットコマンドを入力した時||`` エージェントを自分の位置へ戻そう。

![agent build path](https://teck89.xsrv.jp/MEE_tutorial/img/forloops_expert.png)


```ghost
player.onChat("farm", function () {
    agent.teleportToPlayer()
    agent.setItem(CARROTS, 64, 1)
    for (let index = 0; index < 5; index++) {
        agent.move(FORWARD, 1)
        agent.place(FORWARD)
        agent.turn(RIGHT)
    }
})

``` 
#### ~ tutorialhint

```block

player.onChat("tp", function () {
    agent.teleportToPlayer()
})

``` 

## Step 2
家のカベ作り

次に、家のカベを作るため、1つ目とは別の``||player: チャットコマンドを入力した時||``ブロックを追加しよう。 

## Step 3
家のカベ作り

``||agent: エージェントにブロックを設定させる||``で、エージェントにアカシアの木材を64個持たせる。  
エージェントを上に1ブロック移動させる。

## Step 4
家のカベ作り

カベを1辺を作るため、次の2つの処理を``||loops: くりかえし||``4回の中に入れよう。    
　・エージェントに下に置かせる。  
　・エージェントを前に1ブロック移動させる。

その後、エージェントの向きを右に変えよう。

## Step 5
家のカベ作り

カベを1周作るため、新たに``||loops: くりかえし||``ブロックを追加して、
カベを1辺作る処理を4回くり返そう。

## Step 6
家のカベ作り

カベの高さを3段にするため、新たに``||loops: くりかえし||``を追加して、
「エージェントを上に1ブロック移動させる」と
カベを1周作る処理を3回くり返そう。

#### ~ tutorialhint

```block

player.onChat("wall", function () {
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

## Step 7
家の屋根作り

家の屋根を作るため、新たに``||player: チャットコマンドを入力した時||``ブロックを追加しよう。 


## Step 8
家の屋根作り

エージェントにレンガのハーフブロックを64個持たせて、
エージェントを上に1ブロック移動させよう。

## Step 9
家の屋根作り

``||loops: くりかえし||``5回の中に``||loops: くりかえし||``5回を入れよう。

## Step 10
家の屋根作り

内側の``||loops: くりかえし||``の中に次の処理を入れよう。

・エージェントに下へ置かせる。  
・エージェントを前に1ブロック移動させる。

## Step 11
家の屋根作り

内側の``||loops: くりかえし||``の下に、次の処理を入れよう。

・エージェントを右に1ブロック移動させる。  
・エージェントを後ろに5ブロック移動させる。


#### ~ tutorialhint
```blocks
player.onChat("roof", function () {
    agent.setItem(BRICKS_SLAB, 64, 1)
    agent.move(UP, 1)
    for (let index = 0; index < 5; index++) {
        for (let index = 0; index < 5; index++) {
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.move(RIGHT, 1)
        agent.move(BACK, 5)
    }
})
```

##Step 12
プログラムができたら、家をたてよう。  
　1.家をたてたい所にエージェントを移動しよう。  
　2.カベを作るチャットコマンドを実行しよう。  
　3.屋根を作るチャットコマンドを実行しよう。