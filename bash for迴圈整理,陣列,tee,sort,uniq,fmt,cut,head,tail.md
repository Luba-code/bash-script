# bash for迴圈整理,陣列,tee,sort,uniq,fmt,cut,head,tail

---

![](https://i.imgur.com/AmfssVr.jpg)

![](https://i.imgur.com/xrmFvrF.jpg)

![](https://i.imgur.com/SIyafbB.jpg)

![](https://i.imgur.com/wXzCD86.jpg)

---

* 陣列

![](https://i.imgur.com/mj55S4t.jpg)

![](https://i.imgur.com/jGnwsCS.jpg)

![](https://i.imgur.com/65bll0F.jpg)

![](https://i.imgur.com/4LaYBUZ.jpg)

![](https://i.imgur.com/e5bbbeq.jpg)

![](https://i.imgur.com/xpZrgpZ.jpg)

![](https://i.imgur.com/p06rlgx.jpg)

![](https://i.imgur.com/PxhkIrs.jpg)

```
#!/bin/bash
for ((no=0;no<=20;no++))
do
array[no]=$no
echo "array[$no]"=${array[no]}
done
```

---

* tee

![](https://i.imgur.com/cfQXcV1.jpg)

![](https://i.imgur.com/1CbaCXg.jpg)

![](https://i.imgur.com/NTurhqe.jpg)

![](https://i.imgur.com/SS9uIWe.jpg)

# sudo tee 很重要，許多需要根目錄的檔案都需要用到

---

* sort

![](https://i.imgur.com/p5IawB9.jpg)

![](https://i.imgur.com/DB1Rt7V.jpg)

![](https://i.imgur.com/NwgRPBS.jpg)

---

* uniq

![](https://i.imgur.com/VB9aPKg.jpg)

![](https://i.imgur.com/j3BygwQ.jpg)

---

* cut

![](https://i.imgur.com/810w80Z.jpg)

![](https://i.imgur.com/Osg55qJ.jpg)

![](https://i.imgur.com/hCecDc2.jpg)

---

* fmt

![](https://i.imgur.com/PQfNl3s.jpg)

---

* head

![](https://i.imgur.com/eLY6N7Q.jpg)

---

* tail

![](https://i.imgur.com/ujx0rEf.jpg)


###### tags: `bash`
