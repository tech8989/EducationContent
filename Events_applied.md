### @explicitHints true

# Tutorial

## Step 1
いろいろな場面で、イベントを使ったプログラムを作ろう。

```ghost 
player.onTravelled(WALK, function () {
    mobs.spawn(PRIMED_TNT, pos(0, 0, 0))
    while (true) {
    	
    }

    for (let index = 0; index < 4; index++) {
        gameplay.timeSet(gameplay.time(DAY))
        gameplay.setWeather(CLEAR)
        test = positions.add(
        player.position(),
        pos(0, 0, 0)
        )
        mobs.spawn(CHICKEN, randpos(
        pos(0, 0, 0),
        pos(0, 0, 0)
        ))        
        
    }
})

player.onItemInteracted(IRON_SHOVEL, function() {
    
})

let item: number
item += 1

```