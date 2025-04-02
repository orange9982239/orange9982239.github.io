---
title: 履歷 Resume
---
# 柳叔旻
> 📞 0932360815
>
> 📍 台北市內湖區安泰街86巷6號3樓
> 
> 📧 orange9982239@gmail.com
>
> 👨‍💻[github](https://github.com/orange9982239)

# ℹ️ 簡介 Profile
## 自介
* 我來自宜蘭縣，大學就讀於屏科大工業工程與管理系。個性隨和，喜歡接觸新事物、工具和技術，並尋求更低本或高效的方法來提高工作成果。
* 初始接觸程式碼是在大學專案中，使用VBA或AppScriot解決重複性工作，後續的IT工作生涯中更多的建置SERVER及專案來解決工作上遇到的問題。

## 工作抱負
* 研究更低本或高效的方法來增加工作成果，持續學習新技術成為有價值的軟體工程師。
* 更高度的自動化
  * 自動作業
    * 固定工作 => script
    * Deploy工作 => cicd
  * 自動告警
    * 硬體
      * BMC發起      => syslog
      * SERVER水線   => snmp
    * 服務狀態
      * port狀態監控
      * os中script監控

# 🎓 學歷 Degree
* 學士	國立屏東科技大學	工業管理系	2015/09-2019/07

# 💼 工作經驗 Job Experience
1. 2020/04 - 2020/09    儒鴻企業股份有限公司    生管	
   * 本職
     * 生管負責追蹤生產中所需要的料件，排期進行生產，期間大量使用excel公式
   * 專案
     * 普及VBA使用，並大量製作小工具給其他生管夥伴
     * 學習python基礎及使用bin方式安裝
     * 邊緣系統開發
       * 利用Python+VBA+SQL SERVER優化既有的powerbuilder建置之前端(匯出時間從3小時降低至5分鐘)

2. 2020/09 – 2022/10    台東大學圖資館          技術師	
   * 本職
     * 使用C#和ASP.NET webform維護校務系統。
     * 部分使用mssql的store procedure。
     * 學習windows及linux伺服器的基礎維運及建置。
     * GIT上文件
       * 軟體建置
   * 專案
     * 學習docker容器化技術及docker容器包版。
     * 學習git flow，建立gitea服務並將SVN轉至git，並推動全組組員對gitflow的使用
     * 學習gitea的進階管理，分組提供儲存庫給外包廠商使用以保留source code。
     * 學習HyperV虛擬化技術，虛擬機器加快校務系統建置。
       1. HyperV建立多台VM(Windows server with IIS)
       2. NLB網路負載平衡綁定VIP
     * 學習jenkins服務，建立jenkins服務以利docker容器的自動化建置。
     * 學習ci/cd流程，建立jenkins服務接入git flow完成初級cicd流程。
     * 學習ASP.NET CORE框架，並應用MVC架構建置`放棄錄取資個專案`
     * 學習DNS SERVER，搭配git flow及jenkins達成只要push到master分支就能Apply到DNS Server中。

3. 2023/02 - 2024/11    台灣遊戲橘子            系統工程師
   * 本職
     * windows,linux server建置、管理、SQL資料撈取
     * 維護遊戲產品    B級 瑪奇
     * 維護遊戲產品    A級 天堂M
     * 維護大數據系統
   * 專案
     1. 掃毒專案
        * 提供全SE建置說明書，及推動全環境進行安裝。
        * 透過Proxy Server更新病毒碼。
        * 用powershell自動掃描權環境中沒有安裝防毒的SERVER。
        * 提供掃毒結果報告
          * mail
          * telegram
     2. Grafana Dashoard專案
        * 設計帶有變數及輸入框的資料撈取面板。
        * 管理權限並提供給營運單位。
     3. Container Registry專案
        * 原因
          * 原廠提供以包好的image(tar檔案)，由於過去無Container Registry，只能透過scp放入每台k8s及docker server中，造成管理不易，故建置Container Registry，將image 存入其中，並透過docker pull的方式取得image。
        * 建置
          * SERVER
            * docker建置gitea(內置Container Registry)
            * 提供原廠單獨組織名稱，方便管理。
          * CLIENT
            * k8s及docker server
            * 配置好私有的registry
        * 腳本
          * 為了簡化tar檔案放入Container Registry的步驟
          1. 在windows端提供powershell腳本
             1. 用來scp檔案到gitea server上，並觸發上方的bash腳本，將檔案放入Container Registry中。
          2. gitea server上的bash腳本
             1. 將tar檔案的image先進到docker引擎中
             2. 打上新的tag後push到Container Registry中
             3. 清理掉tar檔案及docker image
        * 效果
          * 更新image效率增加
            * docker-compose及k8s只需要編輯yml上的image tag
            * 數百台一次完成
     4. 監控建置專案
         * 建置
           * docker建置librenms服務
           * 透過snmp協議收集中每台SERVER的參數
         * 告警
           * 硬體水位
             * 設計告警域值
             * 告警訊息傳送至telegram
           * 服務狀態
     5. Proberbility專案
        * script
          * powershell script收集log、過濾並傳入DB中
        * DB
          * mssql
        * 管理用WEB
          * C# net8 mvc 後台專案建置

# 🛠️ 工具及技能 Tools & Skills
1. 平台與工具 Development Tools
   1. IDE Tools(Visual Studio,VS Code)
   2. Version control(Git,SVN)
2. 維運技術
   1. SERVER建置
      1. 上下架硬體
      2. OS
         1. windows
            * server 2016/2019/2022
         2. linux 
            * ubuntu
            * debian
      3. 虛擬化技術
         1. Hyper-V
         2. VMware ESXI
         3. Prommox VE(KVM)
      4. 容器化技術
         1. 引擎
            1. Docker,Podman
            2. swarm,k8s
         2. 編排 
            1. docker-compose
            2. k8s yml
   2. 伺服器管理
      1. Windows AD
      2. ldap
   3. 監控
      1. SNMP 
      2. IPMI運用

3. 程式開發技能 Program development skills
   1. 腳本: PowerShell, Bash, Python
   2. 前端: HTML/CSS/JavaScript, jQuery/Bootstrap
   3. 後端: C#, Python
   4. DB: SQL Server (SSMS, SQLCmd, Store Procedure)

4. DevOps
   1. Gitea
      1. git csm
      2. container registry
   2. Gitea Actions
   3. Jenkins
      1. Free Style Project