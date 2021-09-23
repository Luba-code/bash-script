# bash case,grep,通配字元

---

![](https://i.imgur.com/3TYQ5GW.jpg)

![](https://i.imgur.com/Ikz5yjO.jpg)

![](https://i.imgur.com/rkXWhSR.jpg)

![](https://i.imgur.com/bUQn4FU.jpg)

![](https://i.imgur.com/yLLBSvm.jpg)

```
#!/bin/bash
read -p "你喜歡川普嗎?" ans
case $ans in
y|Y)
  echo "川普粉絲多一人"
  ;;
n|N)
  echo "討厭川普又多一人"
  ;;
esac
```
![](https://i.imgur.com/OKX3ZSL.jpg)

加入while true 讓迴圈一值跑

![](https://i.imgur.com/YXNt6uf.jpg)

![](https://i.imgur.com/N9diLpw.jpg)

```
#!/bin/bash
while true
do
clear
read -p "你喜歡川普嗎?" ans
case $ans in
y|Y)
  echo "川普粉絲多一人"
  break
  ;;
n|N)
  echo "討厭川普又多一人"
  break
  ;;
*)
  continue
  ;;
esac
done
```

![](https://i.imgur.com/U4MfNl0.jpg)

```
#!/bin/bash
while true
do
clear
ehco -e "
1.目前使用者
2.家目錄
3.主機名稱"
read -p ans
case $ans in
1)
  whoami
  break
  ;;
2)
  echo "$HOME"
  break
  ;;
3)
  hostname
  break
  ;;
esac
done
```

---

* grep

![](https://i.imgur.com/L8a1xNV.jpg)

![](https://i.imgur.com/2xV937A.jpg)

![](https://i.imgur.com/wNLgPA1.jpg)

![](https://i.imgur.com/F2orImS.jpg)

---

* 通配字元

![](https://i.imgur.com/BUWDqyn.jpg)

![](https://i.imgur.com/VdM6Wom.jpg)


###### tags: `bash`
