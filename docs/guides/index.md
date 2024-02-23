# 安裝與設定 EyeTrading



## 下載免安裝版

!!! info "下載"

    [EyeTrading 免安裝版](../assets/EyeTrading.zip)

<div markdown>

## 設定

!!! note "設定檔路徑"

    請至解壓縮後的資料夾(通常為 <font color="red">X:\EyeTrading\</font> )內尋找 <font color="red">config.json</font>，然後打開這個檔案，這是Shioaji api所需要的相關設定.

![Image title](img/setting.png){ align=left }

!!! success ""

    * shioaji_key_name: 輸入設定的key name.(可填可不填)
    * shioaji_key_expire_date: key的過期時間，小於30天時會提醒.(格式: yyyy-mm-dd)
    * shioaji_api_key: 輸入api_key.
    * shioaji_screate_key: 輸入screate_key.
    * ca_path: 輸入憑證的路徑.
    * ca_pid: 輸入個人的ID.
    * ca_passwd: 輸入憑證的密碼.

</div>
<hr>
<div markdown>
    
## 建立桌面捷徑

!!! example "建立捷徑"

    1. 在桌面空白處按滑鼠右鍵後選擇 <font color="red">新增</font> -> <font color="red">捷徑</font>
    2. 出現設定的畫面中選擇 <font color="red">瀏覽</font>
    3. 瀏覽至資料夾 <font color="red">EyeTrading</font> 內，選擇 EyeTrading.exe
    4. 回至建立捷徑畫面後，確認輸入項的位置的檔案是 <font color="red">EyeTrading.exe</font> 後按下一步.
    5. 按完成，即可在桌面看到 EyeTrading.exe 的圖示.

    (可參考下方圖片資訊)

![Image title](img/shortcut_1.png){ width="300"}

![Image title](img/shortcut_2.png){ width="450"}

![Image title](img/shortcut_3.png){ width="450"}

![Image title](img/shortcut_4.png){ width="450"}

![Image title](img/shortcut_5.png){ width="450"}

![Image title](img/down.png){ width="450"}


## 執行

!!! note "請先執行校時程式"

    目前已設定完成，要執行程式之前，請先下載並執行 [網路校時軟體](https://www.stdtime.gov.tw/chinese/details/details.htm) 以避免登入時發生 Timeout Error，然後點擊剛剛建立的 Eyetrading 桌面捷徑.

    ![Image title](img/nclock.png){ width="200"}