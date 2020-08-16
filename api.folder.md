# 收藏夹

## 列出收藏夹

> https://api.bilibili.com/x/v3/fav/folder/created/list-all

- 不填`cookie`就不显示隐藏的收藏夹

*请求方式：GET*

---

**参数**
|参数|必选|类型|说明|
|----|----|----|----|
|up_mid|true|int|用户ID，用于列出该用户的收藏夹|
|rid|false|int|视频播放列出的收藏夹，指的是视频的作者 没啥用|

---
## 收藏视频
- 认证方式：[Cookie（SESSDATA）](#cookie);

- 鉴权方式：[Cookie（SESSDATA、bili_jct）](#cookie)方式时需要验证referer为 .bilibili.com域名下<br>但我自己试了试，可以不用 如果用不了就试试

> https://api.bilibili.com/x/v3/fav/resource/deal

*请求方式：post*

### 提交表单
|字段|必选|类型|说明|
|----|----|----|----|
|rid|true|num或str|av号请填写数字<br>BV号填写完整即可|
|add_media_ids|true|int|收藏夹ID<br>增加视频到此收藏夹<br>不然为空即可(二选一)|
|del_media_ids|true|int|收藏夹ID<br>删除视频到此收藏夹<br>不然为空即可(二选一)|
|type|true|num|必须为2 不然会提示参数错误|
|csrf|true|string|使用cookie [查看获取方法](#cookie)|


---

**返回**

根对象：

| 字段| 类型 | 内容 | 备注 |
| ------- | ---- | -------- | ------- |
| code| num| 返回值 | 0：成功<br />-101：账号未登录<br />-111：csrf校验失败<br />-400：请求错误<br />-403：访问权限不足<br />10003：不存在该稿件<br />11201：已经收藏过了<br />11202：已经取消收藏了<br />11203：达到收藏上限<br />72010017：参数错误 |
| message | str| 错误信息 | 正确为0|
| data| obj| 信息本体 ||

`data`对象：

| 字段 | 类型 | 内容| 备注 |
| ------ | ---- | ----- | ------------ |
| prompt | bool | false | 作用尚不明确 |

---

## 判断视频是否被收藏

> http://api.bilibili.com/x/v2/fav/video/favoured

*请求方式：GET*

认证方式：[Cookie（SESSDATA）](#cookie)

**参数**

| 参数名| 类型| 内容| 必要性| 备注 |
| ---------- | -------- | -------- | ----------- | ---- |
| aid| num或str | 视频avID或视频bvID | 必要||

**返回**

根对象：

| 字段 | 类型 | 内容| 备注 |
| ------- | ---- | -------- | -------|
| code | num| 返回值| 0：成功<br />-400：请求错误<br />-101：账号未登录 |
| message | str| 错误信息 | 默认为0 |
| ttl| num| 1||
| data | obj| 信息本体 ||

`data` 对象：

| 字段| 类型 | 内容| 备注 |
| -------- | ---- | -------- | ---------|
| count | num| 1| 作用尚不明确|
| favoured | bool | 是否收藏 | true：已收藏<br />false：未收藏 |

## Cookie

|字段|必选|类型|说明|
|----|----|----|----|
|SESSDATA|false|string|这是登录密钥|
|bili_jct|false|string|md5密钥 csrf使用的|
