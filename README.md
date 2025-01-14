# CSDN 爬虫

> 主要功能：爬取 csdn 博客指定用户的所有博文并转换为 markdown 格式保存到本地。

## 下载脚本
```shell
git clone https://github.com/ds19991999/csdn-spider.git
cd csdn-spider
python3 -m pip install -r requirements.txt

# 测试
python3 test.py # 需要先配置登录 cookie
```

## 获取 cookie

登录 `csdn` 账号，进入：https://blog.csdn.net ，按 `F12` 调试网页，复制所有的 `Request Headers`，保存到`cookie.txt`文件中

![1571482112632](assets/1571482112632.png)


## 爬取用户全部博文
```python
import csdn
csdn.spider("ds19991999", "cookie.txt")
# 参数 usernames: str, cookie_path:str, folder_name: str = "blog"
```

* 示例爬取博文效果： [ds19991999 的博文](https://github.com/ds19991999/csdn-spider/tree/master/blog/ds19991999)

## 注意

1、要用python3，不然会报错： def get_headers(cookie_path:str):     SyntaxError: invalid syntax

2、在一级目录下新建cookies.txt，method不要有:，以及其它key值不要有:，不然会报错：ValueError: Invalid header name b

3、url地址也要正确，不然会报错：requests.exceptions.ConnectionError: HTTPSConnectionPool(host='', port=443)

## LICENSE

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a>



`PS`：随意写的爬虫脚本，佛系更新。
