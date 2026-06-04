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

* Q1:
```bash
./build/X86/gem5.opt configs/example/se.py -c tests/test-progs/hello/bin/x86/linux/hello --cputype=TimingSimpleCPU --caches --l2cache --mem-type=NVMainMemory --nvmainconfig=../NVmain/Config/PCM_ISSCC_2012_4GB.config 2>&1 | tee log
```

* Q2:
```bash
./build/X86/gem5.opt configs/example/se.py -c tests/test-progs/hello/bin/x86/linux/hello --cputype=TimingSimpleCPU --caches --l2cache --l3cache --mem-type=NVMainMemory --nvmainconfig=../NVmain/Config/PCM_ISSCC_2012_4GB.config 2>&1 | tee log
```

* Q3_2-way:
```bash
./build/X86/gem5.opt configs/example/se.py -c quicksort/quicksort --cputype=TimingSimpleCPU ---caches --l2cache --l3cache --l1d_size=4kB --l1i_size=4kB --l2_size=16kB --l3_size=1MB --l3_assoc=2 --mem-type=NVMainMemory --nvmainconfig=../NVmain/Config/PCM_ISSCC_2012_4GB.config 2>&1 | tee log
```

* Q3_full-way:
```bash
./build/X86/gem5.opt configs/example/se.py -c quicksort/quicksort --cputype=TimingSimpleCPU ---caches --l2cache --l3cache --l1d_size=4kB --l1i_size=4kB --l2_size=16kB --l3_size=1MB --l3_assoc=16384 --mem-type=NVMainMemory --nvmainconfig=../NVmain/Config/PCM_ISSCC_2012_4GB.config 2>&1 | tee log
```

* Q4:
```bash
./build/X86/gem5.opt configs/example/se.py -c quicksort/quicksort --cputype=TimingSimpleCPU --caches --l2cache --mem-type=NVMainMemory --nvmainconfig=../NVmain/Config/PCM_ISSCC_2012_4GB.config 2>&1 | tee log
```

* Q5:
```bash
./build/X86/gem5.opt configs/example/se.py -c multiply/multiply --cputype=TimingSimpleCPU --caches --l2cache --l3cache --l3_assoc=4 --mem-type=NVMainMemory --nvmainconfig=../NVmain/Config/PCM_ISSCC_2012_4GB.config 2>&1 | tee log
```
