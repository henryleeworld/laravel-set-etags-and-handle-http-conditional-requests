# Laravel 10 設定 ETag 回應標頭和處理 HTTP 條件式請求

引入 werk365 的 etagconditionals 套件來擴增設定 ETag 回應標頭和處理 HTTP 條件式請求，針對資源發出起始要求且針對資源啟用快取時，伺服器會產生資源回應的 ETag 值，Cache-control 標示為 private 以確保僅現行使用者可以重複使用快取的內容，no-cache 表示要求伺服器檔案時必須以 ETag 確認是否有更新檔案，若無更新，伺服器不需回應檔案。

## 使用方式
- 把整個專案複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
```sh
$ git clone
```
- 將 __.env.example__ 檔案重新命名成 __.env__，如果應用程式金鑰沒有被設定的話，你的使用者 sessions 和其他加密的資料都是不安全的！
- 當你的專案中已經有 composer.lock，可以直接執行指令以讓 Composer 安裝 composer.lock 中指定的套件及版本。
```sh
$ composer install
```
- 產生 Laravel 要使用的一組 32 字元長度的隨機字串 APP_KEY 並存在 .env 內。
```sh
$ php artisan key:generate
```
- 在瀏覽器中輸入已定義的路由 URL 來訪問，例如：http://127.0.0.1:8000。
- 你可以經由 `/` 來進入歡迎頁面。

----

## 畫面截圖
![](https://i.imgur.com/38XdBae.png)
> ETag 是 HTTP 提供的快取機制，可以讓伺服器利用簡單的字串比對，來驗證客戶端先前快取到的 HTTP 回應是否依然有效
