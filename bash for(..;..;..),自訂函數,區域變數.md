# bash for(..;..;..),自訂函數,區域變數

---

* for(..;..;..)

![](https://i.imgur.com/j2hQtmY.jpg)

![](https://i.imgur.com/jKxCRZ7.jpg)

```
#!/bin/bash
sum=0
[ $# -le 0 ] && echo "要給一個值"
for (( no=1;no<=$1;no=no+1 ))
do
  sum=$((sum+no))
done
echo $sum
```
![](https://i.imgur.com/vFxt9xX.jpg)

```
#!/bin/bash
for ((w=11;w<=15;w=w+1))
do
echo "$w>>>>"
  for  ((x=3;x<=5;x=x+1))
  do
  echo " $x>"
    for  ((y=6;y<=8;y=y+1))
    do
      echo -n " $y:"
      for ((z=9;z<=13;z=z+1))
        do
          echo -n "$z "
        done
        echo
    done
  done
done
```

---

* 自訂函數

![](https://i.imgur.com/9QGQFSe.jpg)

![](https://i.imgur.com/YRrVKGz.jpg)

![](https://i.imgur.com/mtX363q.jpg)

![](https://i.imgur.com/HY53R5O.jpg)

![](https://i.imgur.com/6xKPZL0.jpg)

![](https://i.imgur.com/qe70ATo.jpg)

![](https://i.imgur.com/i14jCLg.jpg)

```
#!/bin/bash
hd()
{
hdinfo=$(df -h | grep /dev/sda)
}
mem()
{
meminfo=$(free -h | grep "Mem")
}
cpu()
{
cpuinfo=$(grep "model name" /proc/cpuinfo)
}
hd
mem
cpu
echo $hdinfo
echo $meminfo
echo $cpuinfo
```

![](https://i.imgur.com/mXjTIhm.jpg)

```
#!/bin/bash
add()
{
add=$(($1+$2))
result=$add
}
sub()
{
sub=$(($1-$2))
result=$sub
}
multi()
{
multi=$(($1*$2))
result=$add
}
div()
{
div=$(($1/$2))
result=$div
}
add 10 20
echo $result
sub 10 20
echo $result
multi 10 20
echo $result
div 10 20
echo $result
```

---

* 區域變數

![](https://i.imgur.com/uLOhyLM.jpg)

![](https://i.imgur.com/m52pTwV.jpg)

![](https://i.imgur.com/9pvYtgM.jpg)

![](https://i.imgur.com/wZHlpY3.jpg)

![](https://i.imgur.com/WaSlJ7p.jpg)

![](https://i.imgur.com/1Lb3WC3.jpg)

![](https://i.imgur.com/vZA3toj.jpg)

![](https://i.imgur.com/l7Gwmx9.jpg)

![](https://i.imgur.com/SnhIvud.jpg)

![](https://i.imgur.com/1En6v3W.jpg)

使用者清單 userlist.conf

```
export USER1=luba
export USER2=luba2
export USER3=luba3
```
```
#!/bin/bash
source userlist.conf
for x in $USER1 $USER2 $USER3
do
sudo useradd -m -s /bin/bash $x &>/dev/null
done
```


###### tags: `bash`
