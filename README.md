## Train-12306

[![Build Status](https://travis-ci.org/ecmadao/Spider-12306.svg?branch=master)](https://travis-ci.org/ecmadao/Train-12306)

最初的灵感来自于[PROTREAM](https://protream.github.io/)的博客[用Python写一个命令行火车票查看器](https://protream.github.io/post/build-a-command-line-train-tickets-query-tool-with-python/)，感谢他提供的车站名称转换链接，有了那个以后我就屁颠屁颠跑去写着玩了。


但与之不同的是,使用了click库而不是docopt库, 我个人觉得这样的话输入会更加人性化一些~

### 开发环境

python 3.5

### 第三方依赖

[prettytable](https://code.google.com/archive/p/prettytable/wikis/Tutorial.wiki)

[click](http://click.pocoo.org/6)

打个广告，[python教程及笔记](https://github.com/ecmadao/Coding-Guide/tree/master/Notes/Python)戳这边，prettytable使用方法可见[Python语言及其应用-3(数据处理)](https://github.com/ecmadao/Coding-Guide/blob/master/Notes/Python/Python%E8%AF%AD%E8%A8%80%E5%8F%8A%E5%85%B6%E5%BA%94%E7%94%A8-3%EF%BC%88%E6%95%B0%E6%8D%AE%E5%A4%84%E7%90%86%EF%BC%89.md)

### USAGE

```bash
$ train
$ train --train-type=[g | d | t | k | z | None] # 查询不同类型的火车
```

**local usage**

不安装项目的情况下

```bash
# 下载项目文件，cd到项目根目录
$ python3 run.py
```

### Help

```python
"""
Usage:
    $ trian
    $ trian --train-type=[g | d | t | k | z| None]

Options:
    --help       查看帮助
    --start      起始站
    --end        目的地
    --train-date 出发时间
    --train-type 车型
        g  高铁
        d  动车
        t  特快
        k  快速
        z  直达

Examples:
    $ train
    $ train --train-type=g
"""
```

### Example

```bash
$ train

# output
+------+------+----------+-------+--------+--------+--------+--------+------+------+------+------+------+
| 车次 | 站点 | 起止时间 |  历时 | 商务座 | 特等座 | 一等座 | 二等座 | 软卧 | 硬卧 | 软座 | 硬座 | 无座 |
+------+------+----------+-------+--------+--------+--------+--------+------+------+------+------+------+
| K904 | 厦门 |  06:59   | 21:55 |   --   |   --   |   --   |   --   |  8   |  有  |  --  |  有  |  有  |
|      | 太原 |  04:54   |       |        |        |        |        |      |      |      |      |      |
+------+------+----------+-------+--------+--------+--------+--------+------+------+------+------+------+
```

![spider_12306 usage example](./example.png)

### TODO

- [ ] use selenium instead of webbrowser
- [x] ~~refactor~~
- [x] ~~use click instead of docopt~~
- [ ] more UnitTest