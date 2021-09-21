### @explicitHints true

# CODING TUTORIALS: Forループ 中級

## Step 1
**畑ににんじんを植えよう**  
![agent build path](https://teck89.xsrv.jp/MEE_tutorial/img/forloops_intermediate.png)


## Step 2
はじめに、エージェントを自分の位置へ戻すチャットコマンドを作ろう。  
``||player: チャットコマンドを入力した時||`` エージェントを自分の位置へ戻そう。  

### ~ tutorialhint

```block
player.onChat("tp", function () {
    agent.teleportToPlayer()
})

``` 

```ghost
player.onChat("farm", function () {
    agent.setItem(CARROTS, 64, 1)
    for (let index = 0; index < 5; index++) {
        agent.till(FORWARD)
        agent.move(FORWARD, 1)
        agent.place(FORWARD)
    }
})

``` 

## Step 3
次に、にんじんを植えるチャットコマンドを作ろう。  
1つ目とは別の``||player: チャットコマンドを入力した時||``を追加しよう。 


## Step 4

まず、``||agent: エージェントにブロックを設定させる||``ブロックで、エージェントににんじんを64個持たせよう。

## Step 5

にんじんをエージェントに持たせた後に、1列にんじんを植えるようにしよう。
``||loops: くりかえし||``ブロックを追加して、次の処理を7回くり返すようにしよう。

1.エージェントに前を耕させる。  
2.エージェントに前に1ブロック移動させる。  
3.エージェントに下へ置かせる。


## Step 6

1列植えた後、次の列に移動するようにしよう。

1.エージェントを後ろに7ブロック移動させる。  
2.エージェントを右に4ブロック移動させる。

## Step 7

にんじんを2列植えるようにしよう。

``||loops: くりかえし||``ブロックを追加し、くりかえし2回にする。
1列植える処理、次の列に移動する処理をその中に入れる。


#### ~ tutorialhint
```blocks
player.onChat("farm", function () {
    agent.setItem(CARROTS, 64, 1)
    for (let index = 0; index < 2; index++) {
        for (let index = 0; index < 7; index++) {
            agent.till(FORWARD)
            agent.move(FORWARD, 1)
            agent.place(DOWN)
        }
        agent.move(BACK, 7)
        agent.move(RIGHT, 4)
    }
})
```