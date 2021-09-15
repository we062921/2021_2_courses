# linux目錄結構(directory structure)

- 檔案系統階層標準(Filesystem Hierarchy Standard，FHS)定義了Linux作業系統中的主要目錄及目錄內容。
- FHS由Linux基金會維護。 目前版本為3.0版，於2015年發布
- [Filesystem Hierarchy Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard)

|目錄名稱|功能|
| ----| -----|
|/	  | 第一階層 的根、 整個檔案系統階層的根目錄 |
|bin   | 系統的一些重要執行檔    Kill、cp、df|
|boot   | 系統開機的一些載入檔  |  　
|cdrom  |  光碟機裡的資料被掛上來的地方|    　
|dosc  |  開機時把dos檔案系統掛上來的地方 |   　
|etc   | 系統設定檔  |  　
|home    |使用者的自家目錄所在、ftp server  |  　
|lib |   基本函數庫 /bin/ 和 /sbin/中二進位檔案必要的庫檔案|    　
|Lost+found   | 系統檢查結果 |   　
|mnt   | 可以掛上其它檔案系統  |  　
|proc   | 整個系統運作資訊 |   　
|root  |  系統管理者的自家目錄所在 |   　
|sbin   | 一些設定的可執行程式、設定網路 必要的系統二進位檔案，例如： init、 ip、 mount|    　
|tmp   | 雜七雜八的東西 |   　
|usr   | 應用程式    X-window|
|var    |記載著各種系統上的變數的地方 變數檔案——在正常執行的系統中其內容不斷變化的檔案，如紀錄檔，離線檔案和臨時電子郵件檔案   | 　
|vmlinuz    |系統核心檔案 |   　

# /proc 下的檔案介紹：
- cd /proc 再執行底下指令
  - more cpuinfo：顯示有關cpu的訊息
  - more devices：區塊設備、字元設備
  - more filesystems：目前核心技援的檔案系統
  - more dma：直接記憶體存取
  - more interrupts：中斷向量值、中斷次數
  - more ioports：系統中每個設備的輸出／輸入埠的位址範圍
  - more meminfo：記憶體分配狀態
  - more pci：顯示PCI介面訊息
