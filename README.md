
![插圖](https://github.com/user-attachments/assets/76e7bdcf-9d4a-4cd3-bb9c-5bd1f79f7fc9)

# 開源模組化桌遊伴侶
---
所有模塊演示網站: https://andy5533.github.io/Open-Modular-Boardgame-Companion/PLAYGROUND/PLAYGROUND.html

項目介紹3d網站: https://andy5533.github.io/Open-Modular-Boardgame-Companion/PLAYGROUND/PLAYGROUND3d.html
## 目錄

- [簡介](#簡介)
- [主要特色](#主要特色)
- [視覺與動畫效果](#視覺與動畫效果)
- [如何新增自訂卡牌](#如何新增自訂卡牌)
- [如何新增自訂模塊](#如何新增自訂模塊)
- [技術棧](#技術棧)
- [安裝與使用](#安裝與使用)
- [貢獻](#貢獻)
- [授權條款](#授權條款)
- [聯繫我們](#聯繫我們)

---

## 簡介

開源模組化桌遊伴侶是一個美麗桌遊配套小工具模塊化網站，目的是利用可適配不同桌遊的模塊化特性讓桌遊玩起來更簡單好玩。
透過此平臺，桌遊玩家可以在遊戲進行中使用網頁工具輕鬆記錄分數、模擬骰子擲出的結果以及運用虛擬計算機進行快速計算或用自由模組做到其他操作，從而提昇遊戲體驗。

---

## 主要特色

- **虛擬骰子模塊**  
  支援自訂骰子數量，玩家可隨時擲骰子，隨機生成點數並計算總和，搭配流暢音動效提昇互動樂趣。

- **虛擬計算機模塊**  
  基本運算功能，讓玩家在遊戲中隨時進行數值運算，方便記錄與計算分數。

- **科學計算機模塊**  
  進階運算功能，讓玩家在遊戲中隨時進行數值運算，方便記錄與計算分數。

- **虛擬抽撲克牌模塊**  
  支援自訂抽卡數量，玩家可隨時隨機抽撲克牌，搭配流暢音動效提昇互動樂趣。

- **虛擬抽自定義卡牌模塊**  
  開發者可以加入圖片資料夾自定義卡背圖樣以及自定義可抽取卡牌，支援自訂抽卡數量，玩家可隨時隨機抽自定義卡牌，搭配流暢音動效提昇互動樂趣。

- **自由自定義模組化設計**  
  使用者和開發者可以根據實際桌遊需求，自行添加或修改模塊，打造專屬的桌遊配套工具。

---

## 視覺與動畫效果

平臺採用**簡潔細緻**的視覺設計與**好看動效**，具體特點包括：

- **極簡風格**：簡單而不失美感的介面設計，專注於核心功能展示，讓使用者能快速找到所需工具。
- **動感模糊效果**：背景採用精心設計的模糊動畫效果，不僅增添視覺層次，也使整體介面更顯柔和與現代。
- **細緻過渡動畫**：從按鈕懸停到模塊切換，每個細節均有平滑的動畫過渡，提供優質的使用體驗。

---

## 如何新增自訂模塊

平臺支持**自由擴展**，您可以根據桌遊的特殊需求添加自己的模塊，步驟如下：

1. **建立模塊文件**： 
本教學將帶您一步步建立一個與計算機模組類似，具有簡潔美觀、動感過渡和互動效果的自定義模塊。您可以依此模式製作其他功能模塊，並輕鬆整合到您的桌遊配套網站中。

一個自定義模塊通常包含以下幾個部分：
- **模塊容器**：包裹整個模塊，應用一致的背景、圓角和陰影效果。
- **標題與描述**：清晰展示模塊用途，如「計算機」或其他功能名稱。
- **內容區域**：放置按鈕、輸入框或其他互動元素，並運用網格佈局或彈性盒模型達到整齊排版。
- **互動效果**：利用 TailwindCSS 的過渡、懸停（hover）和縮放（scale）效果提昇視覺與操作體驗。

以下是一個與計算機模組類似的 HTML 範例：
```html
<section id="custom-module" class="content-container">
  <div class="flex flex-col items-center p-4 rounded-lg shadow hover:shadow-xl hover:scale-105 hover:bg-gray/40 transition duration-300">
    <h2 class="text-2xl font-bold mb-4">自定義模塊</h2>
    <!-- 模塊內容 -->
    <div class="w-full mb-4">
      <!-- 可根據需求新增表單、按鈕或其他互動元素 -->
      <input type="text" id="custom-input" class="w-full p-2 text-right text-2xl border rounded" placeholder="請輸入數值">
    </div>
    <div class="grid grid-cols-4 gap-2 w-full">
      <!-- 示例按鈕 -->
      <button class="module-btn p-4 bg-blue-500 text-white rounded hover:bg-blue-600 transition" data-value="A">A</button>
      <button class="module-btn p-4 bg-blue-500 text-white rounded hover:bg-blue-600 transition" data-value="B">B</button>
      <button class="module-btn p-4 bg-blue-500 text-white rounded hover:bg-blue-600 transition" data-value="C">C</button>
      <button class="module-btn p-4 bg-orange-500 text-white rounded hover:bg-orange-600 transition" data-value="D">D</button>
      <!-- 您可以根據需要增加更多按鈕或其他控件 -->
    </div>
    <div class="mt-4">
      <button id="module-action" class="px-6 py-3 bg-green-500 text-white rounded hover:bg-green-600 transition transform hover:scale-105">執行操作</button>
    </div>
  </div>
</section>
```
解說
- **容器（`<section>` 與 `div`）**  
  使用 `content-container` 類別包裹模塊，確保背景半透明與模糊效果一致，同時利用 Tailwind 的 `rounded-lg`、`shadow` 等類別增強立體感與動感。
  
- **標題與輸入框**  
  標題 `<h2>` 和輸入框 `<input>` 都採用大字體和明確間距，確保內容易讀。

- **按鈕區域**  
  按鈕採用 `grid grid-cols-4` 排版，每個按鈕均有懸停與過渡效果（`hover:bg-blue-600 transition`），提供直觀的反饋效果。

---
本模塊主要利用 TailwindCSS 的實用類別來達成視覺效果，您只需確保在專案中引入 TailwindCSS CDN 或配置好 TailwindCSS。

### 關鍵類別解釋
- `content-container`：可自定義的容器類別，用來統一模塊背景、邊框與模糊效果（可參考專案 CSS 自訂部分）。
- `rounded-lg`：圓角效果，令模塊邊角柔和。
- `shadow hover:shadow-xl`：基礎陰影與懸停時加強陰影，營造立體感。
- `hover:scale-105 transition duration-300`：懸停時略微放大並過渡平滑，提昇互動體驗。
- `hover:bg-gray/40`：懸停時背景顏色變化，提供視覺反饋。

您可以根據需求調整這些類別參數，例如修改背景顏色或陰影強度，以適應不同模塊的視覺風格。

---

若要為模塊增加功能，可透過 JavaScript 監聽按鈕點擊事件。例如：

```javascript
document.querySelectorAll('.module-btn').forEach(button => {
  button.addEventListener('click', function() {
    const value = this.getAttribute('data-value');
    // 將點擊的按鈕數值顯示到輸入框中或執行其他操作
    document.getElementById('custom-input').value += value;
  });
});

document.getElementById('module-action').addEventListener('click', function() {
  // 執行自定義操作，例如計算結果或提交數據
  const inputVal = document.getElementById('custom-input').value;
  alert('輸入的內容：' + inputVal);
});
```

這段程式碼示範了如何捕捉按鈕點擊事件，並將按鈕所代表的數值或字符加到輸入框中，最終在點擊操作按鈕時觸發一個提醒。

---

整合到您的平臺中

當您製作好一個新的模塊後，請記得：
- 將模塊的 HTML 片段添加到主頁面中（例如在 `<main>` 或其他容器內）。
- 更新導航欄或側邊欄，加入對新模塊的連結，以便使用者能快速切換至該模塊。
- 測試模塊在不同裝置與瀏覽器中的顯示效果，確保響應式設計與互動功能正常。

---

小結

透過本教學，您學會了如何利用 HTML、TailwindCSS 以及 JavaScript 建立一個具備計算機模組視覺效果的自定義模塊。這個模板可以作為參考，幫助您製作更多自由模組，滿足各種桌遊配套需求，打造專屬且美觀的遊戲輔助工具。

2. **引入模塊資源**：  
   將您的模塊文件放置於專案目錄中，並在主頁面中使用 `<script>` 或 `<link>` 標籤引入您的文件。

3. **修改導航**：  
   在網站導航欄中增加對應的鏈接，讓使用者能夠快速切換到您新增的模塊。

4. **整合與測試**：  
   確保您的模塊與現有系統無縫整合，並進行充分測試以驗證各項功能和視覺效果是否正常。

5. **提交貢獻（可選）**：  
   如果您希望分享您的模塊，請提交 Pull Request 至本專案，讓更多桌遊愛好者共同受益。
---
## 如何新增自訂卡片

本專案的「抽卡模塊 (圖片)」允許您使用自訂的圖像作為卡片。請依照以下步驟來新增或替換卡片圖片：

1.  **準備圖片文件夾:**
    *   在您的專案根目錄（與 `index.html` 文件同級）下，確保有一個名為 `cards` 的文件夾。如果不存在，請創建它。

2.  **放置卡背圖片 (可選但建議):**
    *   將您想要用作**所有卡片背面**的圖片命名為 `0.png`，並將其放入 `cards` 文件夾中。
    *   如果省略此文件，卡片背面將顯示為預設的淺灰色背景。

3.  **放置卡面圖片:**
    *   將您想要作為**卡片正面**的圖片放入 `cards` 文件夾中。
    *   **重要：** 這些卡面圖片必須使用**從 1 開始的連續數字**來命名，並使用 `.png` 作為擴展名。例如：`1.png`, `2.png`, `3.png`, ..., 一直到您最後一張卡片的編號。
    *   假設您有 50 張不同的卡面，您的文件夾中就應該有 `1.png`, `2.png`, ..., `50.png` 這些文件。

4.  **更新 JavaScript 代碼:**
    *   打開您的 HTML 文件 (例如 `index.html`)。
    *   在 `<script>` 標籤內，找到標記為 **圖像卡片模塊邏輯** (`Image Card Drawing Logic`) 的 IIFE (Immediately Invoked Function Expression) 區塊。看起來像這樣：`(() => { /* ... 圖像卡片代碼 ... */ })();`
    *   在該區塊內，找到下面這一行代碼：
        ```javascript
        const 最大圖像卡片編號 = 52; // ***** 請設置為您 cards 文件夾中最高的卡片編號 *****
        ```
    *   將數字 `52` **修改為您放入 `cards` 文件夾中的最高卡片編號**。例如，如果您放置了 `1.png` 到 `78.png`，您需要將這行改為：
        ```javascript
        const 最大圖像卡片編號 = 78;
        ```
    *   儲存您的 HTML 文件。

5.  **重新整理網頁:**
    *   在瀏覽器中重新整理 (Refresh/Reload) 您的網頁。現在，「抽卡模塊 (圖片)」應該會使用您新增的圖片，並且知道總共有多少張卡片可供抽取。

**建議與注意事項:**

*   **圖片格式:** 建議使用網頁常用的圖片格式，如 `.png`, `.jpg`/`.jpeg`, `.webp`, 或 `.gif`。如果您的圖片格式不是 `.png`，您需要同時修改 JavaScript 中 `卡片圖片基礎路徑` 相關的代碼來處理不同的擴展名（目前代碼預設為 `.png`）。`.png` 格式支援透明背景。
*   **圖片尺寸與長寬比:** 為了獲得最佳顯示效果，建議所有卡面圖片使用**相同**的長寬比 (Aspect Ratio)，例如標準撲克牌的比例 (約 2.5 : 3.5)。CSS 樣式 (`object-fit: cover;`) 會嘗試覆蓋整個卡片區域，如果圖片比例差異太大，可能會導致部分圖像被裁剪。您可以考慮將所有圖片預先處理成統一尺寸和比例。
*   **文件大小:** 優化您的圖片文件大小有助於加快網頁加載速度。
*   **編號連續性:** 請確保卡面圖片的編號是從 1 開始且連續的，否則程式可能無法正確找到所有圖片。
---

## 技術棧

- **前端技術**：HTML5, CSS3, JavaScript
- **CSS 框架**：TailwindCSS（提供快速且現代化的介面樣式）
- **動畫效果**：利用 CSS 動畫和過渡效果實現細膩動效與模糊背景
- **圖標庫**：Font Awesome（豐富的圖標支持）

---

## 安裝與使用

### 先決條件

- 支援 HTML5 與 CSS3 的現代瀏覽器
- 基本網頁伺服器環境（可使用 VSCode 的 Live Server 等工具）

### 安裝步驟

1. **複製倉庫**
   ```bash
   git clone https://github.com/your-repo/open-modular-boardgame.git
   ```
2. **進入專案目錄**
   ```bash
   cd open-modular-boardgame
   ```
3. **打開 `index.html`**  
   直接用瀏覽器打開或部署至本地伺服器以獲得最佳效果。

---

## 貢獻

我們歡迎所有對此專案有興趣的開發者參與改進與擴展，請按照以下流程提交您的貢獻：

1. **Fork 此倉庫**
2. **創建您的新分支**
   ```bash
   git checkout -b feature/YourModule
   ```
3. **提交修改**
   ```bash
   git commit -am '新增自訂模塊'
   ```
4. **推送分支**
   ```bash
   git push origin feature/YourModule
   ```
5. **發送 Pull Request**

請確保您的代碼符合專案風格並通過所有測試。

---

## 授權條款

本專案採用 **MIT 許可證**，詳情請參見 [LICENSE](LICENSE) 文件。

---

## 聯繫我們

- **Email**: andy55335533@gmail.com
- **GitHub**: https://github.com/Andy5533/A-web-companion-tools-page-for-board-game-

---

自由模組桌遊配套平臺致力於打造一個美觀、易用且功能豐富的桌遊輔助工具，期待您的參與與貢獻，共同推動桌遊數位化新體驗！
