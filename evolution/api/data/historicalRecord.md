# 状态和记录
作用
- 当用户发发表在点击与我交流,公共交流时，记录以下当前时间戳,在显示圈圈时，判断当前用户点开的时间之后有没有更新以下内容操作
    1.当用户推荐的文章被评论时；
    2.当用户的评论被点赞时；
    3.当用户的评论有新回复时；
    4.当用户之前发表过评论的文章有了新评论时；
    以上四种状态需要提示用户
，有过当前有上述信息，直接展现在页面上并且统计总个数


### 数据结构

```json
{
    //form_user 对to_user谁进行回复/对哪篇文章进行回复
    "_id" : ObjectId("547fd2ed2997cfa475516662"),
    "aid" :214548745,//当前文章id,
    "form_user" : 2
    "to_user"1
    "insert_time" ：1542324548
    "body" ：'',//展现的内容
    "type" : 1/2/3/4,内容4中情况
}
/*
{
    "_id" : ObjectId("547fd2ed2997cfa475516662"),
    "aid" : ,//当前文章的id
    "user_id" : 52,//文章作者
    "title" : "这是一片抓取的文章",//文章标题
    "insert_time":"xxx",//每次上述4中条件时都会进行数据库的录入
    "add_time" : 1417663213,//第一次发表时间 按此字段排序
    "publish_time" : 1417663213,//最后一次发表时间
    "update_time" : 0,//更新时间
    "type" : 1,//1、2、3、4  推荐的文章、赞你的文章、回复您的文章、当用户之前发表过评论的文章有了新评论时,5表示点评文章生成的记录
    "body" :'评论的主题内容'

}
*/


```