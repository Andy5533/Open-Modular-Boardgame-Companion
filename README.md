# ✨ 開源模組化桌遊伴侶 ✨

![插圖](https://github.com/user-attachments/assets/76e7bdcf-9d4a-4cd3-bb9c-5bd1f79f7fc9)

**一個美觀、易用、可自由擴展的桌遊輔助工具集。**

---

**🚀 立刻體驗:**

*   **所有模塊演示:** [點擊這裡訪問](https://andy5533.github.io/Open-Modular-Boardgame-Companion/PLAYGROUND/PLAYGROUND.html)
*   **項目介紹 (3D):** [點擊這裡探索](https://andy5533.github.io/Open-Modular-Boardgame-Companion/PLAYGROUND/PLAYGROUND3d.html)
*   **GitHub 倉庫:** [點擊這裡查看源碼](https://github.com/Andy5533/Open-Modular-Boardgame-Companion)

---

## 📖 簡介

開源模組化桌遊伴侶旨在透過模塊化特性，簡化並豐富桌遊體驗。它主要包含兩個部分：

*   **🌐 美麗桌遊配套小工具模塊化網站工具集:**
    *   提供網頁端工具，如分數記錄、虛擬骰子、計算機、抽卡器等。
    *   允許玩家和開發者根據特定桌遊需求**自由擴展**，添加自定義模塊。
*   **⌚ Vela小米手環快應用:**
    *   將核心功能（骰子、撲克牌、計算機）帶到手腕上，方便快捷。

## 📜 目錄

*   [簡介](#-簡介)
*   [主要特色](#-主要特色)
*   [視覺與動畫效果](#-視覺與動畫效果)
*   [如何新增自訂卡牌](#-如何新增自訂卡牌)
*   [如何新增自訂模塊](#-如何新增自訂模塊)
*   [技術棧](#-技術棧)
*   [安裝與使用](#-安裝與使用)
*   [貢獻](#-貢獻)
*   [授權條款](#-授權條款)
*   [聯繫我們](#-聯繫我們)

## ✨ 主要特色

### 🌐 網頁端工具集

*   **🎲 虛擬骰子模塊:** 自訂數量，隨機擲骰，計算總和，搭配流暢音效與動畫。
*   **🔢 虛擬計算機模塊:** 提供基本運算，方便遊戲中快速計算分數。
*   **🔬 科學計算機模塊:** 提供進階運算功能，滿足更複雜的計算需求。
*   **🃏 虛擬抽撲克牌模塊:** 自訂抽卡數量，隨機抽取標準撲克牌，視覺效果流暢。
*   **🖼️ 虛擬抽自定義卡牌模塊:** 允許開發者加入自定義圖片作為卡牌（含卡背），隨機抽取，同樣支援音效與動畫。
*   **📊 表格模塊:** 提供一個可自定義內容的基礎表格樣式範例。
*   **🧩 自由自定義模組化設計:** 核心優勢！使用者和開發者可輕鬆添加或修改模塊，打造專屬工具。

### ⌚ Vela小米手環快應用

*   **🎲 虛擬骰子模塊:** 隨時隨地擲骰子，搭配震動反饋。
*   **🃏 虛擬抽撲克牌模塊:** 方便地抽取撲克牌，同樣有震動提示。
*   **🔢 虛擬計算機模塊:** 在手環上進行簡單的數值計算。

## 🎨 視覺與動畫效果

平臺採用**簡潔細緻**的視覺設計與**流暢動效**，帶來愉悅的使用體驗：

*   **✨ 極簡風格:** 介面設計美觀且專注核心功能，易於上手。
*   **💧 動感模糊背景:** 精心設計的背景模糊動畫，增添視覺層次感與現代感。
*   **🎬 細緻過渡動畫:** 從按鈕懸停到模塊切換，交互細節均有平滑動畫，提昇操作體驗。

---

## 🖼️ 如何新增自訂卡牌

本專案的「抽卡模塊 (圖片)」允許您使用自訂的圖像作為卡片。請依照以下步驟來新增或替換卡片圖片：

1.  **📁 準備圖片文件夾:**
    *   在您的專案根目錄（與 `index.html` 文件同級）下，確保有一個名為 `cards` 的文件夾。如果不存在，請創建它。

2.  **🎨 放置卡背圖片 (可選但建議):**
    *   將您想要用作**所有卡片背面**的圖片命名為 `0.png`，並將其放入 `cards` 文件夾中。
    *   如果省略此文件，卡片背面將顯示為預設的淺灰色背景。

3.  **🖼️ 放置卡面圖片:**
    *   將您想要作為**卡片正面**的圖片放入 `cards` 文件夾中。
    *   **⚠️ 重要：** 這些卡面圖片必須使用**從 1 開始的連續數字**來命名，並使用 `.png` 作為擴展名。例如：`1.png`, `2.png`, `3.png`, ..., 一直到您最後一張卡片的編號。
    *   假設您有 50 張不同的卡面，您的文件夾中就應該有 `1.png`, `2.png`, ..., `50.png` 這些文件。

4.  **⚙️ 更新 JavaScript 代碼:**
    *   打開您的 HTML 文件 (例如 `index.html`)。
    *   在 `<script>` 標籤內，找到標記為 **圖像卡片模塊邏輯** 的 IIFE (Immediately Invoked Function Expression) 區塊。
    *   在該區塊內，找到下面這一行代碼：
        ```javascript
        const 最大圖像卡片編號 = 52; // ***** 請設置為您 cards 文件夾中最高的卡片編號 *****
        ```
    *   將數字 `52` **修改為您放入 `cards` 文件夾中的最高卡片編號**。例如，如果您放置了 `1.png` 到 `78.png`，您需要將這行改為：
        ```javascript
        const 最大圖像卡片編號 = 78;
        ```
    *   儲存您的 HTML 文件。

5.  **🔄 重新整理網頁:**
    *   在瀏覽器中重新整理 (Refresh/Reload) 您的網頁。現在，「抽卡模塊 (圖片)」應該會使用您新增的圖片，並且知道總共有多少張卡片可供抽取。

**💡 建議與注意事項:**

*   **圖片格式:** 建議使用網頁常用的圖片格式 (`.png`, `.jpg`/`.jpeg`, `.webp`, `.gif`)。`.png` 支持透明背景。若使用其他格式，需修改 JS 中處理擴展名的部分。
*   **圖片尺寸與長寬比:** 建議所有卡面圖片使用**相同**的長寬比 (Aspect Ratio) 以獲得最佳顯示效果（避免裁剪）。
*   **文件大小:** 優化圖片大小有助於加快網頁加載速度。
*   **編號連續性:** 確保卡面圖片編號從 1 開始且連續。

---

## 🧩 如何新增自訂模塊

本平臺支持**自由擴展**，您可以根據桌遊的特殊需求添加自己的模塊。以下是詳細步驟：

### 1. 🏗️ 建立模塊結構 (HTML)

本教學將引導您建立一個自定義模塊，參考現有模塊（如快記、骰子、計算機等）的結構與風格，實現簡潔美觀、具備互動效果的設計。

一個自定義模塊通常包含以下幾個核心部分：

*   **📦 模塊容器 (`<section>`)**:
    *   使用唯一的 `id` (例如 `id="自定義模塊"`)。
    *   應用 `內容容器` class 來獲得統一的視覺風格 (背景、模糊、圓角、陰影)。
*   **🏷️ 標題 (`<h2>`)**:
    *   清晰標示模塊名稱和用途 (例如 `<h2 id="自定義標題">...</h2>`)。
*   **🧱 內容區域 (`<div>`)**:
    *   放置核心元素 (輸入框、按鈕、顯示區等)。
    *   利用 **TailwindCSS** 的網格 (`grid`) 或彈性盒 (`flex`) 進行佈局。
*   **✨ 互動元素與視覺反饋**:
    *   為按鈕、輸入框等添加 TailwindCSS 的過渡 (`transition`)、懸停 (`hover:`)、縮放 (`scale`) 等效果。
    *   可複用現有樣式類 (如 `計算機按鈕`) 或創建新樣式。

**範例 HTML (模仿簡易計算機結構):**

```html
<!-- 自定義模塊範例 -->
<section id="自定義模塊" aria-labelledby="自定義標題" class="內容容器">
  <div class="flex flex-col items-center p-4 rounded-lg max-w-md mx-auto">
    <h2 id="自定義標題" class="text-2xl font-bold mb-4">我的自定義模塊</h2>

    <!-- 顯示區域 -->
    <div class="w-full mb-4">
      <input type="text" id="自定義顯示" aria-label="自定義模塊顯示屏" class="w-full p-3 text-right text-3xl border rounded bg-gray-100 text-gray-800" value="初始值" readonly>
    </div>

    <!-- 按鈕網格 -->
    <div class="grid grid-cols-4 gap-2 w-full">
      <!-- 示例按鈕 -->
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-數字" data-action="action1">動作1</button>
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-數字" data-action="action2">動作2</button>
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-運算符" data-action="action3">動作3</button>
      <button class="計算機按鈕 p-4 text-xl text-white rounded 按鈕-運算符" data-action="action4">動作4</button>
      <!-- 可根據需要增加更多按鈕 -->
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

*   **容器 (`<section>` & `div`)**: 使用 `id` 標識，`內容容器` class 統一風格，Tailwind 類控制內部佈局。
*   **標題與顯示框**: 清晰標示，使用 `<input readonly>` 作為顯示區。
*   **按鈕區域**: 使用 `grid` 佈局，複用 `計算機按鈕` 相關樣式，`data-action` 用於 JS 識別功能。

---

**🎨 關鍵樣式類解釋 (TailwindCSS + 自訂 CSS):**

*   **`內容容器` (自訂 CSS)**: 定義於 `<style>`，提供基礎外觀 (半透明背景、模糊、圓角、陰影)。
*   **Tailwind 佈局**: `flex`, `grid`, `items-center`, `gap-*`, `space-*` 等。
*   **Tailwind 視覺**: `p-*`, `m-*`, `w-*`, `h-*`, `bg-*`, `text-*`, `font-*`, `rounded-*`, `shadow-*`。
*   **Tailwind 互動**: `hover:*`, `transition`, `duration-*`, `scale-*`。
*   **自訂按鈕樣式 (CSS)**: 如 `計算機按鈕`, `按鈕-數字` 等，定義於 `<style>`，確保風格統一。

您可以調整 Tailwind 類或修改自訂 CSS 來打造模塊風格。

---

### 2. ⚡ 添加模塊功能 (JavaScript)

使用 **立即調用函數表達式 (IIFE)** 封裝每個模塊的邏輯，避免全局汙染。

**範例 JavaScript (IIFE 結構):**

```javascript
// --- 自定義模塊邏輯 ---
(() => {
  // 1. 獲取模塊根元素，檢查是否存在
  const 區塊 = document.getElementById('自定義模塊');
  if (!區塊) {
    console.warn('找不到 ID 為 "自定義模塊" 的區塊。');
    return;
  }

  // 2. 在模塊內部查找元素
  const 顯示區 = 區塊.querySelector('#自定義顯示');
  const 所有功能按鈕 = 區塊.querySelectorAll('.計算機按鈕[data-action]');
  const 重置按鈕 = 區塊.querySelector('#自定義清除按鈕');

  // 3. 檢查必要元素是否存在
  if (!顯示區 || !重置按鈕) {
      console.error('自定義模塊缺少必要的元素。');
      return;
  }

  // 4. 為功能按鈕添加事件監聽器
  所有功能按鈕.forEach(button => {
    button.addEventListener('click', function() {
      const action = this.getAttribute('data-action'); // 獲取動作標識
      // 根據 action 執行不同操作...
      顯示區.value = `執行了: ${action}`;
      console.log(`自定義模塊: 按鈕 ${action} 被點擊`);
    });
  });

  // 5. 為重置按鈕添加事件監聽器
  重置按鈕.addEventListener('click', function() {
    顯示區.value = '初始值'; // 重置顯示
    console.log('自定義模塊: 已重置');
    // 重置其他狀態...
  });

  // 6. 模塊初始化代碼 (如果需要)
  console.log('自定義模塊已初始化。');

})(); // IIFE 結束並立即執行
```

**解說:**

1.  **IIFE 封裝**: `(() => { ... })();` 創建獨立作用域。
2.  **獲取根元素**: `getElementById` + 檢查。
3.  **內部元素查詢**: `區塊.querySelector/All()` 更安全。
4.  **事件監聽**: 為按鈕綁定 `click` 事件。
5.  **功能邏輯**: 根據 `data-action` 執行操作。
6.  **初始化**: 可在此處執行模塊加載時的設置。

### 3. 🔗 整合到您的平臺中

1.  **添加 HTML**: 將 `<section>...</section>` 複製到主 HTML 文件的 `<main>` 或其他容器內。
2.  **添加 JavaScript**:
    *   **推薦**: 將 JS IIFE 代碼塊添加到現有 `<script>` 內的 `DOMContentLoaded` 監聽器中。
    *   **或**: 保存為獨立 `.js` 文件，用 `<script src="..." defer></script>` 引入。
3.  **更新導航**:
    *   在**桌面導航** (`hidden md:block` 內) 添加鏈接:
        ```html
        <a href="#自定義模塊" class="nav-link-style">自定義模塊</a>
        ```
        *(請替換 `nav-link-style` 為您導航鏈接的實際 Tailwind 類)*
    *   在**行動選單** (`id="行動選單"`) 添加鏈接:
        ```html
        <a href="#自定義模塊" class="mobile-nav-link-style">自定義模塊</a>
        ```
        *(請替換 `mobile-nav-link-style` 為行動選單鏈接的實際 Tailwind 類)*
    *   確保 `href="#自定義模塊"` 與 `<section>` 的 `id` 匹配。

### 4. 🧪 整合與測試

*   在瀏覽器中打開網頁。
*   檢查樣式和佈局。
*   測試導航鏈接。
*   測試所有互動功能，檢查控制臺有無錯誤。
*   進行響應式測試 (不同熒幕尺寸)。

### 5. 🤝 提交貢獻 (可選)

*   整理好您的代碼 (HTML, CSS, JS)。
*   訪問項目 GitHub 倉庫。
*   創建 Pull Request (PR)，詳細說明您的模塊。

**小結**

遵循此模式，您可以輕鬆創建、整合和分享功能豐富、風格統一的自定義模塊，擴展此桌遊伴侶平臺的功能。

---

## 🛠️ 技術棧

*   **前端基礎**: HTML5, CSS3, JavaScript (ES6+)
*   **CSS 框架**: **TailwindCSS v3** - 用於快速構建現代化界面。
*   **動畫效果**: CSS Animations & Transitions - 實現流暢動效與背景模糊。
*   **圖標庫**: **Font Awesome 6** - 提供豐富的圖標資源。
*   **打字效果**: Typed.js (用於導航欄標題)。

## 🚀 安裝與使用

### ✅ 先決條件

*   現代網頁瀏覽器 (Chrome, Firefox, Edge, Safari 等)。
*   (可選) 本地開發伺服器 (如 VS Code 的 Live Server 擴展) 以避免某些瀏覽器本地文件限制。

### ⚙️ 安裝步驟

1.  **克隆倉庫:**
    ```bash
    git clone https://github.com/Andy5533/Open-Modular-Boardgame-Companion.git
    ```
2.  **進入項目目錄:**
    ```bash
    cd Open-Modular-Boardgame-Companion
    ```
3.  **打開 `PLAYGROUND/PLAYGROUND.html`:**
    *   直接在瀏覽器中打開此文件。
    *   或通過本地開發伺服器運行。

## 🤝 貢獻

歡迎所有形式的貢獻！如果您想參與改進：

1.  **Fork** 本倉庫。
2.  創建您的特性分支 (`git checkout -b feature/AmazingFeature`)。
3.  提交您的更改 (`git commit -m 'Add some AmazingFeature'`)。
4.  推送至分支 (`git push origin feature/AmazingFeature`)。
5.  打開一個 **Pull Request**。

請確保您的代碼風格與項目一致，並提供清晰的 PR 描述。

---

## 📄 授權條款

本項目採用 **MIT 許可證** 授權。詳情請參見 [LICENSE](LICENSE) 文件 (如果您的倉庫根目錄有此文件的話，否則可以移除此鏈接或說明)。

---

## 📞 聯繫我們

*   **Email**: [andy55335533@gmail.com](mailto:andy55335533@gmail.com)
*   **GitHub Issues**: [報告問題或建議](https://github.com/Andy5533/Open-Modular-Boardgame-Companion/issues)

---

**感謝您使用開源模組化桌遊伴侶！期待您的參與與貢獻，共同打造更好的桌遊數位化體驗！**
