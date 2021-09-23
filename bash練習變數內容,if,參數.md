# bash script 變數內容、if、參數

---

* 變數內容

![](https://i.imgur.com/jNBbyzW.jpg)

![](https://i.imgur.com/A2ygn67.jpg)

![](https://i.imgur.com/eEJEl5C.jpg)

![](https://i.imgur.com/LMOLybH.jpg)

練習

![](https://i.imgur.com/SXc34gU.jpg)

![](https://i.imgur.com/GgSPDa9.jpg)

```
bigred@web-ubs2004:~$ pw="125dFgS4"
bigred@web-ubs2004:~$ pw1=${pw//[0-9]/}
bigred@web-ubs2004:~$ pw2=${pw1,,}
bigred@web-ubs2004:~$ echo $pw, $pw1, $pw2
125dFgS4, dFgS, dfgs
```
```
bigred@web-ubs2004:~$ pw="123asdQWE_@"
bigred@web-ubs2004:~$ pw1=${pw//[a-z]/}
bigred@web-ubs2004:~$ pw2=${pw//[!a-z]/}
bigred@web-ubs2004:~$ pw3=${pw//[A-Z]/}
bigred@web-ubs2004:~$ pw4=${pw//[!A-Z]/}
bigred@web-ubs2004:~$ pw5=${pw//[!A-Z0-9]/}
bigred@web-ubs2004:~$ pw6=${pw//[!A-Z0-9a-z]/}
bigred@web-ubs2004:~$ echo $pw, $pw1, $pw2, $pw3, $pw4, $pw5, $pw6
123asdQWE_@, 123QWE_@, asd, 123asd_@, QWE, 123QWE, 123asdQWE
```
---

* if-then,elif,read

![](https://i.imgur.com/6B1Bql6.jpg)

```
#!/bin/bash
clear
read -p "do you love me ?" ans
[ "${ans,,}" = "y" ] && echo "i love you too"
[ "${ans,,}" = "n" ] &&  echo "i hate you"
```

![](https://i.imgur.com/Ctmw0YT.png)

練習

![](https://i.imgur.com/BxTC5cq.jpg)

```
#!/bin/bash
read  -p "password?" ans
if [ ${ans,,} = "qwer" ]
then
  echo "pass"
else
  echo "not correct"
fi
```

![](https://i.imgur.com/o68nltP.jpg)

![](https://i.imgur.com/EA6x9UF.jpg)

>/dev/null 丟進黑洞，通常放一些冗長的訊息

![](https://i.imgur.com/FSL28nT.jpg)

由於輸出都正確，所以2是空值沒東西

![](https://i.imgur.com/jZI8bBb.jpg)

![](https://i.imgur.com/uTaWevf.jpg)

![](https://i.imgur.com/rXqhqlS.jpg)

![](https://i.imgur.com/8mlYkWn.jpg)

![](https://i.imgur.com/HUNb0S1.jpg)

```
#!/bin/bash
clear
read  -p  "no?"  ans
if  [ ${ans}  -le  60 ] ;then
echo  "no pass"
fi
```
![](https://i.imgur.com/MMjlErM.jpg)

![](https://i.imgur.com/Nd8NCvo.jpg)

```
#! /bin/bash
read  -p  "請使用者輸入分數?"  ans
if  [ ${ans}  -le  60 ] ;then
echo  " D grade "
elif   [ ${ans}  -le  80 ] ; then
echo  " C grade "
else
echo " B grade "
fi
```

---

* 參數

![](https://i.imgur.com/ANl9wIW.jpg)

![](https://i.imgur.com/elKfjeS.jpg)

```
#!/bin/bash
read  -p "password?" ans
if [ "$ans" = "$1" ]
then
  echo "pass"
else
  echo "not correct"
fi
```

###### tags: `bash`
