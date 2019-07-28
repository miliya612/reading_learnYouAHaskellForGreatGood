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
```


