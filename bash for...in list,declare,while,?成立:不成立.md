# bash for...in list,declare,while,?成立:不成立

---

* for...in list

![](https://i.imgur.com/73u1dUa.jpg)

![](https://i.imgur.com/Z2LVLVz.jpg)

```
#!/bin/bash
arg="luba luba1 luba2"
for x in $arg
do
cat /etc/passwd | grep $x >/dev/null
if [ $? = 0 ];then
  echo "存在不建立"
else
  echo "不存在幫您建立" && sudo useradd -m -s /bin/bash $x
fi
done
```

---

* declare

![](https://i.imgur.com/or7xfeY.jpg)

![](https://i.imgur.com/10EOvAI.jpg)

![](https://i.imgur.com/cNmcJr6.jpg)

![](https://i.imgur.com/aoUJQd9.jpg)

1100,-900,100000,0

![](https://i.imgur.com/KjUtVe3.jpg)

![](https://i.imgur.com/72QEWgX.jpg)

![](https://i.imgur.com/2aNtEe2.jpg)

---

* while do...done

![](https://i.imgur.com/5pTM0E7.jpg)

![](https://i.imgur.com/1Z6QS3O.jpg)

![](https://i.imgur.com/vQmW4Ft.jpg)

```
#!/bin/bash
no=1
sum=0
while (( no <= 100 ))
do
if [ $((no%2)) -eq 1 ];then
  sum=$((sum+no))
  no=$((no+1))
else
  no=$((no+1))
fi
done
echo $sum
```
![](https://i.imgur.com/USv9TbP.jpg)

```
#!/bin/bash
sum=0
read -p "star" star
read -p "end" end
while (( star <= end ))
do
if [ $((star%2)) -eq 1 ];then
  sum=$((sum+star))
  star=$((star+1))
else
  star=$((star+1))
fi
done
echo $sum
```
![](https://i.imgur.com/SBjrIOO.jpg)

```
#!/bin/bash
x=0
while (( x <= 19 ))
do
x=$((x+1))
if [ $x = 3 ] || [ $x = 11 ];then
  continue
else
  echo -n "$x "
fi
done
```

---

* ?成立:不成立

![](https://i.imgur.com/cUqJyOj.jpg)

![](https://i.imgur.com/3uAyBds.jpg)

![](https://i.imgur.com/q30t8cH.jpg)

```
#!/bin/bash
sum=0
read -p "star" star
read -p "end" end
while (( star <= end ))
do
[ $((star%2)) == 1 ] && sum=$((sum+star)) && star=$((star+1)) || star=$((star+1))
done
echo $sum
```

![](https://i.imgur.com/DbPju4l.jpg)

```
#!/bin/bash
w=11
while (( w <= 15 ))
do
  echo "$w>>>>"
  x=3
  while (( x <= 5 ))
  do
    echo "$x>"
    y=6
    while (( y <= 8 ))
    do
      echo -n " $y:"
      z=9
      while (( z <= 13 ))
      do
        echo -n "$z "
        z=$((z+1))
      done
      echo
      y=$((y+1))
    done
    x=$((x+1))
  done
  w=$((w+1))
done
```
###### tags: `bash`
