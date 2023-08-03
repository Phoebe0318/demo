# 用戶註冊及登入功能
密碼用 BCrypt 加密
使用 JPA 及 MyBatis 跟 DB 溝通
將 User ID 包在 JWT 裡

設定Spring Security，除了註冊跟登入外，其他 API 都有 JWT 管控，如果 JWT 失效回傳 HTTP Status 401
並用 Spring Security做 CORS 設定

# Schedule & Async 打卡 API
每日的特定時間用排程計算每個用戶當天的打卡時間差
每一個用戶的打卡時間差計算都用一個 thread 處裡
限制 async task 數量為 8 個，並用 CompletableFuture 管理全部的 task，當全部工作做完印出工作完成 log

# API 文件
設定 Swagger 文件
Swagger UI 支援 JWT header

# i18n
當註冊 API 有帳號重複時，根據 Accept-Language header 回傳不同語系的錯誤訊息

# Log
設定 Slf4j，有 info、debug、error 三種等級
設定 logback 配置檔，info 跟 error 額外寫到自己等級的 log file
