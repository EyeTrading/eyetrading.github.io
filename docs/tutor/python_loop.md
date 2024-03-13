# Python 操作記錄--for 迴圈


## <a href="https://docs.python.org/zh-tw/3/tutorial/controlflow.html#for-statements" target="_blank">Python for-loop</a> 基本操作

!!! example "Range"
    ```
    for n in range(100):
        print(n)
    ```

!!! example "list"
    ```
    {==# 一般==}
    n_lists = [1,2,3,4,5,6]
    for n in n_lists:
        print(n)

    {==# 含index==}
    for i, n in enumerate(n_lists):
        print(f"index:{i}, value:{n}")
    
    ```
    
!!! example "dict"
    ```
    {==# 一般==}
    n_dicts = {"a":1, "b":2, "c":3, "d":4}
    for n in n_dicts:
        print(n)

    {==# keys==}
    for key in n_dicts.keys():
        print(key)

    {==# values==}
    for value in n_dicts.values():
        print(value)

    {==# items==}
    for key, value in n_dicts.items():
        print(f"{key},{value}")
    
    ```