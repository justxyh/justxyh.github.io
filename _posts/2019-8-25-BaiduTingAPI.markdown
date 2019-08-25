---
layout:     post
title:      "BaiduTingAPI"
subtitle:   "百度音乐API整理"
date:       2019-08-25
author:     "JUSTXYH"
header-img: "img/in-post/post-bg-2019-08-25.jpg"
tags:
    - API

---

# 百度音乐API整理



## BaseAPI

```http://tingapi.ting.baidu.com/v1/restserver/ting```

请求方式：```GET```


## 榜单

1. 榜单类型

参数 | 值 
--- | --- 
method | baidu.ting.billboard.billCategory
  
2. 榜单歌曲列表

参数 | 值 
--- | --- 
method | baidu.ting.billboard.billList
type   | 上一个接口响应
size   | 大小
offset | 偏移


## 歌手

1. 歌手列表

参数 | 值 
--- | --- 
method | method=baidu.ting.artist.getList
area   | 0：不限 1：华语 3：欧美 4：日韩 5：其他
sex    | 0：不限 1：男 2：女 3：组合
limit  | 大小
offset | 偏移

2. 歌手歌曲列表

参数 | 值 
--- | --- 
method  | baidu.ting.artist.getSongList
tinguid | 上一个接口响应
limit   | 大小
offset  | 偏移

## 专辑

1. 专辑推荐

参数 | 值 
--- | --- 
method  | baidu.ting.plaza.getRecommendAlbum
limit   | 大小
offset  | 偏移

2. 专辑信息

参数 | 值 
--- | --- 
method   | baidu.ting.album.getAlbumInfo
album_id | 上一个接口响应

## 标签

1. 标签

参数 | 值 
--- | --- 
method  | baidu.ting.tag.getAllTag

2. 标签歌曲列表

参数 | 值 
--- | --- 
method  | baidu.ting.tag.songlist
tagname | 上一个接口响应
limit   | 大小
offset  | 偏移

## 搜索

1. 搜索建议

参数 | 值 
--- | --- 
method  | baidu.ting.search.suggestion
query   | 搜索关键词

2. 搜索

参数 | 值 
--- | --- 
method    | baidu.ting.search.common
query     | 搜索关键词
page_size | 大小
page_no   | 偏移

## 新歌

参数 | 值 
--- | --- 
method  | baidu.ting.plaza.getNewSongs
tagname | 上一个接口响应
limit   | 大小

## 歌曲播放（acc下载链接）

参数 | 值 
--- | --- 
method  | baidu.ting.song.playAAC
songid  | 上一个接口响应

## 推荐歌曲列表

参数 | 值 
--- | --- 
method  | baidu.ting.song.getRecommandSongList
song_id | 上一个接口响应
num     | 大小
