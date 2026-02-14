企業綠色融資暨智慧碳管理平台

專案連結: 點擊開啟模擬系統

📖 專案簡介

本專案為針對金融業設計的 ESG 數位中台原型。旨在解決企業碳盤查數據與銀行投融資碳排（範疇三）之間的斷層。系統整合了 AWS 無伺服器架構 與 人工智慧智能解析 概念，協助法金業務人員與審查單位提升綠色融資的評估效率。

核心解決痛點

數據孤島： 企業自主盤查數據難以即時對接至銀行系統。

人工審閱： 傳統依賴人工翻閱永續報告書，效率低且標準不一。

範疇三計算： 缺乏自動化工具依據 碳核算金融聯盟 方法學計算投融資碳排。

🏗️ 系統架構

本系統採用 三層式架構 設計，確保高可用性與資安合規。

graph TD
    %% 定義樣式
    classDef client fill:#e1f5fe,stroke:#01579b,stroke-width:2px;
    classDef presentation fill:#fff9c4,stroke:#fbc02d,stroke-width:2px;
    classDef business fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px;
    classDef external fill:#eeeeee,stroke:#616161,stroke-width:2px,stroke-dasharray: 5 5;

    subgraph Client_Layer [用戶端環境]
        RM[法金人員 / 審查人員]:::client
        Customer[企業客戶]:::client
    end

    subgraph Presentation_Layer [展示層]
        Web[網頁入口]:::presentation
    end

    subgraph Business_Logic_Layer [業務邏輯層]
        API[介面網址]:::business
        Lambda[雲端函式]:::business
    end

    subgraph External_Systems [外部協作環境]
        Bedrock[智能模組]:::external
    end

    %% 連線關係
    RM -->|加密傳輸| Web
    Customer -->|加密傳輸| Web
    Web -->|數據請求| API
    API --> Lambda
    Lambda -->|碳排運算邏輯| Lambda
    Lambda -.->|模型調用| Bedrock


⚡ 核心功能

1. 碳排試算引擎

技術實作： 使用 Python 部署於 AWS 雲端函式。

功能： 依據 溫室氣體盤查 標準，輸入柴油與電力數據，後端自動引用最新排放係數進行運算。

亮點： 解決前端計算易被竄改之風險，實現雲端集中運算。

2. 人工智慧智能認定

技術概念： 模擬串接 AWS 智能服務。

功能： 自動解析企業上傳之永續報告書，提取「綠色營收佔比」與「資本支出」。

應用場景： 快速判讀企業是否符合金管會「永續經濟活動認定參考指引」。

3. 投融資碳排儀表板

方法學： 內建 碳核算金融聯盟 運算邏輯。

公式： ( 投融資金額 / 企業價值 ) × 企業總碳排

效益： 協助金控端即時監控範疇三排放熱點。

🛠️ 技術棧

前端介面: HTML5, Tailwind CSS, 圖表視覺化工具

後端運算: AWS 雲端運算服務

程式語言: Python

部署環境: 靜態網站託管 + 雲端運算環境

📝 開發者資訊

開發者: 殷小可

$$領英連結$$

此專案為面試展示用途，數據均為模擬資料。
