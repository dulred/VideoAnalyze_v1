<!--
 * @Author: dulred dulred@qq.com
 * @Date: 2024-08-03 12:20:14
 * @LastEditors: dulred dulred@qq.com
 * @LastEditTime: 2024-08-03 13:06:02
 * @FilePath: \Admin\README.md
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
#Admin 视频行为分析系统v1 后台管理

#### 环境
| 程序         | 版本      |
| ---------- | ------- |
| python     | 3.7+    |
| 依赖库      | requirements.txt |

### 安装依赖库
~~~

# 创建虚拟环境
python -m venv venv

# 切换到虚拟环境
venv\Scripts\activate

# 更新虚拟环境的pip版本
python -m pip install --upgrade pip -i https://pypi.tuna.tsinghua.edu.cn/simple

# 在虚拟环境中安装依赖库
python -m pip install -r requirements.txt -i http://mirrors.aliyun.com/pypi/simple --trusted-host mirrors.aliyun.com
~~~

### 启动

~~~
//启动后台管理服务
python manage.py runserver 0.0.0.0:9001

//默认用户
用户名：admin 密码：admin888

~~~


### 国内一些pip源
阿里云 http://mirrors.aliyun.com/pypi/simple/
中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/ 
豆瓣(douban) http://pypi.douban.com/simple/ 
清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
中国科学技术大学 http://pypi.mirrors.ustc.edu.cn/simple/


### 出现问题

WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, stonnection broken 
by 'ProxyError('Cannot connect to proxy.', timeout('_ssl.c:operation timed out'))': /simple/pylint/

出现该错误信息是由于pip源链接证书验证失败，将pip源调整为国内的源就能够了，好比要下载pylinturl

python -m pip install pylint -i http://mirrors.aliyun.com/pypi/simple --trusted-host mirrors.aliyun.com




若是想要永久修改pip源，可按照以下操做：3d


找到系统盘下C:\C:\Users\用户名\AppData\Roamingblog

查看在Roaming文件夹下有没有一个pip文件夹，若是没有建立一个

进入pip文件夹，建立一个pip.ini文件；

使用记事本的方式打开pip.ini文件，写入：

[global]
index-url = http://mirrors.aliyun.com/pypi/simple  # 指定下载源
trusted-host = mirrors.aliyun.com             # 指定域名

Linux:

# 找到~/.pip/pip.conf,若是不存在就建立,加入内容以下：
[global]
timeout = 10 # 设置超时，单位s
index-url =  http://mirrors.aliyun.com/pypi/simple/   # 指定优先下载源
extra-index-url= http://pypi.douban.com/simple/   # 第二下载源
[install]
trusted-host=
    mirrors.aliyun.com
    pypi.douban.com