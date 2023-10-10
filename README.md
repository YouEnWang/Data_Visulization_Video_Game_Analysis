# Video Game Analysis
## 主題
電視遊戲全球分布分析
## 選題動機
電視遊戲（又稱電子遊戲）在1970年代開始以商業娛樂媒體的形式出現在市面上，隨著時間演進，逐漸成為人們重要的娛樂項目。近年受疫情影響，遊戲成為居家休閒的最佳活動之一，大眾在遊戲產業中的消費大幅上升，也成功讓電視遊戲產業再次邁入新的高峰。清明連假時第一次與朋友玩Switch，發現現在的電子遊戲相比於10年前Wii那樣的電子遊戲，在畫質、運行速度與遊玩體驗上，都有明顯的進步。剛好這次在Kaggle上搜尋資料時，看到Video Game Sales這個數據集，便以此當作資料來進行期中報告的資料分析。
## 問題發現與解決
1. rollup()函式使用限制：
   - 問題描述：發現rollup只能對兩個數據及進行groupby，無法對多組數據同時rollup，導致只能用array把多個rollup完的數據存入，在return此array。但在分割array時，發現分割的語法與python有很大不同。
   - 解決方式：多次嘗試後仍無法將資料分割成課堂ppt中return的array like，導致無法以課堂的方式進行後續的sorting以及繪圖。所以最後決定以前述類似state machine的方式進行資料分類。
2. svg繪圖遇到之問題：
   - 問題描述：在嘗試將setupCanvas這個function簡化，使其只要接收一個數據集以及一個state即可完成繪圖的過程中發現，在設自訂變數時，一定要把自訂變數設定初始值。在不知道如何設定資料型態的情況下，使我無法在程式中呼叫數據集內的資料。
   - 解決方式：在現階段初學javascript的情況下，無奈只能將全部的數據集都送入function，並為每個數據都寫一段繪製bar chart的程式碼，才能達到想要的結果。
## 心得
在找資料的過程中，有在網路上看到很多程式大佬做的資料視覺化專案，發現設計精美的分析圖確實能讓人眼睛為之一亮，但呈現的資料讓人容易讀懂也相當重要。我在程式設計的最後一個步驟時，原本想設計讓畫面一次只會顯示一張分析圖，並讓使用者能透過鍵盤按鍵切換不同的bar chart，但多次嘗試d3.select()函式、keydown設置、使用Event.keyCode甚至是清空svg的selectAll("*").remove()語句都無法順利運行。雖然也有試著用後續課堂會使用的按鍵方式想要達到目標，但內部的一些語法卻不知道該如何設定。因為種種原因，所以後來仍然選擇讓視窗上顯示所有的分析圖，期待後續課程我能在理解完老師的講解過後，回頭成功完成此項目標。
