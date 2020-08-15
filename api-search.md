# 搜索

### 调用地址

https://api.bilibili.com/x/web-interface/search/type


### 参数

|字段| 必选|类型|说明|
|----| ----|----| ----|
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

### 必要 Referer 参数

Referer 参数可填写https://search.bilibili.com

不填则403



### 例子

xdown：

```
https://api.bilibili.com/x/web-interface/search/type?&page=1&order=click&keyword=MMD&search_type=video --header "Referer:https://search.bilibili.com" 
```
