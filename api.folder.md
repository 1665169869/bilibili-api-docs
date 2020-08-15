# 收藏夹

## 列出收藏夹

### 调用地址
https://api.bilibili.com/x/v3/fav/folder/created/list-all

- 不填cookie就不显示隐藏的收藏夹

---

### 参数
|参数|必选|类型|说明|
|----|----|----|----|
|up_mid|true|int|用户ID，用于列出该用户的收藏夹|
|rid|false|int|视频播放列出的收藏夹，指的是视频的作者 没啥用|

---
## 收藏视频

### 调用地址 (post)
https://api.bilibili.com/x/v3/fav/resource/deal

- 必填cookie
### 提交表单
|字段|必选|类型|说明|
|----|----|----|----|
|rid|true|int|av号，如果只有bv号请转av号 不需要填av|
|add_media_ids|true|int|收藏夹ID 增加视频到此收藏夹 不然为空即可(二选一)|
|del_media_ids|true|int|收藏夹ID 删除视频到此收藏夹 不然为空即可(二选一)|
|type|true|int|必须为2 不然会提示参数错误|
|csrf|true|string|好像是一个md5密钥，不知道怎么组成的 获取方法用审查元素收藏一次然后找deal看提交的表单就行了|
|jsonp|false|jsonp|填jsonp就好，可以不填 知道干啥的记得联系我|


---
## 返回
|返回值字段|字段类型|字段说明|
|---------|-------|--------|
|prompt|boolean|返回false 有时候返回true 不知道啥情况|

---
## Cookie

|字段|必选|类型|说明|
|----|----|----|----|
|SESSDATA|false|string|这是登录密钥|
