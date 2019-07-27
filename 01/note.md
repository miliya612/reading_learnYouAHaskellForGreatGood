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