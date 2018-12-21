# jupyter command not found

原文：https://blog.csdn.net/songyu0120/article/details/78245092

在 EI captain 版本以及以上系统的 Mac 上使用 pip 安装 python 相关的包的时候, 由于 sip 机制 (System Integrity Protection) 的不允许命令行写入内容到系统目录, 因此一个比较”优雅”的解决方案就是针对当前用户安装包 

`pip install jupyter --user `


安装完成后, 直接在命令行里输入`jupyter notebook`可能会显示`jupyter command not found`, 这是由于 pip 安装完 jupyter 后并没有将其加入到 mac 当前运行环境中.

1. 先找到 jupyter 安装位置, 通常是在

	`/Users/yy(your_user_name)/Libraries/Python/2.7/bin`
2. 将下面命令添加到`~/.bash_profile`中
	`export export PATH=/Users/yy(your_user_name)/Library/Python/2.7/bin/:$PATH`

3. 执行 

	`source .bash_profile`

问题得到解决。