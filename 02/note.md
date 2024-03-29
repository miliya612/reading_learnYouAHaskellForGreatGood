# 2

## 2.1

```
Prelude> :t 'a'
'a' :: Char
Prelude> :t True
True :: Bool
Prelude> :t "HELLO!"
"HELLO!" :: [Char]
Prelude> :t (True, 'a')
(True, 'a') :: (Bool, Char)
Prelude> :t 4 == 5
4 == 5 :: Bool
```

## 2.2

```
Prelude> :t 7
7 :: Num p => p
Prelude> :l generalType.hs
[1 of 1] Compiling Main             ( generalType.hs, interpreted )
Ok, one module loaded.
*Main> factorial 50
30414093201713378043612608166064768844377641568960512000000000000
Prelude> :l generalType.hs
[1 of 1] Compiling Main             ( generalType.hs, interpreted )
Ok, one module loaded.
*Main> circumference 4.0
25.132742
Prelude> :l generalType.hs
[1 of 1] Compiling Main             ( generalType.hs, interpreted )
Ok, one module loaded.
*Main> circumference' 4.0
25.132741228718345

*Main> :t True
True :: Bool
*Main> :t 'a'
'a' :: Char
*Main> :t (3, 'a')
(3, 'a') :: Num a => (a, Char)
*Main> :t ('a', 'b')
('a', 'b') :: (Char, Char)
```

## 2.3

```
*Main> :t head
head :: [a] -> a
*Main> :t fst
fst :: (a, b) -> a
```

## 2.4

```
*Main> :t (==)
(==) :: Eq a => a -> a -> Bool
```

## 2.4.1

```
*Main> 5 == 5
True
*Main> 5 /= 5
False
*Main> 'a' == 'a'
True
*Main> "Ho Ho" == "Ho Ho"
True
*Main> 3.432 == 3.432
True

*Main> :t (>)
(>) :: Ord a => a -> a -> Bool
*Main> "Abrakadabra" < "Zebra"
True
*Main> "Abrakadabra" `compare` "Zebra"
LT
*Main> 5 >= 2
True
*Main> 5 `compare` 3
GT
*Main> 'b' > 'a'
True

*Main> show 3
"3"
*Main> show 5.334
"5.334"
*Main> show True
"True"

*Main> read "True" || False
True
*Main> read "8.2" + 3.8
12.0
*Main> read "5" - 2
3
*Main> read "[1,2,3,4]" ++ [3]
[1,2,3,4,3]
*Main> read "4"
*** Exception: Prelude.read: no parse
*Main> :t read
read :: Read a => String -> a

*Main> read "5" :: Int
5
*Main> read "5" :: Float
5.0
*Main> (read "5" :: Float) * 4
20.0
*Main> read "[1,2,3,4]" :: [Int]
[1,2,3,4]
*Main> read "(3, 'a')" :: (Int, Char)
(3,'a')

*Main> [read "True", False, True, False]
[True,False,True,False]
```

### 2.4.5

```
*Main> ['a'..'e']
"abcde"
*Main> [LT .. GT]
[LT,EQ,GT]
*Main> [3 .. 5]
[3,4,5]
*Main> succ 'B'
'C'
```

### 2.4.6

```
*Main> minBound :: Int
-9223372036854775808
*Main> maxBound :: Char
'\1114111'
*Main> maxBound :: Bool
True
*Main> minBound :: Bool
False

*Main> :t maxBound
maxBound :: Bounded a => a
*Main> :t minBound
minBound :: Bounded a => a
*Main> maxBound :: (Bool, Int, Char)
(True,9223372036854775807,'\1114111')
```

### 2.4.7

```
*Main> :t 20
20 :: Num p => p
*Main> 20 :: Int
20
*Main> 20 :: Integer
20
*Main> 20 :: Float
20.0
*Main> 20 :: Double
20.0

*Main> :t (*)
(*) :: Num a => a -> a -> a
```

### 2.4.8

```
*Main> :t sin
sin :: Floating a => a -> a
*Main> :t cos
cos :: Floating a => a -> a
*Main> :t sqrt
sqrt :: Floating a => a -> a
```

### 2.4.9

```
Prelude> :t fromIntegral
fromIntegral :: (Integral a, Num b) => a -> b
Prelude> :t length
length :: Foldable t => t a -> Int
Prelude> length [1,2,3,4] + 3.2

<interactive>:3:20: error:
    • No instance for (Fractional Int) arising from the literal ‘3.2’
    • In the second argument of ‘(+)’, namely ‘3.2’
      In the expression: length [1, 2, 3, 4] + 3.2
      In an equation for ‘it’: it = length [1, 2, 3, ....] + 3.2
Prelude> fromIntegral (length [1,2,3,4]) + 3.2
7.2
```

