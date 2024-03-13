# 永豐Shioaji api 操作記錄--取得行情


## Shioaji API 行情種類

- 即時: 
    - 即時行情: <a href="https://sinotrade.github.io/tutor/market_data/streaming/stocks/" target="_blank">subscribe()</a>
    - 市場快照: <a href="https://sinotrade.github.io/tutor/market_data/snapshot/" target="_blank">snapshot()</a>
    - 市場排行: <a href="https://sinotrade.github.io/tutor/market_data/scanners/" target="_blank">scanner()</a>
- 歷史:
    - 明細: <a href="https://sinotrade.github.io/tutor/market_data/streaming/historical/" target="_blank">ticks()</a>
    - K線: <a href="https://sinotrade.github.io/tutor/market_data/streaming/historical/" target="_blank">kbars()</a>


## 即時行情

!!! example "subscribe/unsubscribe"

    ### 訂閱
    ```
    # 登入並等 Contract 下載完成後

    api.quote.subscribe(
        api.Contracts.Stocks["2330"],   #合約
        quote_type = sj.constant.QuoteType.Tick, #報價種類
        version = sj.constant.QuoteVersion.v1   #版本
    )
    # quote_type 共有三種: {==sj.constant.QuoteType.Tick(成交明細)、sj.constant.QuoteType.bidask(五檔)、sj.constant.QuoteType.quota(五檔+明細)==}
    ```

    ### 取消訂閱
    ```
    # 已有訂閱合約情況下

    api.quote.unsubscribe(
        api.Contracts.Stocks["2330"],   #合約
        quote_type = sj.constant.QuoteType.Tick, #報價種類
        version = sj.constant.QuoteVersion.v1   #版本
    )
    
    ```
    
!!! example "snapshot"

    ### 快照
    ```
    # 登入並等 Contract 下載完成後

    snapshot = api.snapshots([api.Contracts.Stocks['6231']])
    print(snapshot)
    # response
    {== Snapshot(ts=1709821800000000000, code='6231', exchange='OTC', open=293.0, high=298.0, low=282.5, close=284.0, ==}
    {== tick_type=<TickType.Sell: 'Sell'>, change_price=-7.5, change_rate=-2.57, change_type=<ChangeType.Down: 'Down'>, ==}
    {== average_price=288.14, volume=2, total_volume=2210, amount=568000, total_amount=636783310, yesterday_volume=2382.0, ==}
    {== buy_price=284.0, buy_volume=3.0, sell_price=284.5, sell_volume=4, volume_ratio=0.93) ==}
    ```

!!! example "scanner"

    ### 排行
    ```
    # 登入並等 Contract 下載完成後
    # 有五種排行: ChangePercentRank(漲跌幅)、ChangePriceRank(漲跌點數)、DayRangeRank(振幅)、VolumeRank(成交量)、AmountRank(成交金額)
    rank = api.scanners(
        scanner_type=sj.constant.ScannerType.VolumeRank,
        count=1
    )
    print(rank)
    
    ```


## 歷史行情

!!! example "Ticks"

    ### 成交明細

    ```
    # 登入並等 Contract 下載完成後
    {==# 當日==}
    ticks = api.ticks (
        contract = api.Contracts.Stocks['2317'],
        date = "2024-03-13"
    )

    {==# 區間==}
    ticks = api.ticks(
        contract=api.Contracts.Stocks["2317"], 
        date="2024-03-13",
        query_type=sj.constant.TicksQueryType.RangeTime,
        time_start="11:19:00",
        time_end="11:33:00"
    )
    ```


!!! example "KBars"

    ### K棒

    ```
    # 登入並等 Contract 下載完成後
    kbars = api.kbars (
        contract = api.Contracts.Stocks['2317'],
        start = "2024-03-12",
        end = "2024-03-13",
    )
    {==歷史資料 From 2020-03-02 to now ==}
    ```