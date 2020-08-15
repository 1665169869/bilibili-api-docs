# 个人中心

## 首页
### account(账户)
调用地址:
https://api.bilibili.com/x/member/web/account
### reward(经验奖励)
调用地址:
https://api.bilibili.com/x/member/web/exp/reward
### user(用户信息)
#### 调用地址:
可填参数:https://api.bilibili.com/x/vip/web/user/info

## 大会员
### button
#### 调用地址
可填参数:https://big.bilibili.com/web/user/vip/button

好像是用来显示过期没 自行调用查看吧，这里就不多放一些没用的接口了

## 会员积分
没会员积分，弄个蛇皮

## 我的信息
调用地址:https://api.bilibili.com/x/member/web/account

## 我的头像
### 激活记录
调用地址:https://account.bilibili.com/pendant/myHistory
|字段| 必选|类型|说明|
|----|----|----|----|
|page|false|string|结果分页选择 默认为第1页|

## 黑名单
调用地址:https://api.bilibili.com/x/relation/blacks
|字段| 必选|类型|说明|
|----|----|----|----|
|re_version|false|?|未知用途|
|pn|false|int|结果分页选择 默认为第1页|
|ps|false|int|单页返回的记录条数，默认为20。(没那么多黑名单，不知道是否有最大限制)|
|jsonp|false|string|填写jsonp即可|

## 我的硬币
### 硬币余额
调用地址:https://account.bilibili.com/site/getCoin
### 硬币记录
可填参数:https://api.bilibili.com/x/member/web/coin/log


## 我的记录
### 登录记录
#### 调用地址
可填参数:
https://api.bilibili.com/x/member/web/login/log

### 节操记录
#### 调用地址
可填参数:
https://api.bilibili.com/x/member/web/moral/log

### 经验记录
#### 调用地址
可填参数:
https://api.bilibili.com/x/member/web/exp/log


### 通用参数（标记为可填参数的，没标记不用填）

|字段| 必选|类型|说明|
|----|----|----|----|
|jsonp|false|string|填写jsonp即可|

### Cookie

|字段|必选|类型|说明|
|----|----|----|----|
|SESSDATA|true|string|这是登录密钥，不填就提示未登录|

### 这些都是要填cookie的 不然会提示未登录