 大立光 (Largan Precision) - 製程工程師面試紀錄
💰 職位待遇與工作環境 (Compensation & Environment)
基本薪資 (Base Salary): NT$ 35,000
工作時間 (Work Hours): 07:50 - 20:50 (每日 13 小時，高強度長工時)
休假制度 (Off Days): 每月僅排休 5 天 (高壓排班制)
環境要求: 需配合產線與技術需求，著重於自動化與數據監控。
🧩 技術面試情節：監控系統的效率挑戰 (The Efficiency Challenge)
面試官透過開發一套「機台數據監控系統」的情境，連續追問了三個核心技術問題：
1. 數據結構的抉擇：List vs. Array
情境： 每秒有上萬筆機台壓力數據湧入，該如何儲存？
回答： 我選擇 Array (如 NumPy Array)。在大數據場景下，list 記憶體不連續且速度慢；array 在記憶體中連續存放，支援向量化運算。在追求精密與速度的大立光產線，效能（Performance）即是金錢，使用 Array 能讓運算效率提升百倍。
2. 非同步 API 的必要性：def vs. async def
情境： 數據傳輸至雲端時，如何確保監控程式不卡死？
回答： 必須使用 async def。若用傳統 def，程式會因等待網路回應（I/O 阻塞）而中斷數據接收；非同步開發能讓程式在等待傳輸時，繼續抓取下一秒的即時數據，確保產線監控「零間斷」。
3. 物件引用的陷阱：The Append Trap
情境： 連續使用 append 將 list1 放入 list2 再放入 list3，若修改 list1 後輸出，結果為何？
回答： 這涉及 Reference (引用) 觀念。因為 append 存入的是記憶體地址而非副本，修改 list1 會導致 list2 與 list3 同步變動。在處理產線邏輯時，若未注意此陷阱，可能導致歷史數據被污染，造成系統判斷錯誤。
