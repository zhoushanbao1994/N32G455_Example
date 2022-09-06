---
typora-root-url: ./
---







## 一、新建一个文件夹

​	用于存放工程文件

## 二、新建工程

### 1. 新建Prj

​	"Project"->"New uVision Project.."，然后选择保存位置为刚才创建的文件夹，设置工程名字为"N32G455.uvproj"。

### 2. 选择芯片型号

​	选择"N32G455REL7"，点击OK。

![image-20220906222146592](./PNG/image-20220906222146592.png)

### 3. 选择外设

​	直接取消（不用这种方式）

<img src="./PNG/image-20220906222929254.png" alt="image-20220906222929254" style="zoom:80%;" />

### 4. 空工程创建完毕

![image-20220906223206393](./PNG/image-20220906223206393.png)

![image-20220906223358384](./PNG/image-20220906223358384.png)



## 三、拷贝库文件

将“N32G455xx_V3.0.0\6-软件开发套件(Software Development Kit)\Nationstech.N32G45x_Library.2.1.0”路径下的“firmware文件夹”拷贝至上面新建的文件内（可以考虑将文件夹内所有文件改为只读文件，防止误修改）

![image-20220906224037724](./PNG/image-20220906224037724.png)

创建“User文件夹”，在文件夹内创建“main.c”

![image-20220906225838143](./PNG/image-20220906225838143.png)

![image-20220906225916769](./PNG/image-20220906225916769.png)

```c
// main.c 内容
#include <stdio.h>

int mian()
{
	return 0;    
}

```





## 四、添加库文件到工程

配置文件路径

![image-20220906224939453](./PNG/image-20220906224939453.png)

Group:STARTUP ->"\firmware\CMSIS\device\startup\startup_n32g45x.s"

![image-20220906230242843](./PNG/image-20220906230242843.png)

Group:CMSIS->"\firmware\CMSIS\device\system_n32g45x.c"

![image-20220906230329051](./PNG/image-20220906230329051.png)

Group:FWLIB->"\firmware\n32g45x_std_periph_driver\src\*.c"

![image-20220906230347398](./PNG/image-20220906230347398.png)

Group:USER->"mian.c"

![image-20220906230403555](./PNG/image-20220906230403555.png)

添加完成

![image-20220906230453072](./PNG/image-20220906230453072.png)





## 五、包含头文件路径

选择魔术棒

![image-20220906230548509](./PNG/image-20220906230548509.png)

"C/C++(AC6)"->"Include Paths":

- .\firmware\CMSIS\core
- .\firmware\CMSIS\device
- .\firmware\n32g45x_std_periph_driver\inc
- .\User

![image-20220906231307943](./PNG/image-20220906231307943.png)



## 六、其他

### 1. 添加宏定义

"C/C++(AC6)"->"Define"->"N32G45X, USE_STDPERIPH_DRIVER"

![image-20220906234347648](./PNG/image-20220906234347648.png)

### 2. 编译版本

![image-20220907000332617](./PNG/image-20220907000332617.png)

### 3. JLink（可选）

![image-20220906235332258](./PNG/image-20220906235332258.png)

### 4. 下载完成自动运行（可选）

![image-20220906235445879](./PNG/image-20220906235445879.png)

### 5. 生成HEX文件

![image-20220906235542517](./PNG/image-20220906235542517.png)



## 七、编译

![image-20220906235200270](./PNG/image-20220906235200270.png)
