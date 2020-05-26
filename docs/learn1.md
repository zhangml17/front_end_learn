## Vue_learn part 1
### Questions
#### [element-ui中使用@mouseenter、@mouseleave不起作用](https://blog.csdn.net/weixin_34138056/article/details/88683332)
```
分析原因：elementUI内部把相关的方法禁止。
有效写法： <el-button type="primary" @mouseenter.native="loginBtn()">登录</el-button>。
依次推论并验证：在非element标签中使用@mouseenter，能正常执行，无需添加native。
```
