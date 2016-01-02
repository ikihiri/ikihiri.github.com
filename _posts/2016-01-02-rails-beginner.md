---
layout: post
date: 2016-01-02 23:00:00
category : rails
tags : [rails, beginner]
title : rails projectを始める時に参考にするかもしれない何か
---
{% include JB/setup %}

# 概要
railsで何か作ろう！って思ったときに何入れていいか分からない人（俺）のためのメモ。  
主にテスト周りとか


# gemでいれちゃう

[suspenders](https://github.com/thoughtbot/suspenders): thoughtbot社が作成したgem

thoughtbot社でrails applicationを作成する時にbaseにしているらしい  
実際の会社で使われてるというだけで何か信頼感が増すような気がしてくる

githubのREADMEから引用（下記はv1.35.0のもの）

    It includes application gems like:
      Airbrake for exception notification
      Autoprefixer Rails for CSS vendor prefixes
      Bourbon for Sass mixins
      Bitters for scaffold application styles
      Delayed Job for background processing
      Flutie for page_title and body_class view helpers
      High Voltage for static pages
      jQuery Rails for jQuery
      Neat for semantic grids
      New Relic RPM for monitoring performance
      Normalize for resetting browser styles
      Postgres for access to the Postgres database
      Rack Canonical Host to ensure all requests are served from the same domain
      Rack Timeout to abort requests that are taking too long
      Recipient Interceptor to avoid accidentally sending emails to real people from staging
      Refills for “copy-paste” components and patterns based on Bourbon, Neat and Bitters
      Simple Form for form markup and style
      Title for storing titles in translations
      Puma to serve HTTP requests
    
    And development gems like:
      Dotenv for loading environment variables
      Pry Rails for interactively exploring objects
      ByeBug for interactively debugging behavior
      Bullet for help to kill N+1 queries and unused eager loading
      Bundler Audit for scanning the Gemfile for insecure dependencies based on published CVEs
      Spring for fast Rails actions via pre-loading
      Web Console for better debugging via in-browser IRB consoles.
      Quiet Assets for muting assets pipeline log messages
    
    And testing gems like:
      Capybara and Capybara Webkit for integration testing
      Factory Girl for test data
      Formulaic for integration testing HTML forms
      RSpec for unit testing
      RSpec Mocks for stubbing and spying
      Shoulda Matchers for common RSpec matchers
      Timecop for testing time

ByeBugやBullet、Springとか。あとはtest周りのgemはよく見かけるものかな  
自分はmysqlを普段使ってますが、最近のスタートアップ企業での流行はPostgresらしいので、  
新規だったらこのgem使ってみるのはアリなきがしますね


# （他人の作った）Application Template使う
他人のApplication Templateをどこかから取ってきてプロジェクト作成時に下記のように引数追加する感じですね

    rails new new_project_name -m 取ってきたtemplate.rb

[githubで人気のtemplate検索して](https://github.com/search?o=desc&q=rails+template&s=stars&source=c&type=Repositories)見つけるというのも一つの手ですが、  
正直、どれが良いかもわからない、、、といった初心者も多いのではないかなー、と。  
下記辺りがおすすめです。

- [RailsのApplication templateを使って開発の初速をあげよう！](http://qiita.com/tachiba/items/26b2e9dc271bd8e6907d)
- [Rails 4.2 + Bootstrap の Application Template 1コマンドでモダンRailsが！](http://morizyun.github.io/blog/rails4-application-templates-heroku/)

# 個人的な感想というかまとめ

- とりあえず上記辺りに含まれているgemを参考にする
- 社内とかにノウハウが溜まってきたら、Application Templateを作ってみる

的な方向でやってくのがいいのかなーと思いました

