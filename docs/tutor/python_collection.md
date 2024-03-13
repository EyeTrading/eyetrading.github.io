# Python 操作記錄--list、dict、set


## Python List 基本操作

!!! example "<a href="https://docs.python.org/zh-tw/3/tutorial/datastructures.html#more-on-lists" target="_blank">List</a>"
    ```
    {==# empty list==}
    a = []
    a = list()
    {==# 加入資料==}
    a.append(5)
    a.insert(1, 30)
    {==# 刪除資料==}
    del a[0]        #刪除 0位置的資料
    a.remove(30)    #刪除內容為 30 的資料
    a.pop(1)    #取出位於 1位置的資料
    a.clear     #清空資料
    {==# 經常用到==}
    a[-1]       # 取最後一筆資料
    a[5:10]     # 取位置 0,1,2,3,4,5,6,7,8,9,10 中的 5~9的資料
    a[2:]       # 取 2~最後一筆資料
    len(a)      # 返回 list 的個數
    a.count(4)  # 計算 4有幾個
    ```
    

## Python Dict 基本操作

!!! example "<a href="https://docs.python.org/zh-tw/3/tutorial/datastructures.html#dictionaries" target="_blank">Dict</a>"

    ```
    {==# empty dict==}
    d = {}
    d = dict()
    {==# 加入資料==}
    d = {"a": 123, "B": 456, "c": 789}
    {==# 取得資料==}
    a_value = d['a']                # 取得 a的值,若是沒有 a則會出錯
    c_value = d.get('c', None)      #如果沒有c,則回傳 None
    {==# 修改資料==}
    d['a'] = 258
    {==# 刪除資料==}
    del d['a']        #刪除 key: a的資料
    d.pop("B")      #刪除並取出位於 key: B的資料
    d.clear()       #清空
    {==# 常用 ==}
    d.keys()        #回傳所有的 key值
    d.values()      #回傳所有的 value值
    len(d)          #回傳個數
    ```

## Python Set 基本操作

!!! example "<a href="https://docs.python.org/zh-tw/3/tutorial/datastructures.html#sets" target="_blank">Set</a>"

    set 內的資料只會有一個，不會有重複資料.

    ```
    {==# empty dict==}
    s = set()
    {==# 加入資料==}
    s = {"a", 123, "B", 456, "c", 789}
    s.add(99)
    {==# 刪除資料==}
    s.remove("B")
    {==# 常用 ==}
    len(s)          #回傳個數
    ```