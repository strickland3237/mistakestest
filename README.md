
<center><img src='/assets/images/yohelogo.png'/></center>
<center><a href='https://yohe-tw.github.io/'>web 網站連結</a></center>
# 教學 
[連結](https://medium.com/@starshunter/%E7%94%A8-jekyll-%E5%92%8C-github-page-%E4%BE%86%E6%9E%B6%E8%A8%AD%E9%9D%9C%E6%85%8B-markdown-%E9%83%A8%E8%90%BD%E6%A0%BC-fcaa288d4dd7)
some issue when execute `bundle exec jekyll serve` after add Minimal Mistakes theme:
1. `GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.`: solved by adding `github: [metadata]` to `_config.yml`
2. `gem 'wdm', '>= 0.1.0'`

3. (the main error)
```
<internal:C:/Ruby32-x64/lib/ruby/3.2.0/rubygems/core_ext/kernel_require.rb>:38:in `require': cannot load such file -- webrick (LoadError)
        from <internal:C:/Ruby32-x64/lib/ruby/3.2.0/rubygems/core_ext/kernel_require.rb>:38:in `require'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve/servlet.rb:3:in `<top (required)>'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve.rb:184:in `require_relative'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve.rb:184:in `setup'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve.rb:102:in `process'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve.rb:93:in `block in start'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve.rb:93:in `each'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve.rb:93:in `start'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/lib/jekyll/commands/serve.rb:75:in `block (2 levels) in init_with_program'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/mercenary-0.3.6/lib/mercenary/command.rb:220:in `block in execute'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/mercenary-0.3.6/lib/mercenary/command.rb:220:in `each'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/mercenary-0.3.6/lib/mercenary/command.rb:220:in `execute'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/mercenary-0.3.6/lib/mercenary/program.rb:42:in `go'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/mercenary-0.3.6/lib/mercenary.rb:19:in `program'
        from C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/jekyll-3.9.5/exe/jekyll:15:in `<top (required)>'
        from C:/Ruby32-x64/bin/jekyll:25:in `load'
        from C:/Ruby32-x64/bin/jekyll:25:in `<main>'
```
solve by add `bundle add webrick` [link](https://github.com/jekyll/jekyll/issues/8523)

https://github.com/benbalter/wordpress-to-jekyll-exporter/issues/37
