# 凱基API 操作記錄--登入、登出

## 凱基API 初始化元件

!!! example "Initialize"

    ```
    import clr
    from System import UInt16
    clr.AddReference("Package")      #必要引用dll
    clr.AddReference("PushClient")   #必要引用dll
    clr.AddReference("TradeCom")     #必要引用dll
    from Smart import TaiFexCom

    port = xxxx
    # Initialize TaiFexCom 元件.
    tradecom = TaiFexCom("", UInt16(port), 'API')
    print(tradecom.version)

    ...成功的話，可以看到console上面秀出元件的版本，版本有可能不同...
    2022050517
    
    tradecom.OnGetStatus += onGetStatusFunc            {==#設定狀態事件通知的處理==}
    tradecom.OnRcvMessage += onRcvMsgFunc              {==#設定資料接收事件通知的處理==}
    tradecom.OnRecoverStatus += onRecoverStatusFunc    {==#設定資料回補事件通知的處理==}
    tradecom.OnRcvServerTime += onRcvServerTimeFunc    {==#設定系統時間事件通知的處理==}

    def onGetStatusFunc(sender, status, msg):
        pass
    def onRcvMsgFunc(sender, pkg):
        pass
    def onRecStatusFunc(sender, topic, status, count):
        pass
    def onRcvServerTimeFunc(sender, time, quality):
        pass
    ```

## 凱基API 登入

!!! example "接收狀態事件"

    ```
    # 設定 GetStatusFunc 印出內容
    def onGetStatusFunc(sender, status, msg):
        smsg = bytes(msg).decode('UTF-8','strict')
        res = {
            'Event': 'GetStatus',
            'status': status.ToString(),
            'msg': smsg
        }
        print(res)

    ```

!!! example "資料回補事件"

    ```
    # 設定 onRecoverStatusFunc 印出內容
    def onRecoverStatusFunc(sender, topic, status, count):
        res = {
            'Event': 'RECOVER',
            'topic': topic,
            'status': status.ToString(),
            'count': count
        }
        print(res)
    ```

!!! example "Login"

    ```
    ...需完成元件 initialze 才可...
    # 需先設定訊息
    tradecom.AutoSubReport = True               {==#訂閱回報==}
    tradecom.AutoRecoverReport = True           {==#自動回補委託/成交資料==}
    tradecom.AutoRetriveProductInfo = True      {==#自動下載商品檔==}

    # 登入資訊 請填入申請後 券商提供的相關主機及帳號資料
    host = 'xxxxx'
    port = xxxx
    person_id = 'a123456789'
    passwd = 'login'

    # 登入
    tradecom.LoginDirect(host, UInt16(port), person_id, passwd, {==' '==})    {==#最後一個欄位就是空白沒有打錯==}

    ===Console 訊息===
    {'Event': 'GetStatus', 'status': 'CONNECT_READY', 'msg': '連線成功'}            {==#當主機資訊設定正確且可連線時==}
    ...連線成功之後，會開始商品資料的回補...
    {'Event': 'RECOVER', 'topic': 'ProList.xml', 'status': 'RS_BEGIN', 'count': 0}
    {'Event': 'RECOVER', 'topic': 'ProList.xml', 'status': 'RS_DONE', 'count': 275}
    {'Event': 'RECOVER', 'topic': 'ProductBaseSv1801.xml', 'status': 'RS_BEGIN', 'count': 0}
    {'Event': 'RECOVER', 'topic': 'ProductBaseSv1801.xml', 'status': 'RS_DONE', 'count': 367}
    ...略...
    {'Event': 'GetStatus', 'status': 'LOGIN_READY', 'msg': '登入成功'}              {==#登入資料正確時==}
    ===Console 訊息===
    ```

## 凱基API 登出

!!! example "Logout"

    ```
    ...需完成元件 initialze且登入成功之後...

    tradecom.logout()
    tradecom.Dispose()

    ===Console 訊息===
    {'Event': 'GetStatus', 'status': 'DISCONNECTED', 'msg': ''}
    ===Console 訊息===
    ```