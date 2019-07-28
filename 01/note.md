## 1.1

```
Prelude> 2 + 15
17
Prelude> 49 * 100
4900
Prelude> succ 8
9
Prelude> min 9 10
9
Prelude> min 3.4 3.2
3.2
Prelude> max 100 101
101
Prelude>  succ 9 + max 5 4
15
Prelude> succ 9 * 10
100
Prelude> succ (9 * 10)
91
Prelude> div 92 10
9
Prelude> 92 `div` 10
9
```

## 1.2

### 関数呼び出し

```
Prelude> :l baby
[1 of 1] Compiling Main             ( baby.hs, interpreted )
Ok, one module loaded.
*Main> doubleMe 9
18
*Main> doubleMe 8.3
16.6
*Main> :l baby
[1 of 1] Compiling Main             ( baby.hs, interpreted )
Ok, one module loaded.
*Main> doubleUs 4 9
26
*Main> doubleUs 2.4 34.2
73.2
*Main> doubleUs 28 88 + doubleMe 123
478
*Main> :l baby
[1 of 1] Compiling Main             ( baby.hs, interpreted )
Ok, one module loaded.
*Main> doubleUs 4 9
26
```

## 1.3

```
*Main> let lostNumbers = [4, 8, 15, 16, 23, 42]
*Main> lostNumbers
[4,8,15,16,23,42]
```

### 1.3.1

```
*Main> [1,2,3,4] ++ [9,10,11,12]
[1,2,3,4,9,10,11,12]
*Main> "hello" ++ " " ++ "world"
"hello world"
*Main> ['w','o'] ++ ['o','t']
"woot"
```

```
*Main> 'A':" SMALL CAT"
"A SMALL CAT"
*Main> 5:[1,2,3,4,5]
[5,1,2,3,4,5]
```

```
*Main> [1,2,3,4] ++ [5]
[1,2,3,4,5]
*Main> 1:2:3:4:[] ++ 5:[]
[1,2,3,4,5]
```

### 1.3.2

```
Prelude> "Steve Buscemi" !! 6
'B'
Prelude> [9.4,33.2,96.2,11.2,23.25] !! 1
33.2
Prelude> [9.4,33.2,96.2,11.2,23.25] !! 6
*** Exception: Prelude.!!: index too large
```

### 1.3.3

```
Prelude> let b = [[1,2,3,4],[5,3,3,3],[1,2,2,3,4],[1,2,3]]
Prelude> b
[[1,2,3,4],[5,3,3,3],[1,2,2,3,4],[1,2,3]]
Prelude> b ++ [[1,1,1,1]]
[[1,2,3,4],[5,3,3,3],[1,2,2,3,4],[1,2,3],[1,1,1,1]]
Prelude> [6,6,6]:b
[[6,6,6],[1,2,3,4],[5,3,3,3],[1,2,2,3,4],[1,2,3]]
Prelude> b !! 2
[1,2,2,3,4]
```

### 1.3.4

```
Prelude> [3,2,1] > [2,1,0]
True
Prelude> [3,2,1] > [2,10,100]
True
Prelude> [3,4,2] < [3,4,3]
True
Prelude> [3,4,2] > [2,4]
True
Prelude> [3,4,2] == [3,4,2]
True
```

### 1.3.5

```
Prelude> head [5,4,3,2,1]
5
Prelude> tail [5,4,3,2,1]
[4,3,2,1]
Prelude> last [5,4,3,2,1]
1
Prelude> init [5,4,3,2,1]
[5,4,3,2]
Prelude> head []
*** Exception: Prelude.head: empty list
Prelude> length [5,4,3,2,1]
5
Prelude> null [1,2,3]
False
Prelude> null []
True
Prelude> reverse [5,4,3,2,1]
[1,2,3,4,5]
Prelude> take 3 [5,4,3,2,1]
[5,4,3]
Prelude> take 1 [3,9,3]
[3]
Prelude> take 5 [1,2]
[1,2]
Prelude> take 0 [6,6,6]
[]
Prelude> drop 3 [8,4,2,1,5,6]
[1,5,6]
Prelude> drop 0 [1,2,3,4]
[1,2,3,4]
Prelude> drop 100 [1,2,3,4]
[]
Prelude> maximum [1,9,2,3,4]
9
Prelude> minimum [8,4,2,1,5,6]
1
Prelude> sum [5,2,1,6,3,2,5,7]
31
Prelude> product [6,2,1,2]
24
Prelude> product [1,2,5,6,7,9,2,0]
0
Prelude> 4 `elem` [3,4,5,6]
True
Prelude> 10 `elem` [3,4,5,6]
False
```

## 1.4

```
Prelude> [1..20]
[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20]
Prelude> ['a'..'z']
"abcdefghijklmnopqrstuvwxyz"
Prelude> ['K'..'Z']
"KLMNOPQRSTUVWXYZ"

Prelude> [2,4..20]
[2,4,6,8,10,12,14,16,18,20]
Prelude> [3,6..20]
[3,6,9,12,15,18]
Prelude> [20,19..1]
[20,19,18,17,16,15,14,13,12,11,10,9,8,7,6,5,4,3,2,1]

Prelude> [13,26..24*13]
[13,26,39,52,65,78,91,104,117,130,143,156,169,182,195,208,221,234,247,260,273,286,299,312]
Prelude> take 24 [13,26..]
[13,26,39,52,65,78,91,104,117,130,143,156,169,182,195,208,221,234,247,260,273,286,299,312]

Prelude> take 10 (cycle [1,2,3])
[1,2,3,1,2,3,1,2,3,1]
Prelude> take 12 (cycle "LOL ")
"LOL LOL LOL "
Prelude> take 10 (repeat 5)
[5,5,5,5,5,5,5,5,5,5]
Prelude> replicate 3 10
[10,10,10]

Prelude> [0.1, 0.3 .. 1]
[0.1,0.3,0.5,0.7,0.8999999999999999,1.0999999999999999]
```

## 1.5

```
Prelude> [x*2 | x <- [1..10]]
[2,4,6,8,10,12,14,16,18,20]

Prelude> [x*2 | x <- [1..10], x*2 >= 12]
[12,14,16,18,20]
Prelude> [ x | x <- [50..100], x `mod` 7 == 3]
[52,59,66,73,80,87,94]

*Main> :l intensionalDefinition.hs
[1 of 1] Compiling Main             ( intensionalDefinition.hs, interpreted )
Ok, one module loaded.
*Main> boomBangs [7..13]
["BOOM!","BOOM!","BANG!","BANG!"]
*Main> [ x | x <- [10..20], x /= 13, x /= 15, x /= 19]
[10,11,12,14,16,17,18,20]

*Main> [x+y | x <- [1,2,3], y <- [10,100,1000]]
[11,101,1001,12,102,1002,13,103,1003]

*Main> [ x*y | x <- [2,5,10], y <- [8,10,11]]
[16,20,22,40,50,55,80,100,110]
*Main> [ x*y | x <- [2,5,10], y <- [8,10,11], x*y > 50]
[55,80,100,110]
*Main> let nouns = ["hobo","frog","pope"]
*Main> let adjectives = ["lazy","grouchy","scheming"]
*Main> [adjective ++ " " ++ noun | adjective <- adjectives, noun <- nouns]
["lazy hobo","lazy frog","lazy pope","grouchy hobo","grouchy frog","grouchy pope","scheming hobo","scheming frog","scheming pope"]

Prelude> :l intensionalDefinition.hs
[1 of 1] Compiling Main             ( intensionalDefinition.hs, interpreted )
Ok, one module loaded.
*Main> length' [1,2,3,4,5]
5
*Main> removeNonUppercase "Hahaha! Ahahaha!"
"HA"
*Main> removeNonUppercase "IdontLIKEFROGS"
"ILIKEFROGS"

*Main> let xxs = [[1,3,5,2,3,1,2,4,5],[1,2,3,4,5,6,7,8,9],[1,2,4,2,1,6,3,1,3,2,3,6]]
*Main> [ [ x | x <- xs, even x ] | xs <- xxs]
[[2,2,4],[2,4,6,8],[2,4,2,6,2,6]]
```

## 1.6

```
Prelude> (1, 3)
(1,3)
Prelude> (3, 'a', "hello")
(3,'a',"hello")
Prelude> (50, 50.4, "hello", 'b')
(50,50.4,"hello",'b')
```

