# bilibili-api-docs
哔哩哔哩网页版的API接口

## 导航

[搜索](./api.search.md);
[收藏夹](./api.folder.md);
[个人中心](./api.acount.md);
[其他](./api.other.md);

### 通用错误代码

|代码|说明|
|----|----|
|-1|应用程序不存在或已被封禁|
|-2|Access key错误|
|-3|API校验密匙错误|
|-101|帐号未登陆|
|-102|帐号被封停|
|-103|积分不足|
|-104|硬币不足|
|-105|验证码错误|
|-106|帐号未激活|
|-107|帐号非正式会员或在适应期|
|-108|应用沒有存取相应功能的权限|
|-400|请求有误|
|-403|权限不足|
|-404|文档不存在|
|-500|服务器内部错误|
|-503|调用速度过快|

### 请求方法

官方的好像都是get请求，不需要太复杂 如果是post请求我会特别标注

### 大多数参数都没进行实际测试，如果不能用请反馈<br>我不可能一个个测试，那样太慢了