# 安裝與設定 EyeTrading

## 下載免安裝版

!!! warning "請確定您有 <span style="color:red;font-weight:bold"><a href="https://sinotrade.github.io/tutor/prepare/open_account/" target="_blank">永豐金證券</a></span> 的帳戶並且有申請 <span style="color:red;font-weight:bold"><a href="https://sinotrade.github.io/tutor/prepare/terms/" target="_blank">Shioaji API</a></span> 的使用權限。請確保有 <span style="color:red;font-weight:bold">備援系統</span> 可使用。{==盤後選股不需要登入永豐帳號==}"

!!! warning "測試版限制"

    - 使用期限: <span style="color:red;font-weight:bold"> 2024/03/31</span>
    - 下單數量: <span style="color:red;font-weight:bold"> 1 張</span>
    - 下單視窗: <span style="color:red;font-weight:bold"> 1 個</span>
    - 零股: <span style="color:red;font-weight:bold"> 價格非零股報價</span>

!!! info "下載"

    請先閱讀 [免責聲明](../disclaimer.md/)，下載即視為您已閱讀其內容並同意相關事項。
    
    - Windows10/11: {~~[EyeTrading Windows免安裝版 V0.5.6]~> 請看連絡方式~~}
    - {++MacOS++}: {~~[EyeTrading Mac免安裝版 V0.5.6]~> 請看連絡方式~~}

    V0.5.6 Release:

        - feat: 新增盤後選股(目前只一個策略)
        - feat: K線圖(Mac版)
    
    V0.5.3 Release:
    
        - fixed: 量比修正.
        - feat: 調整排序為選股Table header.
        - feat: 調整啟動選股至視窗內.

    !!! tips "Windows執行程式遇到保護問題"

        ![win_warn_1](img/win_warn_1.png){ width="300" align=left}

        ![win_warn_1](img/win_warn_2.png){ width="300" align=right}

    !!! tips "Mac執行時遇到檔案已損毀問題"

        請參考<a href="https://epe.idv.tw/fix-app-damaged-cant-be-opened-trash-error-mac/" target="_blank"> 如何解決 MACOS 碰到 「XXX」應用程式已損毀，無法打開．你應該將其丟到「垃圾桶」的問題</a>

        步驟如下：

        1. 打開 {==終端機==}
        2. 於終端機內輸入指令```{++xattr -cr /路徑/EyeTrading.app++}```，可於輸入完 {==xattr -cr ==}後將 app拖入終端機內就會直接帶出路徑，然後Enter即可
        3. 再次執行 EyeTrading應用程式即可.

    
<div markdown>
    
## 建立桌面捷徑

!!! example "建立捷徑"

    1. 在桌面空白處按滑鼠右鍵後選擇 <font color="red">新增</font> -> <font color="red">捷徑</font>
    2. 出現設定的畫面中選擇 <font color="red">瀏覽</font>
    3. 瀏覽至資料夾 <font color="red">EyeTrading</font> 內，選擇 EyeTrading.exe
    4. 回至建立捷徑畫面後，確認輸入項的位置的檔案是 <font color="red">EyeTrading.exe</font> 後按下一步.
    5. 按完成，即可在桌面看到 EyeTrading.exe 的圖示.

    (可參考下方圖片資訊)

    ![Step1](img/shortcut_1.png){ width="250"}

    ![Step2](img/shortcut_2.png){ width="400"}

    ![Step3](img/shortcut_3.png){ width="400"}

    ![Step4](img/shortcut_4.png){ width="400"}

    ![Step5](img/shortcut_5.png){ width="400"}

    ![Down](img/down.png){ width="250"}


## 執行

!!! note "請先執行校時程式"

    目前已設定完成，要執行程式之前，請先下載並執行 <a href="https://www.stdtime.gov.tw/chinese/details/details.htm" target="_blank">網路校時軟體</a> 以避免登入時發生 Timeout Error，然後點擊剛剛建立的 Eyetrading 桌面捷徑.

    ![Time](img/nclock.png){ width="200"}

