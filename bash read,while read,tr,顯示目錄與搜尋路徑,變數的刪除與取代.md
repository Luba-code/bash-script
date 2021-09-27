# bash read,while read,tr,顯示目錄與搜尋路徑,變數的刪除與取代

---

* read

![](https://i.imgur.com/VmXXeBb.jpg)

![](https://i.imgur.com/rmpUR98.jpg)

![](https://i.imgur.com/bIFcvqJ.jpg)

![](https://i.imgur.com/HfkqeDN.jpg)

![](https://i.imgur.com/JhtTNHh.jpg)

---

* while read

![](https://i.imgur.com/X4ySRUk.jpg)

![](https://i.imgur.com/XMFHOMj.jpg)

![](https://i.imgur.com/eUGZTSN.jpg)

![](https://i.imgur.com/UW06adk.jpg)

![](https://i.imgur.com/1at57OW.jpg)

![](https://i.imgur.com/2HEarty.jpg)

![](https://i.imgur.com/WfOyVEp.jpg)

![](https://i.imgur.com/sP3Byyb.jpg)

```
IF you
Do not love me
I will go
Jumpping to the sea
Because
I love you
So much
```

```
#!/bin/bash
if [ $# == 0 ];then
  echo "沒參數(檔名)"; exit
else
  if [ -f $1 ];then
  while read var
  do
    echo "$var"
    sleep 1
  done < txt01
  else
    echo "沒有此文件"
  fi
fi
```

![](https://i.imgur.com/1FcyEaM.jpg)

---

* tr

![](https://i.imgur.com/ROQTV1C.jpg)

![](https://i.imgur.com/H3xnwtH.jpg)

![](https://i.imgur.com/Sb6lGMr.jpg)

![](https://i.imgur.com/QISpJPh.jpg)

![](https://i.imgur.com/uk5paa3.jpg)

---

* 顯示目錄與搜尋路徑

![](https://i.imgur.com/BrM0lGz.jpg)

![](https://i.imgur.com/qUh7B5Q.jpg)

![](https://i.imgur.com/idE03xz.jpg)

![](https://i.imgur.com/7jKHDF7.jpg)

重開機後，路徑變會消失，如果永久存在路徑得去家目錄的~/.bash profile裡面增加

---

* 變數的刪除與取代

![](https://i.imgur.com/bBYIOeX.jpg)

![](https://i.imgur.com/qcprzZ7.jpg)

![](https://i.imgur.com/Czo2goD.jpg)

![](https://i.imgur.com/BRNSfbo.jpg)

![](https://i.imgur.com/42Wtj64.jpg)

![](https://i.imgur.com/Csj5AUV.jpg)

![](https://i.imgur.com/QNeGrni.jpg)

![](https://i.imgur.com/ms7DFTJ.jpg)

![](https://i.imgur.com/r5jcnHE.jpg)

```
#!/bin/bash
txt="1;2;33;44;55;66;77;"
for  ((no=1;no<=7;no=no+1))
do
txt=${txt#*;}
echo $txt
done
```

###### tags: `bash`
