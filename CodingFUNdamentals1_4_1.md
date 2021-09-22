### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Secure the Area

## Step 1
**柵(さく)でかこおう**  
エージェントに樫の木の柵を持たせて、右側におかせよう。17個必要だよ。  
また、前のブロックは、こわそう。

#### ~ tutorialhint
```blocks
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
        agent.place(RIGHT)
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
    }
})
```

