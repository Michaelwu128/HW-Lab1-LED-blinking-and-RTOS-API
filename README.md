## Features (功能說明)
1. **Task_1 (LED 控制與長短按偵測)**:
   * 透過 GPIO 雙邊緣觸發中斷偵測 USER Button。
   * **短按 (< 1秒)**: LED 以 1Hz 頻率閃爍 5 秒。
   * **長按 (> 1秒)**: LED 以 10Hz 頻率快速閃爍 5 秒。
   * 實作狀態機防彈跳邏輯，並使用 **Queue** 將按鍵訊息傳遞給 Task_1。
   
2. **Task_2 (Timer 自動閃爍)**:
   * 每 10 秒由 TIM6 觸發一次 Semaphore 喚醒 Task_2。
   * 喚醒後 LED 以 10Hz 頻率閃爍 2 秒。

3. **Mutex 資源保護**: 
   * 實作 Mutex_LED，確保 Task_1 與 Task_2 在控制同一個 LED 時不會發生資源搶奪與閃爍干擾。

## Hardware Requirement
* STM32L475VGT6 (B-L475E-IOT01A 開發板)
