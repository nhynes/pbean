# pbean

*A simple, healthy, and convenient vegan meal.*

<img src="nutrition_facts.png" width="250px">

## Recipe

The following recipe makes 12 servings.

### Ingredients

* 432 g navy beans (or other white bean); soaked
* 425 g smooth peanut butter (must contain only peanuts)
* 185 g cocoa powder
* 79 g chia seeds (57 g ground, 22g whole)
* 12 g iodized salt

### Directions

1. pressure cook beans for about 10 minutes
2. blend all ingredients
3. dilute to 5.68 L (1.5 gal)
4. refrigerate for up to six days

## Tips

### Equipment

* immersion blender
* funnel
* half-gallon jugs
* coffee grinder

### Flavors

* good: vanilla, mint, coffee, coconut
* okay: pumpkin pie spice
* bad: strawberry, banana

### Additives

* citric/lactic acid - just in case you want to pretend you're drinking kefir
* sunflower lecithin - helps keep phases mixed while bottling and serving


## FAQ

* Can I drink pbean and nothing else? No. You must supplement it with at a few leaves of kale (or other Brassica) to get the RDA of vitamins A, C, and K.
* Can I use other nut butters? Yes, but the flavor will not change much.


## Optimization

Feed the following linear program into your favorite LP solver.

```
Maximize f = .3074h + .1370c + .5136p + .015b
4.86h + 2.28c + 5.98p + 3.37b = 4000
.00772627h + .010110375c + .0044150p + .0032891832b <= 5
.1654h + .1960c + .2221p + .2233b >= 200
.17840h >= 5.5
.12264p - .65485h <= 0
```

f is fat, h is chia, c is cocoa, p is peanut butter, and b is beans.

The objective is to maximize fat (as a proxy for flavor) subject to having 20 g protein per serving, enough ALA, and a 4:1 omega6:omega3 ratio.
The cost for 10 servings is also constrained to be less than $5, but that's more to prevent unreasonable solutions like peanut butter cocoa water (which isn't as tasty as it sounds and raises the question of whether maximizing fat is the correct objective).
