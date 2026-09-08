<p align="center">
    <img src="doc/demo/logo.png" width="80px" />
    <h1 align="center">Cloud Mail</h1>
    <p align="center">基於 Cloudflare 的簡約響應式郵箱服務，支持郵件發送、附件收發 🎉</p> 
    <p align="center">
        傳統中文 | <a href="/README-en.md" style="margin-left: 5px">English </a>
    </p>
    <p align="center">
        <a href="https://github.com/maillab/cloud-mail/tree/main?tab=MIT-1-ov-file" target="_blank" >
            <img src="https://img.shields.io/badge/license-MIT-green" />
        </a>    
        <a href="https://github.com/maillab/cloud-mail/releases" target="_blank" >
            <img src="https://img.shields.io/github/v/release/maillab/cloud-mail" alt="releases" />
        </a>  
        <a href="https://github.com/maillab/cloud-mail/issues" >
            <img src="https://img.shields.io/github/issues/maillab/cloud-mail" alt="issues" />
        </a>  
        <a href="https://github.com/maillab/cloud-mail/stargazers" target="_blank">
            <img src="https://img.shields.io/github/stars/maillab/cloud-mail" alt="stargazers" />
        </a>  
        <a href="https://github.com/maillab/cloud-mail/forks" target="_blank" >
            <img src="https://img.shields.io/github/forks/maillab/cloud-mail" alt="forks" />
        </a>
    </p>
    <p align="center">
        <a href="https://trendshift.io/repositories/20459" target="_blank" >
            <img src="https://trendshift.io/api/badge/repositories/20459" alt="trendshift" >
        </a>
    </p>
</p>


## 項目簡介

衹需要一個域名，就可以創建多個不同的郵箱，類似各大郵箱平臺，本項目支持署到 Cloudflare Workers ，降低服務器成本，搭建自己的郵箱服務

## 項目展示

- [在線演示](https://skymail.ink)<br>
- [部署文檔](https://doc.skymail.ink)<br>

| ![](/doc/demo/demo1.png) | ![](/doc/demo/demo2.png) |
|-----------------------|-----------------------|
| ![](/doc/demo/demo3.png) | ![](/doc/demo/demo4.png) |




## 功能介紹

- **💰 低成本使用**： 可部署到 Cloudflare Workers 降低服務器成本

- **💻 響應式設計**：響應式佈局自動適配PC和大部分手機端瀏覽器

- **📧 郵件發送**：集成Resend發送郵件，支持群發，內嵌圖片和附件發送，發送狀態查看

- **🛡️ 管理員功能**：可以對用戶，郵件進行管理，RABC權限控制對功能及使用資源限制

- **📦 附件收發**：支持收發附件，使用R2對象存儲保存和下載文件

- **🔔 郵件推送**：接收郵件後可以轉發到TG機器人或其他服務商郵箱

- **📡 開放API**：支持使用API批量生成用戶，多條件查詢郵件 

- **🔢 驗證碼識別**：使用Workers AI，自動識別郵件驗證碼 

- **📈 數據可視化**：使用ECharts對系統數據詳情，用戶郵件增長可視化顯示

- **🎨 個性化設置**：可以自定義網站標題，登錄背景，透明度

- **🤖 人機驗證**：集成Turnstile人機驗證，防止人機批量註冊

- **📜 更多功能**：正在開發中...



## 技術棧

- **平臺**：[Cloudflare Workers](https://developers.cloudflare.com/workers/)

- **Web框架**：[Hono](https://hono.dev/)

- **ORM：**[Drizzle](https://orm.drizzle.team/)

- **前端框架**：[Vue3](https://vuejs.org/) 

- **UI框架**：[Element Plus](https://element-plus.org/) 

- **郵件推送：** [Resend](https://resend.com/)

- **緩存**：[Cloudflare KV](https://developers.cloudflare.com/kv/)

- **數據庫**：[Cloudflare D1](https://developers.cloudflare.com/d1/)

- **文件存儲**：[Cloudflare R2](https://developers.cloudflare.com/r2/)

## 目錄結構

```
cloud-mail
├── mail-worker				    # worker後端項目
│   ├── src                  
│   │   ├── api	 			    # api接口層			
│   │   ├── const  			    # 項目常量
│   │   ├── dao                 # 數據訪問層
│   │   ├── email			    # 郵件處理接收
│   │   ├── entity			    # 數據庫實體
│   │   ├── error			    # 自定義異常
│   │   ├── hono			    # web框架配置、攔截器、全局異常等
│   │   ├── i18n			    # 語言國際化
│   │   ├── init			    # 數據庫緩存初始化
│   │   ├── model			    # 響應體數據封裝
│   │   ├── security			# 身份權限認證
│   │   ├── service			    # 業務服務層
│   │   ├── template			# 消息模板
│   │   ├── utils			    # 工具類
│   │   └── index.js			# 入口文件
│   ├── pageckge.json			# 項目依賴
│   └── wrangler.toml			# 項目配置
│
├── mail-vue				    # vue前端項目
│   ├── src
│   │   ├── axios 			    # axios配置
│   │   ├── components			# 自定義組件
│   │   ├── echarts			    # echarts組件導入
│   │   ├── i18n			    # 語言國際化
│   │   ├── init			    # 入站初始化
│   │   ├── layout			    # 主體佈局組件
│   │   ├── perm			    # 權限認證
│   │   ├── request			    # api接口
│   │   ├── router			    # 路由配置
│   │   ├── store			    # 全局狀態管理
│   │   ├── utils			    # 工具類
│   │   ├── views			    # 頁面組件
│   │   ├── app.vue			    # 入口組件
│   │   ├── main.js			    # 入口js
│   │   └── style.css			# 全局css
│   ├── package.json			# 項目依賴
└── └── env.release				# 項目配置
```

## 贊助

<a href="https://doc.skymail.ink/support.html" >
<img width="170px" src="./doc/images/support.png" alt="">
</a>

## 許可證

本項目採用 [MIT](LICENSE) 許可證	


## 交流

[Telegram](https://t.me/cloud_mail_tg)



