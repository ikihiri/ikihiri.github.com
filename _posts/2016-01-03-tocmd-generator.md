---
layout: post
date: 2016-01-03 03:00:00
category : github pages
tags : [github pages]
title : tocmd-generator
---
{% include JB/setup %}

# 概要
ドキュメント書くとき目次が無いと落ち着かない性格なので、github pagesで使えるものが無いか探してみた


# tocmd-generator

[tocmd-generator](https://github.com/dafi/tocmd-generator)

こんな感じで置いて
    |-- assets
        |-- css
            |-- toc.css
        |-- js
            |-- jquery.toc.js

postのlayout側で呼び出して
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
    <script src="{{site.github.url}}/assets/js/jquery.toc.js"></script>
    <link href="{{site.github.url}}/assets/css/toc.css" rel="stylesheet" media="all">
        
    ・・・略・・・
        
    <script type="text/javascript">
        $(function() {
            $('#main').toc({ // 探索範囲
                showAlways:true,
                renderIn:'#renderIn', // 目次を表示する場所
                contentsText:"目次"
            });
        });
    </script>

表示のHTML部分で目次を入れるためのタグと、探索範囲を指定するためにタグにidを仕込む
    <div id="renderIn"></div>  // tag自体を追加
    <div class="bd" id="main"> // id="main"を追加


とりあえず上記で表示までは出来る。  
デフォルトのcssだとあんまり自分の文章と合わないので、ちょっと変えた

- toggle（表示・非表示）いらないので無理矢理消した
     #toc .toctoggle, .toc .toctoggle {
     +    display: none;
          font-size: 94%;
      }

- alight centerやめた
     #toc #toctitle, .toc #toctitle, #toc .toctitle, .toc .toctitle {
     -    text-align: center;
     +    #text-align: center;
      }

とりあえずこれくらい。
