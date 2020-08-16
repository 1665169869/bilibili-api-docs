# 其他接口

### 搜索框默认内容
- 认证方式：无

- 鉴权方式：无

> https://api.bilibili.com/x/web-interface/search/default

*请求方式：GET*

**返回** `data` 字段

|返回值字段|字段类型|字段说明|
|----|----|----|
|show_name|string|视频标题|
|goto_type|int|这个应该是有多少个视频|
|goto_value|int|视频av号|
|url|int|视频地址|
