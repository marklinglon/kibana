# kibana 要与es版本一致

# 不指定字段搜索
1. 不指定字段搜索为全文搜索，匹配到的结果是完整的value
2. 不带引号的搜索，搜索的字符串可以是完整的value,可以是正则表达式，还也可以是通配符，但搜索的内容不能是时间戳，也不能是key
3. 带引号的搜索,搜索内容必须是完整的value
4. 通配符和正则搜索都不能带引号
例:
log: gamesvr
正确的搜索语句：
"gamesvr"
gamesvr
/gamesvr/ 
正则
/gamesv.*/  
通配符
gamesv?
gamesv*
模糊匹配
games~*

错误搜索：
"gamesv*"
"gamesv?"
"game.*"
/game*/
"game~*"


# 指定字段搜索字符串
1. 匹配到的结果是完整的value
2. 通配符和正则搜索都不能带引号
例子：
log: INFO
log: INFO this is a test row
搜索语句:
log: INFO 只能匹配到第一行
正则
log: /INFO.*/ 可以匹配到两行
log: /I.*/ 可以匹配到两行
通配符
log: INF~ 只能匹配到第一行
log: IN~* 可以匹配到两行
log: INF?
