# 搜索

### 调用地址
- 认证方式：[Cookie（SESSDATA）](#cookie);

- 鉴权方式：[Cookie（SESSDATA）](#cookie)方式时需要验证[Referer](#Referer)为 .bilibili.com域名下

> https://api.bilibili.com/x/web-interface/search/type

*请求方式：GET*

### 参数
|字段|必选|类型|说明|
|---|---|---|---|
|keyword|true|string|搜索的关键字，必须做URLencoding。|
|search_type|true|string|必填，可以填video 反正不知是啥|
|page| false |int| 搜索结果分页选择 默认为第1页|
|order|false|string|排序方式|


### 排序方式
|字段|说明|
|----|----|
|default|综合排序|
|pubdate|按发布日期倒序排序|
|senddate|按修改日期倒序排序|
|id|按投稿ID倒序排序|
|ranklevel|按相关度排序|
|click|按点击从高至低排序|
|scores|按评论数从高至低排序|
|damku|按弹幕数从高至低排序|
|stow|按收藏数从高至低排序|

### Referer
|字段|必选|类型|说明|
|----|----|----|----|
|Referer|true|string|来源地址，必填 可填写https://search.bilibili.com|
不填则403

### 返回
|返回值字段|字段类型|字段说明|
|---------|-------|--------|
|type|string|mylist 我的列表 video 视频 special 专题|
|lid|int|我的列表编号 当type为mylist时才会出现|
|aid|int|视频编号 当type为video时才会出现|
|bvid|string|BV号   |
|spid|int|专题编号 当type为special时才会出现|
|author|string|视频作者|
|mid|int|视频作者ID|
|play|int|播放次数|
|review|int|评论数|
|video_review|int|弹幕数|
|favorites|int|收藏数|
|title|string|视频/mylist/专题标题|
|description|string|视频/mylist/专题描述|
|tag|string|视频/mylist/专题关键字|
|pic|string|封面图片地址|
|pubdate|int|发布日期|

### 错误代码
|代码|说明|
|----|-------|
|-501|系统错误|
|-502|搜索正在进行中|

### 例子

xdown：
```
https://api.bilibili.com/x/web-interface/search/type?&page=1&order=click&keyword=MMD&search_type=video --header "Referer:https://search.bilibili.com" 
```
懒得写代码，能知道意思就行 要是这都看不懂就没必要写爬虫了