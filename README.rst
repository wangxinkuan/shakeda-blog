`Pelican <http://docs.getpelican.com/en/stable/>`_ 模板: shakeda-blog
#####################################################################


* 利用 Pelican-quickstart  生成项目

* 在 pelicanconf.py中 扩充jinja的过滤器，添加::

    from bs4 import BeautifulSoup

    def prettify(string):
        soup = BeautifulSoup(string, "lxml")
        return soup.prettify()

    JINJA_FILTERS = {'prettify': prettify}

* 在 pelican.conf 中将 THEME 变量设置为本模板路径，如::
    
    THEME = '/var/shakeda-blog'

* 编辑文档 fab build 并启动服务器 fab serve 前往 localhost:8000 查看