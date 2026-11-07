+++
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
author = ''
date = '{{ now.Format "2006-01-02" }}'
pages = 0
# 书目只进 Reading 列表，不生成独立页面
[build]
render = 'never'
+++
