# hmplayer

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

# 发现音乐 接口文档

>  所有接口的请求方式都是`get`

## 轮播图

> 说明 : 调用此接口 , 可获取 banner( 轮播图 ) 数据

**可选参数 :**

`type`:资源类型,对应以下类型,默认为 0 即PC

```
0: pc

1: android

2: iphone

3: ipad
```

接口地址：https://autumnfish.cn/banner





## 推荐歌单

>  说明 : 调用此接口 , 可获取推荐歌单

**可选参数 :** `limit`: 获取数量 , 默认为 30 (不支持 offset)

**接口地址 :** https://autumnfish.cn/personalized



## 最新音乐

> 说明 : 调用此接口 , 可获取最新音乐

**接口地址 :** https://autumnfish.cn/personalized/newsong





## 播放歌曲

> 说明 : 调用此接口 , 传入音乐 `id`, 可获得歌曲播放地址

**参数 :** `id`: 音乐 id, 如 `id=347230`

**接口地址 :** https://autumnfish.cn/song/url





## 推荐MV

> 说明 : 调用此接口 , 可获取推荐 mv

**接口地址 :** https://autumnfish.cn/personalized/mv

# 最新MV页面 接口文档

>  所有接口的请求方式都是`get`

## 搜索接口

> 根据关键字搜索结果，通过调整类型，搜索不同的值

**必选参数 :** `keywords` : 关键词

**可选参数 :** 

1. `limit` : 返回数量 , 默认为 30 
2. `offset` : 偏移数量，用于分页 , 如 : 如 :( 页数 -1)*30, 其中 30 为 limit 的值 , 默认为 0

3. `type`: 搜索类型；默认为 1 即单曲 , 取值意义 :如下

```
歌曲:1
歌单:1000
MV:1004
```

**接口地址 :**  https://autumnfish.cn/search

# 歌单详情页 接口文档

>  所有接口的请求方式都是`get`



## 歌单信息

**必选参数 :** `id` : 歌单 id

**接口地址 :** https://autumnfish.cn/playlist/detail



## 热门评论

说明 : 调用此接口 , 传入 type, 资源 id 可获得对应资源热门评论 ( 不需要登录 )

**必选参数 :**

`id` : 资源 id

`tpye`: 数字 , 资源类型 , 对应歌曲 , mv, 专辑 , 歌单 , 电台, 视频对应以下类型

```
0: 歌曲

1: mv

2: 歌单

3: 专辑

4: 电台

5: 视频
```

**可选参数 :**

 `limit`: 取出评论数量 , 默认为 20

`offset`: 偏移数量 , 用于分页 , 如 :( 评论页数 -1)*20, 其中 20 为 limit 的值

**接口地址 :**  https://autumnfish.cn/comment/hot



## 最新评论

说明 : 调用此接口 , 传入音乐 id 和 limit 参数 , 可获得该歌单的最新评论

**必选参数 :** `id`: 歌单 id

**可选参数 :** 

`limit`: 取出评论数量 , 默认为 20

`offset`: 偏移数量 , 用于分页 , 如 :( 评论页数 -1)*20, 其中 20 为 limit 的值

**接口地址 :** https://autumnfish.cn/comment/playlist

# 推荐歌单 接口文档

>  所有接口的请求方式都是`get`



## 歌单列表 - 精品歌单

说明 : 调用此接口 , 可获取精品歌单  

**可选参数 :** 

1. `limit`: 取出歌单数量 , 默认为 20

2. `cat`: 歌单的标签，可选值如下

```
全部
欧美
华语
流行
说唱
摇滚
民谣
电子
轻音乐
影视原声
ACG
怀旧
治愈
旅行
```

**接口地址 :**  https://autumnfish.cn/top/playlist/highquality



## 歌单列表 - 歌单列表

说明 : 调用此接口 , 可获取网友精选碟歌单

**可选参数 :** 

1. `limit`:获取的个数
2. `offset`: 偏移数量 , 用于分页 , 如 :( 页数 -1)*20, 其中 20 为 limit 的值

3. `cat`: 歌单的标签, 可选值如下

```
全部
欧美
华语
流行
说唱
摇滚
民谣
电子
轻音乐
影视原声
ACG
怀旧
治愈
旅行
```

**接口地址 :** https://autumnfish.cn/top/playlist/

# MV详情页 接口文档

>  所有接口的请求方式都是`get`



## MV地址

> 通过这个接口可以获取MV的在线地址

**必选参数 :** `id`: mv的id

**接口地址 :** https://autumnfish.cn/mv/url



##  相关MV

> 说明 : 调用此接口 , 传入 `mvid` 可获取相似 mv

**必选参数 :** `mvid`: mv的id

**接口地址 :** https://autumnfish.cn/simi/mv



## MV信息

> 说明 : 调用此接口 , 传入 mvid ,即可获取MV信息

**必选参数 :** `mvid`: mv 的 id

**接口地址 :** https://autumnfish.cn/mv/detail





## 歌手信息

> 说明 : 调用此接口 , 传入歌手 id, 可获得歌手部分信息,比如歌手的头像

**必选参数 :** `id`: 歌手 id, 可由搜索接口获得

**接口地址 :** https://autumnfish.cn/artists





## MV评论

>  说明 : 调用此接口 , 传入mv id 和 limit 参数 , 可获得该 mv 的所有评论 

**必选参数 :** `id`: mv id

**可选参数 :**

 `limit`: 取出评论数量 , 默认为 20

`offset`: 偏移数量 , 用于分页 , 如 :( 评论页数 -1)*20, 其中 20 为 limit 的值

**接口地址 :** https://autumnfish.cn/comment/mv

# 最新MV页面 接口文档

>  所有接口的请求方式都是`get`

## 全部MV

说明 : 调用此接口 , 可获取全部 mv

**可选参数 :**

1. `area`: 地区,可选值为：全部、内地、港台、欧美、日本、韩国、不填则为全部 
2. `type`: 类型,可选值为：全部、官方版、原生、现场版、网易出品,不填则为全部

3. `order`: 排序,可选值为：上升最快、最热、最新、不填则为上升最快

4. `limit`: 取出数量 , 默认为 30

5. `offset`: 偏移数量 , 用于分页 , 如 :( 页数 -1)*50, 其中 50 为 limit 的值 , 默认 为 0

**接口地址 :**  https://autumnfish.cn/mv/all





