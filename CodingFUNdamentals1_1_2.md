### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move to the gold plate!

## Step 1
エージェントを動かして、金の感圧板をふませよう。  
  
``||player:チャットコマンドを入力した時||`` の中に、``||agent:エージェントを前に移動||``を入れるよ。 


#### ~ tutorialhint 
エージェントに金の感圧板をふませるには何ブロック前に移動すれば、いいかな？  
``||agent:エージェントを前に移動||`` の数字を変えよう！  
  
エージェントの向きは、``||agent:エージェントの向きを変える||``を使って変えれるよ！



```ghost
player.onChat("1", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

``` 