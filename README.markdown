This is a simple Markdown resume template, LaTeX header, and pre-processing
script that can be used with [Pandoc](http://johnmacfarlane.net/pandoc/) to
create professional-looking PDF and HTML output.

Dependencies
------------

* Pandoc >= 1.9 (you can adjust the Makefile to use an earlier version -- the
  arguments format changed)
* Python 2.7
* A Tex installation with pdflatex and the Tex Gyre Pagella font, and some
  packages needed by pandoc.  On Ubuntu you can get this by installing
  `texlive`, `texlive-latex-extra`, and `tex-gyre`.

Be sure to run `git submodule update --init` to fetch the custom pandoc
template which the resume is based on.

* For fedora:

		yum -y install pandoc
		
		yum -y install texlive texlive-latex texlive-xetex
		yum -y install texlive-collection-latex
		yum -y install texlive-collection-latexrecommended
		yum -y install texlive-xetex-def
		yum -y install texlive-collection-xetex

Usage
-----

Simply run `make` to generate PDF and HTML versions of each .md file in the
directory.

In order to enable visually appealing display of contact information, the
Markdown is passed through a Python script that looks for contact details
beginning on the fourth line and moves them into a right-aligned, zero-height
box at the top of the document.  Lines with bullets(•) will be treated as
separate contact lines in the output.

By default, an image of your [Gravatar](http://www.gravatar.com) will be added
to the HTML resume.  This feature can be disabled by setting the environment
variable `GRAVATAR_OPTION=--no-gravatar`.

Problems
-----
* Not found specify font when run `make pdf`:  

		pandoc: Error producing PDF from TeX source.
		!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
		!
		! fontspec error: "font-not-found"
		! 
		! The font "WenQuanYi Zen Hei Mono" cannot be found.
		! 
		! See the fontspec documentation for further information.
		! 
		! For immediate help type H <return>.
		!............................................... 

		[root@localhost resume]# fc-list |grep "WenQuanYi"
		[root@localhost resume]# yum search "WenQuanYi Zen Hei Mono"
		[root@localhost resume]# yum install -y wqy-zenhei-fonts.noarch

* Install latex package on fedora 
	su -c 'yum install texlive-titlesec'
	su -c 'yum install texlive-titling'
	su -c 'yum install texlive-lastpage'
  
* pandoc support chinese, look [利用Pandoc将markdown文件转化为pdf](http://blog.sina.com.cn/s/blog_5ee56d450101dah2.html)

* On ubuntu
	sudo apt-get install texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended  
	sudo apt-get install tex-gyre  

Reference
------
+ [An elegant Markdown -> PDF/HTML resumé generator](https://github.com/mwhite/resume)
+ [How to install LaTeX and XeLaTeX in Fedora 19](http://mednis.info/wp/?p=63)
