# linux目錄結構
|目錄名稱|功能|
| ----| -----|
|  |  |
|bin   | 系統的一些重要執行檔    Kill、cp、df|
|boot   | 系統開機的一些載入檔  |  　
|cdrom  |  光碟機裡的資料被掛上來的地方|    　
|dosc  |  開機時把dos檔案系統掛上來的地方 |   　
|etc   | 系統設定檔  |  　
|home    |使用者的自家目錄所在、ftp server  |  　
|lib |   基本函數庫|    　
|Lost+found   | 系統檢查結果 |   　
|mnt   | 可以掛上其它檔案系統  |  　
|proc   | 整個系統運作資訊 |   　
|root  |  系統管理者的自家目錄所在 |   　
|sbin   | 一些設定的可執行程式、設定網路|    　
|tmp   | 雜七雜八的東西 |   　
|usr   | 應用程式    X-window|
|var    |記載著各種系統上的變數的地方   | 　
|vmlinuz    |系統核心檔案 |   　

# /proc 下的檔案介紹：
more cpuinfo：顯示有關cpu的訊息
more devices：區塊設備、字元設備
more filesystems：目前核心技援的檔案系統
more dma：直接記憶體存取
more interrupts：中斷向量值、中斷次數
more ioports：系統中每個設備的輸出／輸入埠的位址範圍
more meminfo：記憶體分配狀態
more pci：顯示PCI介面訊息
