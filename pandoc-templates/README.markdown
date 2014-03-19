This is a fork of the default
[pandoc-templates](http://github.com/jgm/pandoc-templates) for
[pandoc](http://github.com/jgm/pandoc).  It provides the following additional
templates:

-  default.mla-paper:  a latex template that provides a default MLA-formatted
   paper template.  It uses the variables `authorfirst`, `authorlast`,
   `professorlast`, and `classname` to determine components of the MLA output.
   Requires the
   [mla-paper](http://www.ctan.org/tex-archive/macros/latex/contrib/mla-paper)
   package.

-  default.latex-hw: a latex template based on the article class with more
   minimal title output and smaller margins, suitable for homework exercises.

-  for support chinese font, I have add this code to default.latex file
	\usepackage{xeCJK} % 分開設置中英文字型
	\setCJKmainfont{WenQuanYi Zen Hei Mono} % 設定中文字型
   
