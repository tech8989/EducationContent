### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move up to the gold plate!

## Step 1
�G�[�W�F���g�ɐ��������ǂ点�āA���̊������ӂ܂��悤�B  
�����ɁA�I�����W�̓��̐�ɂ��銴���������łӂ����B  
�ǂ����10�b�ȓ��ɂӂނ��Ƃ��ł���΁A**�N���A**����I

```ghost
player.onChat("last", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
```  