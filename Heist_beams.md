### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @flyoutOnly true
### @hideIteration true 
### @explicitHints 1

# Beams of Color

## Step 1
壁にある色付きブロックと同じ色順になるように、色付きガラスを置こう。  
  
**ブロックの説明:**  
``||ww:Move [forward] by (0)||`` ワンダーウーマンを指定したブロック分 動かせる。  
　　※　forward=前　back=後ろ　left=左　right=右  
``||ww:Turn [左]||`` ワンダーウーマンの向きを変える。  
``||ww:Place [Yellow] Stained Glass [forward]||`` ワンダーウーマンにガラスを置かせる。  
　　※　Yellow=黄色　Lime=ライム　Blue=青　Red=赤  

#### ~ tutorialhint 
```blocks
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 3)
    ww.placeBlock(BeamsGlass.RedStainedGlass, Direction.Left)
    ww.moveWW(Direction.Forward, 3)
    ww.placeBlock(BeamsGlass.LimeStainedGlass, Direction.Left)
    ww.moveWW(Direction.Forward, 3)
    ww.placeBlock(BeamsGlass.BlueStainedGlass, Direction.Left)
    ww.moveWW(Direction.Forward, 3)
    ww.placeBlock(BeamsGlass.YellowStainedGlass, Direction.Left)
})

```
```ghost
player.onChat("run", function () {
    for (let index = 0; index < 4; index++) {
        ww.moveWW(Direction.Forward, 1)
        ww.turnWW(LEFT_TURN)
        ww.placeBlock(BeamsGlass.YellowStainedGlass, Direction.Forward)
    }
})
```
```template
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 3)
    ww.placeBlock(BeamsGlass.LimeStainedGlass, Direction.Right)
})
```
```package
minecraft-ww1984=github:ReWrite-Media/ww1984-ts
```