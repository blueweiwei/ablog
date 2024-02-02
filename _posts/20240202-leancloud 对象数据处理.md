---
layout: post
title: leancloud 对象数据处理
date: 2024-02-02
Author: 小萌 
tags: [ 技术分享 ]
comments: true
toc: true

---

> learncloud 作为简单后端数据库

需要提前引入  axios.js  script 脚本

headers 包含账号信息

#### 1. 创建对象

   官方案例

   ```tex
   curl -X POST \
     -H "X-LC-Id: {{appid}}" \
     -H "X-LC-Key: {{appkey}}" \
     -H "Content-Type: application/json" \
     -d '{"content": "每个 Java 程序员必备的 8 个开发工具","pubUser": "LeanCloud官方客服","pubTimestamp": 1435541999}' \
     https://API_BASE_URL/1.1/classes/Post
   ```

   axios 请求

   ```html
   // 获取数据
       axios({
         method:'post',
         url:'https://api.com/1.1/classes/post',
         headers:{
           'X-LC-Id' : appId,
           'X-LC-key' : appKey,
           'content-type' : 'application/json'
         },
         data:{
           "content" : "weiwei"
         }
       }).then(res =>{
           console.log(res);
       });
   ```

#### 2. 获取对象

   官方案例

   ```html
   curl -X GET \
     -H "X-LC-Id: {{appid}}" \
     -H "X-LC-Key: {{appkey}}" \
     https://API_BASE_URL/1.1/classes/Post/<objectId>
   ```

   axios 请求

   ```html
   // 获取对象
       axios({
         method:'get',
         url:'https://api.com/1.1/classes/post/<objectId>',
         headers:headers
       }).then(res =>{
           console.log(res);
       });
   ```

#### 3. 更新对象

   官方案例

   ```html
   curl -X PUT \
     -H "X-LC-Id: {{appid}}" \
     -H "X-LC-Key: {{appkey}}" \
     -H "Content-Type: application/json" \
     -d '{"content": "每个 python 程序员必备的 8 个开发工具"}' \
     https://API_BASE_URL/1.1/classes/Post/<objectId>
   ```

   axios 请求

   ```html
   //更新对象
   	axios({
         method:'put',
         url:'https://api.com/1.1/classes/post/<objectId>',
         headers:headers,
         data:{
           "content" : "每个 python 程序员必备的 8 个开发工具"
         }
       }).then(res =>{
           console.log(res);
       });
   ```

#### 4. 删除对象

   官方案例

   ```html
   curl -X DELETE \
     -H "X-LC-Id: {{appid}}" \
     -H "X-LC-Key: {{appkey}}" \
     https://API_BASE_URL/1.1/classes/Post/<objectId>
   ```

   axios 请求

   ```html
   //删除对象
       axios({
         method:'delete',
         url:'https://api.com/1.1/classes/post/<objectId>',
         headers:headers,
       }).then(res =>{
           console.log(res);
       });
   ```

经过测试，以上应用正确