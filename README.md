# 離線安裝完整 Angular 開發環境 (大型企業適用)

## 工具與版本

* 適用 Windows 7 以上版本
* Node.js v8.11.4 (64-bit)
    * npm v5.6.0
* Angular CLI v6.1.5
    * rxjs v6.3.1
    * typescript v2.9.2
* Visual Studio Code v1.26.1 (64-bit)
    * Angular Extension Pack v6.4.0
    * Chinese (Traditional) Language Pack for Visual Studio Code v1.26.3

## 預設安裝的路徑

請按照自身電腦環境與磁碟大小，自行調整路徑：

* `D:\Nodejs`
* `D:\VSCode`

## 安裝步驟說明

1. 先到 [Releases](https://github.com/doggy8088/angular6-offline-install/releases/) 下載三個壓縮檔案

    * `node-v8.11.4-win-x64_npm-cache_angular-cli-v6.1.5.zip`
    * `VSCode-win32-x64-1.26.1.zip`
    * `VSCode-win32-x64-1.26.1-exts.zip`

2. 解壓縮 `node-v8.11.4-win-x64_npm-cache_angular-cli-v6.1.5.zip` 到 `D:\` 目錄下。

    設定 npm 預設快取目錄

    ```bash
    npm config set cache "D:\\Nodejs\\npm-cache"
    ```

    設定 npm 預設採用離線安裝優先

    ```bash
    npm config set prefer-offline true
    ```

3. 解壓縮 `VSCode-win32-x64-1.26.1.zip` 到 `D:\VSCode` 目錄下。

4. 解壓縮 `VSCode-win32-x64-1.26.1-exts.zip` 到 `%USERPROFILE%\` 目錄下。

5. 設定 `PATH` 環境變數，加入以下兩個路徑：

    * `D:\Nodejs`
    * `D:\VSCode\bin`

    快速啟動環境變數編輯器的命令：

    ```bash
    rundll32 sysdm.cpl,EditEnvironmentVariables
    ```

6. 啟動「命令提示字元」視窗，並測試執行以下命令：

    先檢查版本資訊：

    ```bash
    node -v
    npm -v
    ng -v
    ```

    建立 Angular 專案骨架 ( 跳過 Git 初始化與 npm install 動作 )

    ```bash
    ng new demo1 --skip-git --skip-install
    ```

    進入專案資料夾

    ```bash
    cd demo1
    ```

    嘗試「完全離線」安裝 (如果有錯誤發生，還要看下個步驟能不能執行才能確定是否設定成功)

    ```bash
    npm install --offline
    ```

    啟動 Angular 應用程式 (如果可以成功執行，且看到網頁顯示，就代表沒問題)

    ```bash
    npm start
    ```

    開啟瀏覽器，打開 `http://localhost:4200/` 網頁。如果可以看到大大的 Angular 圖示，就代表你設定成功啦！

7. 如果上述都可以成功設定，未來在使用 Angular 開發的過程中，就可以跟一般人完全相同。

    建立新專案

    ```bash
    ng new demo1 --routing
    ```

    建立新元件

    ```bash
    ng g c header --skip-tests
    ```

    安裝 jquery 與 @types/jquery 套件

    ```bash
    npm i jquery @types/jquery
    ```

## 相關文章

* [離線安裝完整 Angular 開發環境的標準作業流程 (大型企業適用)](https://blog.miniasp.com/post/2018/09/01/Offline-installation-for-Angular-6-SOP.aspx)
