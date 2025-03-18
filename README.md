# 自由模組桌遊配套平臺
---

## 目錄

- [簡介](#簡介)
- [主要特色](#主要特色)
- [視覺與動畫效果](#視覺與動畫效果)
- [如何新增自訂模塊](#如何新增自訂模塊)
- [技術棧](#技術棧)
- [安裝與使用](#安裝與使用)
- [貢獻](#貢獻)
- [授權條款](#授權條款)
- [聯繫我們](#聯繫我們)

---

## 簡介

自由模組桌遊配套平臺是一個美麗桌遊配套小工具模塊化網站，目的是利用可適配不同桌遊的模塊化特性讓桌遊玩起來更簡單好玩。
透過此平臺，桌遊玩家可以在遊戲進行中使用網頁工具輕鬆記錄分數、模擬骰子擲出的結果以及運用虛擬計算機進行快速計算或用自由模組做到其他操作，從而提昇遊戲體驗。

---

## 主要特色

- **虛擬骰子模塊**  
  支援自訂骰子數量，玩家可隨時擲骰子，隨機生成點數並計算總和，搭配流暢音效提昇互動樂趣。

- **虛擬計算機模塊**  
  基本運算功能，讓玩家在遊戲中隨時進行數值運算，方便記錄與計算分數。

- **即時分數記錄**  
  提供直觀的分數輸入介面，各科目或遊戲項目均可輕鬆輸入，實時更新數據，助你隨時掌握遊戲狀態。

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
