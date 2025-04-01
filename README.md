# 如何建置自己的Hexo Blog
## 簡述
因為想要用來放一些公開的筆記，因此找了很多方案，最終決定使用省錢的HEXO搭配github pages，並把建置過程記錄下來。

## 環境安裝
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

## HEXO建置及GIT配置
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
git push -u origin master
```
## 設定主題
為了簡單搭配全文搜尋，用了NexT主題
1. 下載zip放入路徑\themes\hexo-theme-next-8.14.1，資料夾可以自行命名但我採用zip原始名稱。
2. 設定主題
    ```ps1
    # 修改檔案_config.yml
    vim _config.yml

    # theme節點值改為資料夾名稱
    ## title: 柳書的筆記       #網頁標題
    ## subtitle:               #副網頁標題
    ## description: #網站描述
    ## keywords:
    ## author: ritchieliou       #作者
    ## language: zh-tw         #語系(台灣設定為:zh-tw)
    ## timezone: Asia/Taipei   # 時區
    ## theme: hexo-theme-next-8.14.1
    ```
theme: hexo-theme-next-8.14.1
全文查詢
安裝套件
npm install hexo-generator-search --save
NexT主題開啟全文查詢
檔案\themes\hexo-theme-next-8.14.1\_config.ymllocal_search下enable改為true

local_search:
    enable: true
全文查詢快取以json儲存
修改檔案\_config.yml

search:
    path: search.json
    field: post
    content: true
產生查詢快取json
# 啟動伺服器，用來看結果
hexo server

# 清除舊專案並發布
hexo clean              # 有安裝新的package或大改動才清理舊專案
hexo generate           # 產生靜態網頁跟全文查詢快取json
hexo deploy             # 設定完成就能下此指令發布
三、發佈
儲存程式碼
在github上建立兩個儲存庫

儲存nmp source code，名稱隨意
儲存hexo發布的靜態文件，名稱.github.io
發佈 github pages
如果剛好你也是個貧窮開發者，沒錢購買VM，github pages是個好地方

安裝 hexo-deployer-git。
npm install hexo-deployer-git --save
修改檔案\_config.yml
deploy:
    type: git
    repo: <repository url>
    branch: [branch]
    message: [message]
發布url
https://orange9982239.github.io/

REF
https://www.youtube.com/watch?v=RcJxnNpj64k&ab_channel=PegasusWang
https://hexo.io/zh-tw/docs/one-command-deployment.html