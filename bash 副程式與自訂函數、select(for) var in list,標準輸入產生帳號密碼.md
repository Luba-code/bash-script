#  bash 副程式與自訂函數,(select)for var in list，標準輸入產生帳號密碼

---

![](https://i.imgur.com/NhNxz5X.jpg)

```
#!/bin/bash
cpuinfo=$(cat /proc/cpuinfo|grep "model name")
echo  $cpuinfo
read -p "按任意鍵繼續“
```
```
#!/bin/bash
memoryinfo=$(free -mh |grep "Mem:")
echo  $memoryinfo
read -p "按任意鍵繼續"
```
```
#!/bin/bash
hdinfo=$( df -h |grep "dev/sda2")
echo  $hdinfo
read -p "按任意鍵繼續"
```

```
#!/bin/bash
while true
do
clear
echo "
  1.cpu
  2.memory
  3.HD
  4.exit"
read -p "choice?" cho
case  $cho in
1)
./cpu.sh
;;
2)
./memory.sh
;;
3)
./hd.sh
;;
*)
break
;;
esac
done
```

---

* select in list

![](https://i.imgur.com/NIBE1B0.jpg)

![](https://i.imgur.com/Lu9tehi.jpg)

```
#!/bin/bash
math()
{
add=$((ans1+ans2))
sub=$((ans1-ans2))
multi=$((ans1*ans2))
div=$((ans1/ans2))
}
echo "
  請選擇哪種運算，輸入1~4"
select var in "加" "減" "乘" "除"
do
echo "您輸入的內容為?" $REPLY
read -p "第一個數字為?" ans1
read -p "第二個數字為?" ans2
case  $REPLY in
1)
math $ans1 $ans2
echo "兩數相加結果為$add"
break
;;
2)
math $ans1 $ans2
echo "兩數相減結果為$sub"
break
;;
3)
math $ans1 $ans2
echo "兩數相乘結果為$multi"
break
;;
4)
math $ans1 $ans2
echo "兩數相除結果為$div"
break
;;
*)
break
;;
esac
done
```

---

* for var in list

![](https://i.imgur.com/4lWakPP.jpg)

```
#!/bin/bash
math()
{
add=$(($1+$2))
sub=$(($1-$2))
multi=$(($1*$2))
div=$(($1/$2))
}
for var in "加" "減" "乘" "除"
do
case  $3 in
1)
math $1 $2
echo "兩數相加結果為$add"
break
;;
2)
math $1 $2
echo "兩數相減結果為$sub"
break
;;
3)
math $1 $2
echo "兩數相乘結果為$multi"
break
;;
4)
math $1 $2
echo "兩數相除結果為$div"
break
;;
*)
```

---

* 標準輸入產生帳號密碼

![](https://i.imgur.com/V9h8xFR.jpg)

![](https://i.imgur.com/7PZll6k.jpg)

![](https://i.imgur.com/nNG5MFN.jpg)

![](https://i.imgur.com/Dc183WR.jpg)

![](https://i.imgur.com/Qhda5rg.jpg)

![](https://i.imgur.com/cDxPeNQ.jpg)

![](https://i.imgur.com/3pLP8fb.jpg)

![](https://i.imgur.com/pPUeGJU.jpg)

![](https://i.imgur.com/OIOSeXY.jpg)

```
#!/bin/bash
select var in "產生一個帳號" "產生一系列帳號(多少到多少)"
do
echo $REPLY
case $REPLY in
1)
read -p "帳號名稱" ans
grep $ans /etc/passwd >/dev/null
if [ $? == 0 ];then
  echo "帳號已有不建立"
else
  sudo useradd -m -s /bin/bash ${ans}
  echo "帳號幫您建立"
  echo "$ans:$ans" >> name1.txt
fi
break
;;
2)
read -p "帳號名稱" ans
read -p "開頭" ans1
read -p "結尾" ans2
for (( no=ans1;no<=ans2;no=no+1))
do
grep $ans$no /etc/passwd >/dev/null
[ $? == 0 ] && echo "帳號已有不建立" || sudo useradd -m -s /bin/bash $ans$no &&  echo "帳號幫您建立" && echo "$ans$no:$ans$no" >> name2.txt
done
break
;;
esac
done
```

![](https://i.imgur.com/QD9TJkX.jpg)

```
#!/bin/bash
addaccount()
{
read -p "帳號名稱" ans
read -p "開頭" ans1
read -p "結尾" ans2
for (( no=ans1;no<=ans2;no=no+1))
do
grep $ans$no /etc/passwd >/dev/null
[ $? == 0 ] && echo "帳號已有不建立" || sudo useradd -m -s /bin/bash $ans$no &&  echo "帳號幫您建立" && echo "$ans$no:$ans$no" >> name2.txt
done
}
delaccount()
{
read -p "帳號名稱" ans
read -p "開頭" ans1
read -p "結尾" ans2
for (( no=ans1;no<=ans2;no=no+1))
do
sudo userdel -r $ans$no
done
}
chpasswd()
{
sudo chpasswd < name2.txt
}
```

###### tags: `bash`
