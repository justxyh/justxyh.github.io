---
layout:     post
title:      "百度音乐API"
subtitle:   ""
date:       2017-06-08
author:     "JUSTXYH"
header-img: "img/in-post/post-bg-2017-06-08.jpg"
tags:
    - iOS
    - 技术
    - API

---

# 百度音乐API总结

使用青花瓷截包，获取百度音乐部分API，基本能够满足制作一个简单的访百度音乐的APP使用。

其中有部分接口可能由于百度音乐API验证等原因需要添加部分非必要参数，可直接写死在接口地址中。

本文总结的接口均使用GET请求，亲测可用，希望能帮到想自己实现一下音乐播放器的同学。

## 1.1 搜索建议
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.search.catalogSug&query=

| 字段           | 说明          |
| ------------- | ------------- |
| query         | 搜索关键字      | 

## 1.2 搜索
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.search.common&query=

| 字段           | 说明          |
| ------------- | ------------- |
| query         | 搜索关键字      | 

## 2.1 推荐
https://musicapi.qianqian.com/v1/restserver/ting?method=baidu.ting.plaza.index&channel=c8ce05a8404708959360e95bb6fe144333aeb1e7&cuid=appstore&from=ios&version=

## 3.1 歌曲分类
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.tag.getAllTag

## 3.2 分类歌曲列表
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.tag.songlist&tagname=&limit=&offset=

| 字段           | 说明           |
| ------------- | -------------  |
| tagname       | 分类名 由3.1获取 | 
| limit         | 分页数量      | 
| offset        | 分页偏移量      | 

## 4.1 榜单
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.billboard.billCategory

## 4.2 榜单歌曲列表
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.billboard.billList&type=&offset=&size=

| 字段           | 说明           |
| ------------- | -------------  |
| type          | 榜单类别 由4.1获取 | 
| size         | 分页数量       | 
| offset        | 分页偏移量      | 

## 5.1 电台
http://tingapi.ting.baidu.com/v1/restserver/ting?from=ios&method=baidu.ting.scene.getCategoryScene&category_id=

| 字段           | 说明           |
| ------------- | -------------  |
| category_id   | 分类ID         | 

| category_id   | 电台类型        |
| ------------- | -------------  |
| 0             | 活动            | 
| 1             | 主题            | 
| 2             | 天气            | 
| 3             | 心情            | 
| 4             | 语音            | 
| 5             | 年代            | 
| 6             | 曲风            | 

## 5.2 电台歌曲列表
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.song.getSmartSongList&scene_id=&page_no=&page_size=

| 字段           | 说明           |
| ------------- | -------------  |
| scene_id      | 电台ID    由5.1获取     | 
| page_no   | 分页         | 
| page_size   | 分页数量         | 

## 6.1 歌手
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.artist.getList&area=&sex=&abc=&limit=&offset=

| 字段           | 说明           |
| ------------- | -------------  |
| area      | 地区    6:华语 3:欧美 7:韩国 60:日本 5:其他 0:不限     | 
| sex   | 性别   1:男 2:女 3:组合 0:不限        | 
| abc   | 筛选   热门/其他/A~Z        | 
| limit         | 分页数量      | 
| offset        | 分页偏移量      | 

## 6.2 歌手歌曲列表
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.artist.getSongList&tinguid=&offset=&limits=

| 字段           | 说明           |
| ------------- | -------------  |
| tinguid       | 歌手UID 由6.1获取 | 
| limits         | 分页数量      | 
| offset        | 分页偏移量      | 

## 7.1 专辑
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.plaza.getRecommendAlbum&tagname=&offset=&limit=

| 字段           | 说明           |
| ------------- | -------------  |
| tagname       | 标签: 推荐 华语 欧美 日韩 热销 | 
| limit         | 分页数量      | 
| offset        | 分页偏移量      | 

## 7.2 专辑歌曲列表
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.album.getAlbumInfo&album_id=

| 字段           | 说明           |
| ------------- | -------------  |
| album_id       | 专辑ID 由7.1获取 | 

## 8.1 歌单
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.diy.search&page_no=&page_size=&query=

| 字段           | 说明           |
| ------------- | -------------  |
| query      | 关键字 可使用“全部”     | 
| page_no   | 分页         | 
| page_size   | 分页数量         | 


## 8.2 歌单歌曲列表
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.diy.gedanInfo&listid=

| 字段           | 说明           |
| ------------- | -------------  |
| listid       | 歌单ID 由8.1获取  |

## 9.1  MV
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.mv.searchMV&page_num=&page_size=&query=&order=

| 字段           | 说明           |
| ------------- | -------------  |
| query      | query 关键字:全部 内地 港台 欧美 日本 韩国 现场     | 
| order      | order hottest:最热 newest:最新     | 
| page_num   | 分页         | 
| page_size   | 分页数量         | 

## 9.2 MV详情
http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.mv.playMV&mv_id=

| 字段           | 说明           |
| ------------- | -------------  |
| mv_id       | MVID  由9.1获取       | 

## 10.1 歌曲详情
http://ting.baidu.com/data/music/links?songIds=

| 字段           | 说明           |
| ------------- | -------------  |
| songIds       | 歌曲ID         | 
