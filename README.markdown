cbhl.github.com
===============

Jekyll
------

    sudo apt-get install ruby1.8-dev
    gem install jekyll
    sudo apt-get install blahtexml texlive-binaries python-pygments

See [mojombo/jekyll/wiki/Install][https://github.com/mojombo/jekyll/wiki/Install] for more details.

Migration
---------

Maruku doesn't like SyntaxHighlighter syntax, i.e. "[bash]". It will need to be replaced with Jekyll-style highlighting tags:

    $ sed -in 's/\[bash]/\
    {% highlight bash %}\
    /g' *.markdown
    $ sed -in 's/\[\/bash]/\
    {% endhighlight %}\
    /g' *.markdown
    $ sed -in 's/\[text]/\
    {% highlight text %}\
    /g' *.markdown
    $ sed -in 's/\[\/text]/\
    {% endhighlight %}\
    /g' *.markdown
    $ sed -in 's/\[shell]/\
    {% highlight shell %}\
    /g' *.markdown
    $ sed -in 's/\[\/shell]/\
    {% endhighlight %}\
    /g' *.markdown

Also watch out for \[code lang="..."] tags.

Further Reading
---------------
* [GitHub Pages][]
* [Jekyll Wiki][]

[GitHub Pages]: <http://pages.github.com/>                "GitHub Pages"
[Jekyll Wiki]:  <https://github.com/mojombo/jekyll/wiki>  "Jekyll Wiki"

