
![插圖](https://github.com/user-attachments/assets/76e7bdcf-9d4a-4cd3-bb9c-5bd1f79f7fc9)

# 開源模組化桌遊伴侶

所有模塊演示網站: https://andy5533.github.io/Open-Modular-Boardgame-Companion/PLAYGROUND/PLAYGROUND.html

項目介紹3d網站: https://andy5533.github.io/Open-Modular-Boardgame-Companion/PLAYGROUND/PLAYGROUND3d.html


## 簡介

開源模組化桌遊伴侶分為兩個部分

- 美麗桌遊配套小工具模塊化網站工具集
- Vela小米手環快應用
  
目的是利用可適配不同桌遊的模塊化特性讓桌遊玩起來更簡單好玩。
透過此平臺，桌遊玩家可以在遊戲進行中使用網頁工具輕鬆記錄分數、模擬骰子擲出的結果以及運用虛擬計算機進行快速計算或用自由模組做到其他操作，從而提昇遊戲體驗。
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

## 主要特色

網頁端工具集

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

- **表格模塊**  
  可自定義內容的表格樣式。

- **自由自定義模組化設計**  
  使用者和開發者可以根據實際桌遊需求，自行添加或修改模塊，打造專屬的桌遊配套工具。

Vela小米手環快應用

- **虛擬骰子模塊**  
  玩家可隨時擲骰子，隨機生成點數，搭配震動等效果提昇互動樂趣。
  
- **虛擬抽撲克牌模塊**  
  玩家可隨時隨機抽撲克牌，搭配震動等效果提昇互動樂趣。

- **虛擬計算機模塊**  
  方便運算功能，讓玩家在遊戲中隨時進行數值運算，方便記錄與計算分數。
---

## 視覺與動畫效果

平臺採用**簡潔細緻**的視覺設計與**好看動效**，具體特點包括：

- **極簡風格**：簡單而不失美感的介面設計，專注於核心功能展示，讓使用者能快速找到所需工具。
- **動感模糊效果**：背景採用精心設計的模糊動畫效果，不僅增添視覺層次，也使整體介面更顯柔和與現代。
- **細緻過渡動畫**：從按鈕懸停到模塊切換，每個細節均有平滑的動畫過渡，提供優質的使用體驗。

---

好的，這是一份根據您提供的新代碼重寫的「如何新增自訂模塊」說明文件，保持了原有的結構和風格：

---

## 如何新增自訂模塊

本平臺支持**自由擴展**，您可以根據桌遊的特殊需求添加自己的模塊。以下是詳細步驟：

### 1. 建立模塊結構 (HTML)

本教學將引導您建立一個自定義模塊，參考現有模塊（如快記、骰子、計算機等）的結構與風格，實現簡潔美觀、具備互動效果的設計。您可以依此模式製作其他功能模塊，並輕鬆整合到您的桌遊配套網站中。

一個自定義模塊通常包含以下幾個核心部分：

*   **模塊容器 (`<section>`)**：
    *   使用唯一的 `id` (例如 `id="自定義模塊"`）以便導航和 JavaScript 定位。
    *   應用 `內容容器` class 來獲得統一的半透明背景、模糊效果、圓角和陰影。這是維持整體視覺風格一致性的關鍵。
*   **標題 (`<h2>`)**：
    *   清晰標示模塊的名稱和用途，例如 `<h2 id="自定義標題">自定義模塊標題</h2>`。建議也為標題加上 `id` 以增強可訪問性（例如用於 `aria-labelledby`）。
*   **內容區域 (`<div>`)**：
    *   放置模塊的核心元素，如輸入框、按鈕、顯示區域等。
    *   利用 TailwindCSS 的網格佈局 (`grid`, `grid-cols-*`, `gap-*`) 或彈性盒模型 (`flex`, `flex-col`, `items-center`, `justify-center`, `space-x-*`, `space-y-*`) 來實現整齊、響應式的排版。
*   **互動元素與視覺反饋**：
    *   為按鈕 (`<button>`)、輸入框 (`<input>`) 等元素添加 TailwindCSS 的過渡 (`transition`, `duration-*`)、懸停 (`hover:`)、縮放 (`hover:scale-*`) 和背景變化 (`hover:bg-*`) 效果，以提昇用戶體驗。
    *   參考現有模塊的按鈕樣式 class（如 `計算機按鈕`, `按鈕-數字`, `按鈕-操作` 等）或創建您自己的樣式。

以下是一個參照 **簡易計算機模塊** 結構的 HTML 範例：

```html
<!-- 自定義模塊範例 (模仿簡易計算機結構) -->
<section id="自定義模塊" aria-labelledby="自定義標題" class="內容容器">
  <div class="flex flex-col items-center p-4 rounded-lg max-w-md mx-auto">
    <h2 id="自定義標題" class="text-2xl font-bold mb-4">我的自定義模塊</h2>

    <!-- 顯示區域 -->
    <div class="w-full mb-4">
      <input type="text" id="自定義顯示" aria-label="自定義模塊顯示屏" class="w-full p-3 text-right text-3xl border rounded bg-gray-100 text-gray-800" value="初始值" readonly>
    </div>

    <!-- 按鈕網格 -->
    <div class="grid grid-cols-4 gap-2 w-full">
      <!-- 示例按鈕 - 可自定義樣式與功能 -->
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-數字" data-action="action1">動作1</button>
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-數字" data-action="action2">動作2</button>
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-運算符" data-action="action3">動作3</button>
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-運算符" data-action="action4">動作4</button>
      <!-- 您可以根據需要增加更多按鈕或其他控件 -->
    </div>

    <!-- 其他操作按鈕 -->
    <div class="mt-4 w-full">
      <button id="自定義清除按鈕" class="計算機按鈕 w-full px-6 py-3 text-white rounded 按鈕-操作 transform hover:scale-105">
        <i class="fas fa-sync-alt mr-2" aria-hidden="true"></i>重置模塊
      </button>
    </div>
  </div>
</section>
```

**解說:**

*   **容器 (`<section>` 與 `div`)**:
    *   `id="自定義模塊"` 提供唯一標識符。
    *   `class="內容容器"` 應用了在 `<style>` 區塊中定義的基礎樣式（背景、模糊、圓角、陰影）。
    *   內部的 `div` 使用 `flex`, `items-center`, `max-w-md`, `mx-auto` 等 Tailwind 類來控製佈局和最大寬度。
*   **標題與顯示框**:
    *   `<h2>` 提供清晰標題。
    *   `<input readonly>` 作為顯示區域，使用 Tailwind 設置樣式。
*   **按鈕區域**:
    *   `grid grid-cols-4 gap-2` 創建了一個四列網格佈局。
    *   按鈕使用了現有的計算機按鈕樣式類 (`計算機按鈕`, `按鈕-數字`, `按鈕-運算符`, `按鈕-操作`) 以保持風格一致，並包含 `hover:` 效果和 `transition`。您可以創建自己的按鈕樣式。
    *   `data-action="..."` 屬性可以用於 JavaScript 中識別按鈕的具體功能。

---

**關鍵樣式類解釋 (TailwindCSS + 自訂 CSS):**

*   **`內容容器` (自訂 CSS)**:
    *   定義在 `<style>` 區塊中，負責提供模塊的基礎外觀：半透明背景 (`background-color: rgba(255, 255, 255, 0.55)`), 背景模糊 (`backdrop-filter: blur(12px)`), 圓角 (`border-radius: 1rem`), 和陰影 (`box-shadow: 0 6px 12px rgba(0, 0, 0, 0.08)`).
*   **Tailwind 佈局**: `flex`, `grid`, `items-center`, `justify-center`, `gap-*`, `space-x-*`, `space-y-*` 等用於排列元素。
*   **Tailwind 視覺**: `p-*` (內邊距), `m-*` (外邊距), `w-*`/`h-*` (寬高), `bg-*` (背景色), `text-*` (文字顏色/大小), `font-*` (字體), `rounded-*` (圓角), `shadow-*` (陰影)。
*   **Tailwind 互動**: `hover:bg-*`, `hover:scale-*`, `hover:shadow-*`, `transition`, `duration-*` 提供視覺反饋和動畫。
*   **自訂按鈕樣式 (CSS)**: 如 `計算機按鈕`, `按鈕-數字`, `按鈕-運算符`, `按鈕-操作`, `按鈕-等於` 等，這些類在 `<style>` 中定義了特定的背景色和懸停效果，確保了按鈕風格的統一性。

您可以根據需求調整 Tailwind 類或修改 `<style>` 中的自訂 CSS，以創造獨特的模塊風格。

---

### 2. 添加模塊功能 (JavaScript)

為了讓模塊能夠響應使用者操作，需要編寫 JavaScript 代碼。**最佳實踐是將每個模塊的邏輯封裝在一個獨立的範圍內**，以避免變數衝突和提高代碼可維護性。我們使用 **立即調用函數表達式 (IIFE)** 來達成這個目的。

以下是為上述 HTML 範例添加基本功能的 JavaScript 示例，採用 IIFE 結構：

```javascript
// --- 自定義模塊邏輯 ---
(() => {
  // 首先，檢查模塊的容器元素是否存在
  const 區塊 = document.getElementById('自定義模塊');
  if (!區塊) {
    // 如果找不到該模塊的 section，則直接返回，不執行後續代碼
    console.warn('找不到 ID 為 "自定義模塊" 的區塊，腳本未執行。');
    return;
  }

  // 在模塊內部查找需要的元素
  const 顯示區 = 區塊.querySelector('#自定義顯示');
  const 所有功能按鈕 = 區塊.querySelectorAll('.計算機按鈕[data-action]'); // 選擇帶 data-action 的按鈕
  const 重置按鈕 = 區塊.querySelector('#自定義清除按鈕');

  // 檢查是否成功獲取到必要元素
  if (!顯示區 || !重置按鈕) {
      console.error('自定義模塊缺少必要的元素 (顯示區 或 重置按鈕)。');
      return;
  }

  // 為功能按鈕添加事件監聽器
  所有功能按鈕.forEach(button => {
    button.addEventListener('click', function() {
      const action = this.getAttribute('data-action'); // 獲取按鈕的 data-action 值

      // 根據 action 執行不同操作
      if (action === 'action1') {
        顯示區.value = '執行了動作 1';
      } else if (action === 'action2') {
        顯示區.value = '執行了動作 2';
      } else {
        顯示區.value = `執行了動作: ${action}`;
      }
      // 您可以在這裡添加更複雜的邏輯
      console.log(`自定義模塊: 按鈕 ${action} 被點擊`);
    });
  });

  // 為重置按鈕添加事件監聽器
  重置按鈕.addEventListener('click', function() {
    顯示區.value = '初始值'; // 重置顯示區內容
    console.log('自定義模塊: 已重置');
    // 可能還需要重置其他狀態變量
  });

  // 可以在這裡添加模塊初始化時需要執行的代碼
  console.log('自定義模塊已成功初始化。');

})(); // IIFE 結束並立即執行
```

**解說:**

1.  **IIFE 封裝**: `(() => { ... })();` 創建了一個獨立的作用域。模塊內部定義的變數（如 `區塊`, `顯示區`）不會洩漏到全局範圍。
2.  **獲取模塊根元素**: `const 區塊 = document.getElementById('自定義模塊');` 首先獲取模塊的 `<section>` 元素。添加 `if (!區塊) return;` 是一個好習慣，防止在 HTML 結構不存在時腳本出錯。
3.  **內部元素查詢**: 使用 `區塊.querySelector()` 和 `區塊.querySelectorAll()` 在**模塊內部**查找元素。這比使用全局的 `document.getElementById()` 或 `document.querySelectorAll()` 更安全、更精確。
4.  **事件監聽**: 為按鈕添加 `click` 事件監聽器。回調函數中 `this` 指向被點擊的按鈕。
5.  **功能邏輯**: 根據按鈕的 `data-action` 屬性執行不同的操作，並更新顯示區的值。
6.  **初始化**: IIFE 結尾處可以放置模塊加載時需要執行的初始化代碼。

---

### 3. 整合到您的平臺中

當您完成新模塊的 HTML 結構和 JavaScript 功能後，請執行以下步驟：

1.  **添加 HTML**: 將您創建的 `<section id="自定義模塊">...</section>` HTML 片段複製到主 HTML 文件（例如 `index.html`）的 `<main>` 標籤或其他合適的容器內，與其他模塊並列。
2.  **添加 JavaScript**:
    *   **方式一 (推薦)**: 將您的 JavaScript IIFE `(() => { ... })();` 代碼塊添加到現有 `<script>` 標籤內的 `DOMContentLoaded` 事件監聽器中，與其他模塊的 IIFE 並列。這樣可以確保所有模塊的 JS 在 DOM 加載完成後執行。
    *   **方式二**: 如果您的 JS 代碼較複雜，可以將其保存為一個獨立的 `.js` 文件（例如 `custom-module.js`），然後在主 HTML 文件底部使用 `<script src="custom-module.js" defer></script>` 引入 (`defer` 屬性確保在 HTML 解析完成後執行)。
3.  **更新導航**:
    *   在**桌面導航欄** (class 包含 `hidden md:block` 的 `div`) 中，添加一個指向新模塊的鏈接：
        ```html
        <a href="#自定義模塊" class="text-gray-700 hover:text-blue-800 hover:bg-blue-100 px-3 py-2 rounded-md text-sm font-medium transition transform hover:scale-105 whitespace-nowrap">自定義模塊</a>
        ```
    *   在**行動選單** (`id="行動選單"`) 中，也添加相應的鏈接：
        ```html
        <a href="#自定義模塊" class="text-gray-700 hover:bg-blue-100 block px-3 py-2 rounded-md text-base font-medium">自定義模塊</a>
        ```
    *   確保 `href` 屬性值（例如 `#自定義模塊`）與您模塊 `<section>` 的 `id` 一致。

---

### 4. 整合與測試

*   在瀏覽器中打開您的網頁。
*   檢查新模塊是否正確顯示，樣式是否與其他模塊協調。
*   點擊導航欄中的鏈接，確認頁面能平滑滾動到您的新模塊。
*   測試所有互動元素（按鈕、輸入框等），確保功能符合預期，沒有 JavaScript 錯誤（打開瀏覽器開發者工具的控製臺查看）。
*   在不同大小的熒幕（或使用瀏覽器的響應式設計模式）上測試，確保模塊佈局在桌面和移動設備上都能正常顯示。

---

### 5. 提交貢獻 (可選)

如果您認為您的自定義模塊對其他桌遊愛好者也有幫助，並且希望分享它：

*   請將您的代碼（包括 HTML、可能的 CSS 修改、JavaScript IIFE）整理好。
*   訪問項目的 GitHub 倉庫。
*   創建一個 Pull Request (PR)，詳細說明您的模塊功能和添加的代碼。
*   項目維護者會審核您的貢獻，如果合適，會將其合併到主項目中。

---

**小結**

通過本教學，您學習了如何遵循現有項目的模式，利用 HTML、TailwindCSS、自訂 CSS 以及封裝在 IIFE 中的 JavaScript，來創建一個結構清晰、風格統一且功能獨立的自定義模塊。您可以基於提供的範例和現有模塊的源代碼，開發出更多滿足特定桌遊需求的輔助工具，豐富這個多功能桌遊伴侶平臺。
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
- **GitHub**: https://github.com/Andy5533/Open-Modular-Boardgame-Companion

---

自由模組桌遊配套平臺致力於打造一個美觀、易用且功能豐富的桌遊輔助工具，期待您的參與與貢獻，共同推動桌遊數位化新體驗！
