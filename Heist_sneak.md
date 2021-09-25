### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @flyoutOnly true
### @hideIteration true
### @explicitHints 1

# Stealth Mission

## Step 1
�A���[�����Ȃ�Ȃ��悤�Ƀ��[�U�[�������āA�Ɛl�̌��ɍs����悤�ɁA  
�����_�[�E�[�}���𓮂������B  
���ɂ�����A``||ww:Takedown criminal [forward]||`` ���g���āA�Ɛl��|�����B
  
**�u���b�N�̐���:**  
``||ww:Move [forward] by (0)||`` �����_�[�E�[�}�����w�肵���u���b�N�� ��������B  
�@�@���@forward=�O�@back=���@left=���@right=�E  
``||ww:Turn [��]||`` �����_�[�E�[�}���̌�����ς���B  
``||ww:Takedown criminal [forward]||`` �w�肵�������̔Ɛl��|���B

#### ~ tutorialhint 
```blocks
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 1)
    ww.turnWW(LEFT_TURN)
    ww.moveWW(Direction.Forward, 3)
    ww.turnWW(RIGHT_TURN)
    ww.moveWW(Direction.Forward, 6)
    ww.turnWW(RIGHT_TURN)
    ww.moveWW(Direction.Forward, 6)
    ww.turnWW(LEFT_TURN)
    ww.moveWW(Direction.Forward, 3)
    ww.turnWW(LEFT_TURN)
    ww.moveWW(Direction.Forward, 3)
    ww.turnWW(RIGHT_TURN)
    ww.moveWW(Direction.Forward, 2)
    ww.takedownGoon(Direction.Forward)
})
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 1)
    ww.moveWW(Direction.Left, 3)
    ww.moveWW(Direction.Forward, 6)
    ww.moveWW(Direction.Right, 6)
    ww.moveWW(Direction.Forward, 3)
    ww.moveWW(Direction.Left, 3)
    ww.moveWW(Direction.Forward, 2)
    ww.takedownGoon(Direction.Forward)
})
```

```ghost
player.onChat("run", function () {
    for (let index = 0; index < 4; index++) {
        ww.moveWW(Direction.Forward, 1)
        ww.turnWW(LEFT_TURN)
        ww.takedownGoon(Direction.Forward)
    }
})
```
```template
player.onChat("run", function () {
    ww.moveWW(Direction.Forward, 1)
    ww.turnWW(LEFT_TURN)
})
```
```package
minecraft-ww1984=github:ReWrite-Media/ww1984-ts
```