### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @flyoutOnly true
### @hideIteration true
### @explicitHints 1

# Dance Floor

## Step 1
ワンダーウーマンをプログラムして、壁にかかれているのと同じ色順で動くようにしよう。  
そうすれば、奥の壁にあるひみつのとびらが開くよ。

**ブロックの説明:**  
``||ww:Move [forward] by (0)||`` ワンダーウーマンを指定したブロック分 動かせる。  
　　※　forward=前　back=後ろ　left=左　right=右  
``||ww:Turn [左]||`` ワンダーウーマンの向きを変える。  

#### ~ tutorialhint 
```blocks
player.onChat("run", function () {
    ww.moveWW(Direction.Right, 4)
    ww.moveWW(Direction.Forward, 12)
    ww.moveWW(Direction.Right, 4)
})
player.onChat("run", function () {
    ww.turnWW(RIGHT_TURN)
    ww.moveWW(Direction.Forward, 4)
    ww.turnWW(LEFT_TURN)
    ww.moveWW(Direction.Forward, 12)
    ww.turnWW(RIGHT_TURN)
    ww.moveWW(Direction.Forward, 4)
})

```
```ghost
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 1)
    ww.turnWW(LEFT_TURN)
    for (let index = 0; index < 4; index++) {
        
    }
})
```
```template
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 1)
    ww.turnWW(RIGHT_TURN)
})
```
```package
minecraft-ww1984=github:ReWrite-Media/ww1984-ts
```