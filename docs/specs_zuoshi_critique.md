# 🏗️ 琢石橡塑官網原型設計審查與優化規格書 (specs_zuoshi_critique)

本規格書由 **AntiGravity (AG)** 撰寫，旨在方針性地指出目前「琢石橡塑官網原型」所面臨的「AI Slop (AI 罐頭感) / 版面生硬 / 行業氣質不符」問題，並提供具體的高階優化規格與代碼修改指引，供後續執行端進行實作。

---

## 🔍 現有網站設計審查 (Critique)

目前客戶反饋「網站看起來像 AI 做的、版面怪怪的」，經 AG 深度審查，歸納出以下 5 大核心視覺與功能硬傷：

### 1. 視覺溫度偏差：SaaS 罐頭感 vs. 實體工業氣質
- **問題**：現行配色採用高亮冷灰底色搭配翠綠色（Accent: `oklch(58% 0.16 145)` / Bg: `oklch(98% 0.005 250)`）。這種強烈的「冷色調 + 亮霓虹綠」是標準的 **2024年 Web3 / AI SaaS 罐頭範本配色**。
- **影響**：與一家實體「橡塑化學助劑研發與製造廠」所需的「穩重、嚴謹、工業級互信、高分子科學」調性完全背道而馳。給人一種「虛擬網路公司」的廉價感與不安全感。
- **改進規格**：配色應過渡為 **「穩重石墨灰/高質感深藍 + 溫潤赤土橙/微透琥珀金」**，傳達高分子材料在高溫硫化、擠出成型時的工業美學與可靠度。

### 2. 致命 AI 痕跡：Placeholder Slop (佔位符噪音)
- **問題**：產品目錄頁（`ProductsPage`）的產品圖片區塊直接使用灰色區塊，並居中寫著生硬的大寫 **"PRODUCT IMAGE"**。
- **影響**：這是 AI 生成網頁的「經典簽名特徵」，直接向客戶暴露了「這是個未完成的 AI 草稿」，極度削弱專業感。
- **改進規格**：嚴格執行花叔「反 AI Slop 清單」的「Placeholder > 爛實現」原則。使用高品質的化學材料實景圖、實驗分子結構微透背景，或是完全乾淨的化學助劑包裝袋 Mockup。

### 3. 排版層級混亂與生硬幾何邊框
- **問題**：
  - 首頁 Hero Section 使用了極其生硬的細線圓角 Badge `"Innovation • Precision • Sustainability"`，這是 AI 寫 Copilot/SaaS 網頁的標配，在工業官網中顯得極其多餘且空洞（Filler Content）。
  - 「發展與經營理念」區塊使用了粗暴的對角平鋪（`phi-row`），且邊框使用生硬的 `#e5e4e7` 全封閉框線，缺乏現代網頁的呼吸感與排版留白。
- **改進規格**：精簡無意義的裝飾性 Badge；使用 **無框式排版 (Borderless Layout)** 與柔和的投射陰影，讓元素自然呼吸。

### 4. 單頁應用的功能缺陷：無狀態路由與載入延遲
- **問題**：
  - 網站採用純 React Standalone 狀態路由（`useState('home')`）。客戶點擊「關於我們」或「技術規格」後，若在瀏覽器點擊「重新整理 (Refresh)」，網頁會**直接跳回首頁**！這在真實網站體驗中屬於嚴重 Bug，會讓用戶感到困惑。
  - 使用 `@babel/standalone` 在瀏覽器端進行即時轉譯，每次開網頁都會有明顯的 **1-2秒白屏閃爍 (FOUC)**，這也是 AI 單文件原型的特徵。
- **改進規格**：
  - 導入輕量化的 `hashchange` 監聽器（如 `window.location.hash`），確保重新整理網頁時能保留在當前分頁。
  - 將 CDN React 與 Babel 進行快取優化，或在首頁渲染前加上精緻的「科技感分子鏈骨架屏 (Skeleton Screen)」。

---

## 🛠️ 建議規格修改與實作指引 (Specs)

### 🎨 規格一：品牌設計系統升級 (Brand System Upgrade)
重構 CSS 變數，將 sterile (冷淡) 的色盤替換為高質感工業色盤：

```css
:root {
    /* 質感深沉工業灰色盤 */
    --bg: oklch(98% 0.003 30);        /* 帶極微暖意的石灰白底色 */
    --surface: oklch(100% 0 0);
    --fg: oklch(15% 0.01 30);         /* 深石墨灰，避免純黑的生硬 */
    --muted: oklch(48% 0.01 30);       /* 啞光灰 */
    --border: oklch(92% 0.005 30);
    
    /* 專業化學/高分子象徵色：琥珀金 / 鐵鏽橙 */
    --accent: oklch(62% 0.16 48);      /* 溫潤高質感赤土橙 (Terracotta) */
    --accent-soft: oklch(96% 0.02 48); /* 淺色半透明底色 */

    --font-display: 'Inter', -apple-system, system-ui, sans-serif;
    --font-body: 'Inter', -apple-system, system-ui, sans-serif;
    
    --radius-sm: 4px;
    --radius-md: 8px;
    --radius-lg: 24px;
}
```

### 🧩 規格二：消除 AI 罐頭痕跡 (Anti-Slop Implementation)
1. **移除/重構 generic 裝飾元素**：
   - 移除 Hero 頂部的細線 Badge。
   - 將首頁的無意義小字「定義助劑新標桿」升級為具說服力的企業核心文案。
2. **美化產品卡片圖片區塊**：
   - 嚴格禁止顯示灰色塊文字 "PRODUCT IMAGE"。
   - 使用 CSS 動態渲染純幾何科學線條（如：高分子六角晶格 SVG 背景）作為預設卡片配圖，展現「分子級技術研發」形象。

### 🔗 規格三：原生 Hash 路由修復 (Hash-Based Router)
在 React 程式碼中，使用瀏覽器的 `window.location.hash` 進行分頁狀態維護，解決重新整理網頁會跳回首頁的問題：

```javascript
// 在 App 組件中導入原生 Hash 路由
const App = () => {
    // 預設從 window.location.hash 讀取分頁，例如 #about
    const getHashPage = () => {
        const hash = window.location.hash.replace('#', '');
        return ['home', 'about', 'products', 'support', 'contact'].includes(hash) ? hash : 'home';
    };

    const [currentPage, setCurrentPage] = useState(getHashPage());

    useEffect(() => {
        const handleHashChange = () => {
            setCurrentPage(getHashPage());
        };
        window.addEventListener('hashchange', handleHashChange);
        return () => window.removeEventListener('hashchange', handleHashChange);
    }, []);

    const navigate = (p) => {
        window.location.hash = p === 'home' ? '' : p;
    };
    
    // ... 後續渲染邏輯保持一致 ...
};
```

---

## 📢 指派與下一棒交接 (Handoff)

> [!IMPORTANT]
> **AG 鐵律：AG 只產規格，絕不碰程式碼。**
> 目前設計審查與規格已制定完成。本機有執行助理 **OpenCode** 隨時待命。
>
> 接下來，我們將**呼叫 OpenCode** 並傳遞本規格書，命令 OpenCode 依據上述規格完成程式碼改寫與本機測試，最後自動推送上網讓客戶檢視！
