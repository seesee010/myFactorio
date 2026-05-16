# Blueprint stand

Here you will find all my blueprint doc I am using in factorio.

> [!NOTE]
> "(?= ...)" syntax is used to mark some code for some future chapter - 
> it does not mean that they are unsolved or something like that- 
> but only that it will be answered later on.

## Crafter

```
c:y:2i2o\##
```

c -> crafter blueprint
y -> it uses only yellow / yellow tier - mixing is not in the blueprint system (it just isnt that good)
    \ Except: if the blueprint uses something like some sort of mixed tiers (for example: it is not possible without that) then you write X instead of any tier.
    \ possible tiers: y, r, b, g, X (?= as exception)

2i2o -> everything before i and after ':' means the input amount - for example belts
    \ everything after i and before o means output amount of belts for example.

'\' -> after that there is the "identifier mode"

### Identifier Mode
this is a block of the blueprint namingf convention, where you can specify some things.

If you are using just everything normal (?= view specialities for more information), then you just write "##" 
as for example: `c:X:2i1o\##` -> everything is normal

#### What normality means
It refers to the fact that every item uses their own belt / chest / etc...

#### How non-normal looks

`c:X:2i1o\a/b_#`

the identifier block can be split into 2 sub blocks - input and output,
they are virtually split by using '_' as separator.

If you make everything normal you could have already seen that you dont use '_' you just write: "\##"

In the example above:
the input is split 1/2 and 1/2 using one belt only and 1 for output.

> [!NOTE]
> It will auto split using the right numbers (if a/b/c it will use 1/3 1/3 1/3 - or .33333333333333333... / .33333333333333333... / .33333333333333333...)
> (?= see special cases for more information about that system)

### Special cases

If you want to split some items not using 1/2 and 1/2 you can say that by using:
`(.2)` as percentage... (0.2)(=0.2 from 1.0 =20%)
for example:
```
c:b:2i1o\(.4)a/(.6)b_#
```
input is split as 40% a and 60% b, or like:
```
c:b:2i1o\(1/77)a/(76/77)b_#
```

Here the other syntax is used, but is marked as "Do NEVER USE" - because it would be to complex

> [!NOTE]
> There are multiple ways to write 100%
>
> a) use .X -> this will add up to 1.0, which will stand for 100%
> b) use 20 -> 20 as 20%
> c) use X/y -> fully custom possible

> [!NOTE]
> The best way to write percentage is to just write .2 and .6
> but every other method as given is also allowed - 
> but for ME .X is the shorter and better way to write percent down...

#### Differences:

(6)a/(4)b vs (.6)a/(.4)b are NOT THE SAME
up to 100%      up to 1.0
