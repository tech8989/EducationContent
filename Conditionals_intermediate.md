### @explicitHints true

# Chopping Trees: Blocks

## Step 1
**木を切ろう**

## Step 2
**エージェントを自分の位置にもどすチャットコマンドを作ろう**  

``||player:チャットコマンドを入力した時||``を追加し、``||agent:エージェントを自分の位置にもどす||``を入れます。

### ~ tutorialHint

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## Step 3
**木を切るチャットコマンドを作ろう**  

``||player:チャットコマンドを入力した時||``を追加します。

### ~ tutorialHint
木を切る処理では、上に移動しながら木の高さ（ブロック数）を数えると同時に、葉っぱをこわしていきます。  
その後、数えた高さ分下に降りながら木を切っていきます。

## Step 4
**木を切るチャットコマンドを作ろう**  

新しい変数「高さ」を作って、``||variable: 変数高さを0にする||``を``||player:チャットコマンドを入力した時||``に追加します。

## Step 5
**木を切るチャットコマンドを作ろう**  

``||loops: もし～ならくりかえし||``を``||variable: 変数高さを0にする||``の下に追加します。  
条件を``||agent:エージェントにブロックがあるか前を確認させる||``に変えます。


## Step 6
**木を切るチャットコマンドを作ろう**  

``||loops: もし～ならくりかえし||``の中に次の処理を追加します。  
　・``||variable: 変数高さを1だけ増やす||``    
　・``||agent:エージェントに前を破壊させる||``　　**前**を**上**に変えます。  
　・``||agent: エージェントを前に移動させる||``　　**前**を**上**に変えます。  

## Step 7
**木を切るチャットコマンドを作ろう**  

``||loops:くりかえし||`` を``||loops: もし～ならくりかえし||``の下に追加し、回数を``||variable: 高さ||``にします。

## Step 8
**木を切るチャットコマンドを作ろう**  

``||loops:くりかえし||``の中に次の処理を追加します。  
　・``||agent: エージェントを前に移動させる||``   　　**前**を**下**に変えます。   
　・``||agent:エージェントに前を破壊させる||``  
　・``||agent:エージェントに全てひろわせる||``

### ~ tutorialHint

```blocks
let 高さ = 0
player.onChat("c", function () {
    高さ = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        高さ += 1
        agent.destroy(UP)
        agent.move(UP, 1)
    }
    for (let index = 0; index < 高さ; index++) {
        agent.move(DOWN, 1)
        agent.destroy(FORWARD)
        agent.collectAll()
    }    
})
```

## Step 9

木の前に行って、エージェント呼び、木を切らせよう！
