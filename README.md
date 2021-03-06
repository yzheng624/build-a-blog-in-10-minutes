# 10 分钟、20 行代码搭建你的个人 Blog

Python 大神柳开闫教你用 Django！

## 什么是 Python、Django？

### Why Python?
> Beautiful is better than ugly.  
> Explicit is better than implicit.  
> Simple is better than complex.

	import this

Simple, funny, powerful.

### Why Django?

void 大神：

> 用 Django 好几年了，月月都舒服。

## 1. [1 min] 准备环境

安装 Python、Django。

### Linux and OS X
Python 已经默认安装，只需要先安装 pip（是什么？）：

	curl https://raw.github.com/pypa/pip/master/contrib/get-pip.py | python

然后安装 Django：

	pip install Django

以上。好简单！

### Windows
下载 Python 并安装（注意要下载 2.x 的版本）：

	http://python.org/getit/

将 python.exe 加入环境变量 path。

然后下载 Django 并解压：

	https://www.djangoproject.com/download/

最后在相应目录输入并运行：

	python setup.py install

## 2. [2 min] 基础设施

### 创建 Project 和 App

	django-admin startproject yourname
	cd yourname
	django-admin startapp blog

### 设置数据库

在 settings.py 文件中将 DATABASES 设置为如下内容：

	DATABASES = {
	    'default': {
	        'ENGINE': 'django.db.backends.sqlite3',
	        'NAME': 'blog/db/database.db',
	    }
	}

### 启用 Admin 并将 Blog 加入已安装应用

	INSTALLED_APPS = (
	    ...
	    'django.contrib.admin',
	    'yourname.blog',
	)

### 运行服务器

	python manage.py runserver

## 3. [3 min] Model · 如何储存你的文章

### MVC 简介

### 关于 Model：文章都有什么属性？
* 标题
* 时间
* 内容
* ...

### 同步并建立相应数据库

	python manage.py syncdb

### 将相应 Model 注册入 Admin 中

	admin.site.register(YourModel)


## 4. [2 min] Controller · 数据库和页面间的桥梁
Controller 用来处理 Model 中的数据，传递给 View。

### URL - 路径到函数的绑定
Why need this?

例：1989年的文章列表

* Good URL: ``http://yzheng.me/1989/``
* Bad URL: ``http://yzheng.me/article_list.php?year=1989``

### 要传递给 View 的数据？

## 5. [2 min] View · 页面
View 是网站的前端部分，从 Controller 获得数据，由很多模版组成。

模版就是常规的 HTML 文件。

### 输出
	{{ variables }}
### 迭代
	{% for ele in list %}
		do something w/ ele ...
	{% endfor %}

## http://localhost:8000

## Done! What’s More?
* Category, tag?
* Comment?
* Beautiful template?
* ...
* With group, have a try!

## Further Readings
* Django 文档: [https://docs.djangoproject.com/](https://docs.djangoproject.com/)
* Django Book: [http://djangobook.py3k.cn/2.0/](http://djangobook.py3k.cn/2.0/)
* The Python Tutorial: [http://docs.python.org/tutorial/](http://docs.python.org/tutorial/)
