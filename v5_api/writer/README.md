# 发表文章
由于编辑有自动估存功能，所人从编辑器中发表文章分三个过程
1.js检测用户第一次输入有3秒停顿，生成文章id：aid,并把文章insert到db,同时改变url地址为/writer/874236928/edit,这个过程执行的是insert操作，POST方法调用接口:write/

2.js检测用户第N次输入有3秒停顿,更新文章，这个过程执行的是update操作,PUT方法调用接口:write/874236928

3.js检测用户按下发表文章按钮，更新文章，这个过程执行的是update操作,PUT方法调用接口:write/874236928/publish