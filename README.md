# 須知  

## 程式碼分區如下

**Branches:**  

`Main`: 主線進程，所有操作都位於此  
`Q1, Q2, …`: 題目完成，並且經過測試，`stats.txt`, `log` 都已位於繳交區  

**NVmain**: 因為在 docker 中創建，root 權限大於 user，git 無法擷取內容，不過沒有變更應該不用在意吧？  

## 啟用方法  

切換到選定 branch，因為 docker 因素，需要覆蓋原有的編譯過的 gem5，以及完整的 nvmain 檔案  

有修改的內容一定有在 GitHub 中，未被覆蓋的部分都沒有變更過  

切換 branch 後，scon... 的混合編譯後  

就可以使用了  

## 運行指令:  

*
*
*
*
*