### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move up to the gold plate!

## Step 1
�G�[�W�F���g��**�㉺**�Ɉړ����āA���̊������ӂ܂��悤
#### ~ tutorialhint 
``||agent:�G�[�W�F���g��O�Ɉړ�||`` �́u�O�v�̕����͕ς��邱�Ƃ��ł����B 
   
�G�[�W�F���g�ɋ��̊������ӂ܂���ɂ͂ǂ��ړ�����΁A�������ȁH

```ghost
player.onChat("up", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

```  