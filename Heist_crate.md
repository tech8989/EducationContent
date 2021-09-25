### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @flyoutOnly true
### @hideIteration true 
### @explicitHints 1

# Suspicious Crates

## Step 1
たくさんの木箱の間を通って、ぬすまれた絵画の一部がないか調べよう。  
絵画があったら、その箱をこわして、手に入れよう。  
  
答えは何パターンもあるので、いろんなパターンを考えてみよう。  
  
**ブロックの説明:**  
``||ww:Move [forward] by (0)||`` ワンダーウーマンを指定したブロック分 動かせる。  
　　※　forward=前　back=後ろ　left=左　right=右  
``||ww:Turn [左]||`` ワンダーウーマンの向きを変える。  
``||ww:painting inside crate [forward]||`` 木箱の中に絵画がないかを調べる。  
``||ww:Break crate [forward]||`` 木箱を壊す。


```ghost
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 1)
    ww.turnWW(LEFT_TURN)
    if (ww.locatePainting(Direction.Forward)) {
        ww.retrievePainting(Direction.Forward)
    }
    for (let index = 0; index < 4; index++) {
        
    }
    while (!(false)) {
        
    }	
})
```
```template
player.onChat("run", function () {
    if (ww.locatePainting(Direction.Forward)) {

    }
})
```
```package
minecraft-ww1984=github:ReWrite-Media/ww1984-ts
```