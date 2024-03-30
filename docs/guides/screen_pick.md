# <font color="silver">EyeTrading 功能說明</font>

!!! warning

    類股及選股功能會耗用 Shioaji api 流量，使用量則依據個股數量而定。請參考 <a href="https://sinotrade.github.io/zh_TW/tutor/limit/" target="_blank">Shioaji api 流量限制</a>.

## 類股漲跌

!!! info "類股"
    當日加權指數、櫃買指數以及成交金額排名前11名的類股 K線.

![類股](img/pick_category.png)


## 盤中即時選股

![選股畫面](img/pick_stock.png)


!!! info "Step 1:取得個股清單"

    ![個股清單](img/pick_stock_1.png){ width="250"}

    * 個股日期: 請設定為<span style="color:red;font-weight:bold"> 前一交易日 </span> 的日期。
    * 成交量限制(單位:張): 預設為 1000，表示前一交易日個股成交量 > 1000張的個股。(Minimun:800)
    * 更新個股: 點選之後會自動取得上述設定之個股清單，取得個股清單或異常會有相關訊息出現在選股條件設定的訊息欄位。(<span style="color:red;">因網路關係會有短暫延遲</span>)

    !!! warning "提醒"

        選股功能請務必設定先取得個股清單.


!!! info "Step 2:設定條件"

    ![個股清單](img/pick_stock_2.png){ width="500"}

    - 股價>=: <span style="color:red;">成交價</span> 高於此設定的個股.
    - 股價<=: <span style="color:red;">成交價</span> 低於此設定的個股.
    - 今預估量>=: <span style="color:red;">預估成交量</span> 高於此設定的個股.({==此為預估值，非實際成交量==})
    - 開盤-漲>=: <span style="color:red;">開盤漲幅</span> 高於此設定的個股.
    - 開盤-跌>=: <span style="color:red;">開盤漲幅</span> 低於此設定的個股.
    - 跳空上限>=: <span style="color:red;">開盤漲幅</span> 高於或低於此設定的個股.({==跟漲跌相關==})
    - 估量比-漲>=: <span style="color:red;">估量比</span> 高於此設定的個股.
    - 估量比-跌>=: <span style="color:red;">估量比</span> 高於此設定的個股.
    - 當日振幅>=: <span style="color:red;">當日振幅</span> 高於此設定的個股.
    - 加權比較>=: <span style="color:red;">當日漲跌幅</span> 與加權漲跌幅差.

    設定完條件之後，點選 <span style="color:red;font-weight:bold;"> 設定條件 </span>後即可生效，下次會使用相同設定。<br>
    <br>
    {~~排序方式為下拉式選單，直接選用即可，目前有三種排序~> 調整為點選欄位標題即切換排序~~}

    ![啟動選股](img/pick_stock_sort.png){ width="400"}

        - 漲跌幅: 依漲跌幅大小排序
        - 成交量: 依成交量大小排序
        - {++分量++}: {==依K量大小排序==}
        - 成交價: 依成交價大小排序
        - 量比: 依量比大小排序
        - 估量: 依預估量比大小排序


!!! info "Step 3:啟動盤中選股"

    ![啟動選股](img/pick_stock_2.png)

    - 顯示為<span style="color:red;font-weight:bold"> 停止選股</span>: {==表示目前是停止狀態==}
    - 顯示為<span style="color:green;font-weight:bold"> 選股中</span>: {==表示目前是啟動選股狀態==}

    啟動後，於交易時間 09:00~13:30 將會依條件選出個股.<br>
    點選 <span style="color:red;font-weight:bold"> 停止選股</span>/ <span style="color:green;font-weight:bold">選股中</span>可以隨時{==啟動/停止==}此功能.
    <br>


!!! info "完成"

    下方選股頁面會顯示依據條件設定所選出的多方或空方個股清單以及數量.

    ![啟動選股](img/pick_stock_3.png){ width="500"}
