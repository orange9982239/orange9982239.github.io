# 如何用Hexo建置自己的Blog
## 簡述
* 因為想要用來放一些公開的筆記，因此找了很多方案，最終決定使用省錢的HEXO搭配github pages，並把建置過程記錄下來。
* 這篇文檔將會記錄如何安裝環境，以及如何使用HEXO建置Blog，以及如何使用github pages來發布Blog。
* 最終你將得到
  * 放在github pages中的免費的Blog
  * 可自由修改主題
  * 新增修改文章內容
  * Blog中全文搜索

## 一、環境安裝
```ps1
# 安裝git
winget install git
# 安裝vscode
winget install vscode
# 安裝npm
winget install npm
# 安裝nodejs
winget install nodejs
```
## 二、HEXO建置及GIT配置
```sh
# 初始化git
git init

# 建立README.md
touch README.md

# 安裝hexo-cli工具
npm install hexo-cli -g
# 建立專案
hexo init orange9982239.github.io
# 進入專案
cd orange9982239.github.io
# 安裝依賴包
npm install
# 啟動伺服器，用來看結果
hexo server

# 初次提交請替換成個人的user
git add .
git commit -m "first commit"
git remote add origin https://github.com/orange9982239/orange9982239.github.io.git
git push -u origin main
```
## 三、設定next主題及全文查詢
> 為了簡單搭配全文搜尋，用了NexT主題
1. next主題
   1. 下載next主題包
    ```sh
    # 從github下載next主題並放入themes/next路徑下
    git clone https://github.com/theme-next/hexo-theme-next themes/next
    ```
   2. 全文查詢套件
    ```sh
    npm install hexo-generator-searchdb --save
    ```
   3. next主題包設定
       1. 編輯next主題包下的yml設定檔啟用全文搜尋`vim /themes/next/_config.yml`
            > 全文查詢快取以json儲存
            ```yml
            local_search:
              enable: true
            ```
2. hexo專案下_config.yml檔案修改
   1. 設定next主題
    ```yml
    title: 柳書的筆記       #網頁標題
    subtitle:               #副網頁標題
    description:            #網站描述
    keywords:
    author: orange9982239    #作者
    language: zh-TW         #語系(台灣設定為:zh-TW)
    timezone: Asia/Taipei   # 時區
    
    url: https://orange9982239.github.io
    
    theme: next             # 指定主題(themes之下資料夾名稱)
    ```
## 四、測試及發佈
1. 撰寫
   1. 再source\_posts下放MD檔案
2. 測試
    ```ps1
    hexo clean              # 有安裝新的package或大改動才清理舊專案
    hexo generate           # 產生靜態網頁跟全文查詢快取json
    hexo server             # 啟動伺服器，用來看結果
    ```
3. 手動發佈
   1. 套件
        > 安裝deployer-git套件
        ```ps1
        npm install hexo-deployer-git --save
        ```
   2. 配置發佈到gh-pages分支
        > 編輯\_config.yml
        ```yml
        deploy:
        type: git
        repo: https://github.com/orange9982239/orange9982239.github.io.git   # 你的 GitHub 倉庫地址
        branch: gh-pages
        message: "Site updated: {{ now('YYYY-MM-DD HH:mm:ss') }}"
        ```
   3. 發佈
        ```ps1
        hexo deploy             # 設定完成就能下此指令發布
        ```
   4. 確認發佈結果
      1. 設定GitHub Pages
         1. https://github.com/orange9982239/orange9982239.github.io/settings/pages
         2. 來源選擇gh-pages分支
         3. 路徑選擇根目錄(/)
      2. 檢查github.io
        > https://orange9982239.github.io