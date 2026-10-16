https://www.youtube.com/watch?v=T1OtRZj3IqI
製作流程
1. 專案建立與視覺設定
建立專案： 在 Unity Hub 中選擇「2D Core」模板建立全新的 2D 遊戲專案。

匯入素材： 將準備好的輪盤圖片與背景圖片拖曳至專案的 Assets 資料夾，再將其拉入左側的 Hierarchy 視窗建立 Sprite 物件。

修正圖層遮擋問題： 發現輪盤被白色方形背景遮擋。點選輪盤物件，在 Inspector 視窗中找到 Sprite Renderer 元件的 Additional Settings，將 Order in Layer 數值調高（如設為 1 或以上），確保輪盤顯示於最上層。
2. 音效系統建置
加入音效元件： 在輪盤物件上點擊 Add Component 加入 Audio Source 元件。

匯入音效檔： 將輪盤旋轉的音效檔案拖曳至 Audio Source 第一個屬性 AudioClip 的欄位中。

修正提早播放問題： 為了確保音效只有在玩家按下按鍵時才播放，將 Audio Source 中的 Play On Awake（喚醒時播放） 選項取消勾選。
3. 程式邏輯與輸入設定
撰寫控制腳本： 建立名為 RouletteController 的 C# 腳本並掛載至輪盤物件。腳本內部實作了：

按下「空白鍵」：觸發音效播放（spinAudio.Play()）並使輪盤加速旋轉。

按下「S 鍵」：使輪盤逐漸減速直到完全停止。
