# 課題1
```logo
cs rt -90 repeat 3 [fd 100 rt -120]
```

# 課題2
```logo
cs make “a 0 repeat 100 [setx :a sety 0 fd 100 make “a :a+1]
```

# 課題3
```logo
cs make “a 0 repeat 30 [make “a :a+10 fd :a rt 60]
```

#  課題4
```logo
cs rt 1 repeat 100 [ifelse greater? random 3 0 [setpc 4 fd 50] [setpc 2 fd 50]]
```

# 課題5
```logo
to scroll :d 
  make “a 0
  repeat 30 [make “a :a+10 fd :a rt d]
end
```

# 課題6
```logo
to scroll2 :d :color :loop
  make “a 0
  setpc :color
  repeat :loop [make “a :a+10 fd :a rt d]
end
```

# 課題7
```logo
to edge :a
  if greater? :a 0 [ fd 100 rt 60 edge :a-1]
end

edge 6
```

# 課題8
```logo
to tree :x :n
  setpc :n
  if :n = 0 [ stop ]
  lt 30 fd :x
  tree :x :n-1
  setpc :n
  pu bk :x pd
  rt 60 fd :x
  tree :x :n-1
  setpc :n
  pu bk :x pd lt 30
end
```

# 課題9
```logo
to tree2 :x :n
  if :n = 0 [ stop ]
  lt 30 fd :x
  tree :x :n-1
  pu bk :x pd
  rt 60 fd :x/2
  tree :x :n-1
  pu bk :x/2 pd lt 30
end
```

# 課題10
```logo
to koch1 :length
  fd :length/3
  lt 60
  fd :length/3
  rt 120
  fd :length/3
  lt 60
  fd :length/3
end
```

# 課題11
```logo
to koch :length :depth
  ifelse :depth > 0 [
    koch :length/3 :depth-1
    lt 60
    koch :length/3 :depth-1
    rt 120
    koch :length/3 :depth-1
    lt 60
    koch :length/3 :depth-1
  ][
    fd :length
  ]
end
```

# 課題12
```
cs pu setpos[-200 200] pd rt 90 repeat 6 [koch 100 3 rt 60]
```
