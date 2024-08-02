---
title: SQLmap Note
date: 2024-07-30
categories: [資安]
tags: [note,sqlmap]

description: 基本sqlmap使用方法

published: true #不顯示此文章
---


請參考:[飛飛的SQLmap教學](https://feifei.tw/security-tool-sqlmap/ "https://feifei.tw/security-tool-sqlmap/")

### 基本 Payload

```bash
# 取得資料庫 
sqlmap -u "URL" --dbs 

# 取得資料表 
sqlmap -u "URL" -D 資料庫名稱 --tables  

# 取得欄位 
sqlmap -u "URL" -D 資料庫名稱 -T 資料表名稱 --columns  

# 取得指定欄位的資料 
sqlmap -u "URL" -D 資料庫名稱 -T 資料表名稱 -C 欄位1,欄位2 --dump
```
### 常用參數

- **--batch**：自動選擇預設值，跳過所有提示。
- **--random-agent**：使用隨機選擇的 HTTP User-Agent 標頭值，用於繞過 WAF。
- **--dbms "dbms_type"**：指定後端資料庫類型（如 `"mysql"`、`"Microsoft Access"`）。
- **--force-ssl**：強制使用 SSL/HTTPS。
- **--skip-waf**：跳過 WAF 檢測測試。
- **--os-shell**：獲取操作系統 shell，嘗試執行遠端命令。
- **--flush-session**：清除復現過程記錄，重置會話。

### 內建腳本

```bash
# 使用 tamper script 來繞過 WAF  
--tamper="tamper_script_name"  

# 列出所有內建腳本  
sqlmap --list-tampers
```



