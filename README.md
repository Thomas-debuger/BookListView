# 圖書管理程式 (BookListView)

## 專案簡介
這是一個使用 C# Windows Forms 開發的簡易「圖書管理程式」。此應用程式展示了如何使用 `ListView` 控制項來呈現圖書目錄，並整合了 `ComboBox` 來切換不同的檢視模式（例如：大圖示、詳細資料等）。此外，使用者可以透過雙擊清單中的書籍來模擬借閱流程，系統會跳出確認視窗，並將借出的書籍記錄在側邊的借書清單中。

---

## 功能特色
* **圖書清單展示**：使用 `ListView` 動態載入預設的經典文學書單，包含「書名」、「作者」及「類別」等詳細資訊。
* **多重檢視模式**：透過右上角的下拉式選單 (`ComboBox`)，使用者可即時切換五種不同的資料顯示方式：
  * 大圖示 (Large Icon)
  * 詳細資料 (Details)
  * 小圖示 (Small Icon)
  * 清單 (List)
  * 大圖示加詳細資料 (Tile)
* **模擬借閱系統**：
  * 滑鼠雙擊 `ListView` 中的任一書籍，即可觸發借閱確認對話框。
  * 點擊「是」後，該書籍會自動加入右下方的「借書清單」(`ListBox`) 中。
  * **防呆機制**：系統會自動檢查借書清單，若該書籍已在清單中，則不會重複詢問與加入。

---

## 執行說明

### 1. 開發環境準備
* 請確保已安裝 **Visual Studio**，並包含 **.NET 桌面開發 (Windows Forms)** 工作負載。

### 2. 建立與設定專案
1. 開啟 Visual Studio，建立一個新的 **Windows Forms App (.NET Framework)** 專案，將專案名稱命名為 `BookListView`。
2. 根據截圖設計表單介面，並加入以下控制項（請確保控制項名稱與程式碼一致）：
   * `ListView`：命名為 `lvwBooks`（放置於左側）。
   * `ComboBox`：命名為 `cmbView`（放置於右上角）。
   * `ListBox`：命名為 `lstBorrow`（放置於右下角）。
3. **重要提示（圖片設定）**：
   * 程式碼中使用了 `ImageIndex` 屬性來為書籍綁定圖示。請在表單設計工具中加入 `ImageList` 元件（例如 `imageListLarge` 和 `imageListSmall`）。
   * 將準備好的書籍圖片加入 `ImageList` 中，並將 `lvwBooks` 的 `LargeImageList` 與 `SmallImageList` 屬性分別指定為您建立的 `ImageList` 元件。

### 3. 綁定事件與執行
1. 在表單上按右鍵選擇「檢視程式碼」(View Code)。
2. 將提供的 C# 原始碼貼上並覆蓋專案中的 `Form` 類別內容。
3. 返回設計介面，確保以下事件已正確綁定：
   * `Form` 的 `Load` 事件綁定至 `frmBooks_Load`。
   * `cmbView` 的 `SelectedIndexChanged` 事件綁定至 `cmbView_SelectedIndexChanged`。
   * `lvwBooks` 的 `ItemActivate`（或 `DoubleClick`）事件綁定至 `lvwBooks_ItemActivate`。
4. 按下 `F5` 或點擊「開始」即可編譯並執行程式。

---

## 程式截圖

### 大圖示
<img width="868" height="636" alt="image" src="https://github.com/user-attachments/assets/1e830c9a-7ca5-47da-b381-f782c9ffe193" />

### 詳細資料
<img width="870" height="637" alt="image" src="https://github.com/user-attachments/assets/1d759ef1-fbb7-4226-a8bc-b1f53b2ce890" />

### 小圖示
<img width="872" height="637" alt="image" src="https://github.com/user-attachments/assets/88077a22-4f3c-48a4-951f-0e04d65f2a0c" />

### 清單
<img width="872" height="638" alt="image" src="https://github.com/user-attachments/assets/6dcfb7dd-eaf7-4bed-93a7-39af781a9877" />

### 大圖示加詳細資料
<img width="868" height="635" alt="image" src="https://github.com/user-attachments/assets/2ce5402f-3d7a-4c53-a2f3-991f68242367" />
