### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Program the Agent to move to the gold plate!

## Step 1
�G�[�W�F���g�𓮂����āA���̊������ӂ܂��悤�B  
  
``||player:�`���b�g�R�}���h����͂�����||`` �̒��ɁA``||agent:�G�[�W�F���g��O�Ɉړ�||``�������B 


#### ~ tutorialhint 
�G�[�W�F���g�ɋ��̊������ӂ܂���ɂ͉��u���b�N�O�Ɉړ�����΁A�������ȁH  
``||agent:�G�[�W�F���g��O�Ɉړ�||`` �̐�����ς��悤�I  
  
�G�[�W�F���g�̌����́A``||agent:�G�[�W�F���g�̌�����ς���||``���g���ĕς�����I



```ghost
player.onChat("1", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

``` 