# 前端開發者清單

如果您對這份清單有興趣，可以到譯者我寫的 [front-end climbing](https://enginelin.github.io/front-end-climbing/) 看看。

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**前端開發者清單** 是一份詳細的清單，用來檢查你的網站或網頁公布前所有應該完成的項目。
這份清單基於我多年的前端工程師工作經驗，以及其他公開的清單資源製作。

*在 Product Hunt 上投票與推薦，協助我們將 Front-End Checklist 分享出去*

[![](http://res.cloudinary.com/djnyaloac/image/upload/v1508896898/upvote-producthunt_vzys4c.jpg)](https://www.producthunt.com/posts/front-end-checklist)

## 目錄

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Images](#images)**
6. **[JavaScript](#javascript)**
7. **[Security](#security)**
8. **[Performance](#performance-1)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## 使用方式

**前端開發者清單**中的所有項目皆來是大多數專案的需求，針對你的專案時，還是會有某些項目用不到、可以忽略(例如，在行政用途的網頁 APP 中，你可能不需要 RSS 的訂閱功能)。我們依照可以調動的靈活性區分為三個等級：

* ![Low][low_img] 代表這是個**推薦**項目，但在特定的情況下可以忽略。
* ![Medium][medium_img] 代表這是**高度推薦**項目，在非常少數的特定情況下可以忽略。其中某些項目，如果忽略了會使效能或 SEO 結果(指搜尋引擎上的排名)很糟。
* ![High][high_img] 代表這是任何情況下都**不能忽略**的項目。忽略可能在你的網頁、網頁親和力或 SEO 上造成功能失常。這些項目的測試優先度最高。

某些資源有標示符號，協助你瞭解在清單中找到的內容或協助的類型:

* 📖: 文檔或文章
* 🛠: 網路工具 / 測試工具
* 📹: 媒體或影片內容

---

## Head

> **補充:** 這有[一份列表](https://github.com/joshbuchea/HEAD)可以找到 HTML 檔案中`<head>`裡面可能含有的所有東西。

### Meta 標籤

* [ ] **Doctype (檔案類型)** ![High][high_img] Doctype 是 HTML5，同時要放在 HTML 頁面的最上面。

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> 📖 [決定字符編碼 - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*接下來三個 mata 標籤(Charset、X-UA Compatible 和 Viewport)需要先講解。*

* [ ] **Charset (字符):** ![High][high_img] Charset = UTF-8 被正確的宣告。

```html
<!-- 為文件設定字符編碼 -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible (IE 相容設定):** ![Medium][medium_img] X-UA-Compatible meta 標籤存在。

```html
<!-- 教導 Internet Explorer 使用最新的渲染引擎 -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> 📖 [指定文件的繼承模式 (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport (視點):** ![High][high_img] 正確宣告 viewport。

```html
<!-- Viewport 用在響應式網頁設計 -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title (標題):** ![High][high_img] 所有頁面都有使用一個 title (SEO: Google 會計算 title 上使用的字符寬度，只會偵測到 472px ~ 482px 之間。平均最大值是 55 個字符)。

```html
<!-- 檔案標題 -->
<title>Page Title less than 65 characters</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description (敘述):** ![High][high_img] 有設置 meta description，每個頁面只有一個且長度不能超過150字元。

```html
<!-- Meta Description -->
<meta name="description" content="Description of the page less than 150 characters">
```

> * 📖[Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** ![Medium][medium_img] 每一個 favicon 都需要創立且被正確展示。如果你只有一個 `favicon.ico`，可以將它放在網頁最底層的檔案。通常你不需要對他加以修改。無論如何，這依舊是個好例子，可以跟下方的例子互相呼應。現在比起`.icon`比較推薦 **PNG 的檔案格式**。(大小最少需要: 32x32px)

```html
<!-- 一般的 favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- 推薦使用的 favicon 檔案格式 -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon 產生器](https://www.favicon-generator.org/)
> * 🛠 [真正的 Favicon 產生器 (RealFaviconGenerator)](https://realfavicongenerator.net/)
> * 📖 [Favicon 小抄](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons、手機觸控按鈕 、標題標誌...等等。你需要哪一個? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon (蘋果手機觸控按鈕):** ![Low][low_img] Apple Touch favicon 已設置 Apple Touch Icon。*(200x200px 以上的 apple 按鈕圖檔便能支援大部分你所需螢幕的尺寸)*

```html
<!-- 蘋果手機觸控按鈕 -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> 📖 [搞懂網頁應用程式](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Low][low_img] 已設置並連結 Windows Titels。

```html
<!-- Microsoft Titles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

browserconfig.xml 檔案中 xml 最小設定值如下:
```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> 📖 [瀏覽器的配置模式參考](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical (典範):** ![Medium][medium_img] 使用`rel="canonical"`避免重複的內容。

```html
<!-- 協助避免重複內容的問題 -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

> * 📖 [Use canonical URLs - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
> * 📖 [rel=canonical 常見的五個錯誤 - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML 標籤

* [ ] **Language tag (語言標籤):** ![High][high_img] 語言標籤在網頁中被指定且與當前頁面的語言是相關的。

```html
<html lang="en">
```

* [ ] **Direction tag (方向標籤):** ![Medium][medium_img] 文字閱讀方向有被設定在 body 標籤內 (也可以用在其他 HTML 標籤裡)。

```html
<html dir="rtl">
```
(註: right to left 或 left to right 的簡寫)

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language (備用語言):** ![Low][low_img] 語言標籤在網頁中被指定且與當前頁面的語言是相關的。

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments (條件備註):** ![Low][low_img] 如果有需要，已經為 IE 設定 Conditional comments。

> 📖 [關於 conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)


* [ ] **RSS feed (RSS 訂閱):** ![Low][low_img] 如果網站是部落格或者會分享文章，設置 RSS 連結。

* [ ] **CSS Critical (最小 CSS 合集):** ![Medium][medium_img] CSS critical 將使用在頁面顯示部分的核心 CSS 收集起來，在主要的CSS被呼叫之前就先渲染。它以放置於`<style></style>`間的形式嵌在檔案中(單行形式、最小化)。

> 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical)

* [ ] **CSS order (CSS 順序):** ![High][high_img] 在`<head>`哩，所有 CSS 檔案都要在 JS 檔案前被載入。(例外狀況: 當JS檔案以異步方式在頁面上方被載入)

### 社交 meta

***Facebook OG*** 及 ***Twitter Cards*** 針對所有網頁都高度推薦。關於其他社交媒體的標籤，當你有特別想要確保的社交媒體的顯示功能再考慮。

* [ ] **Facebook Open Graph (FB 開放圖形):** ![Low][low_img] 所有 Facebook Open Graph 都有測試過且沒有遺漏掉或出現失敗的訊息。圖檔最小需要 600x315px，推薦大小 1200x630px。

> **補充:** 利用 og:image:width 及 og:image:height 的方式指定圖片尺寸，者可以協助爬蟲直接渲染圖片，不需要再異步載入並處理它。

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<!-- Next tags are optional but recommended -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

> * 📖 [網頁大師的分享指南](https://developers.facebook.com/docs/sharing/webmasters/)
> * 📖 [Best Practices - Sharing](https://developers.facebook.com/docs/sharing/best-practices/)
> * 🛠 利用[Facebook OG testing](https://developers.facebook.com/tools/debug/)測試你的網頁

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Twitter card 入門 — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 利用[Twitter card validator](https://cards-dev.twitter.com/validator)測試你的網頁

**[⬆ back to top](#table-of-contents)**

---

## HTML

### 最佳寫法

* [ ] **HTML5 Semantic Elements (HTML5 語意元素):** ![High][high_img] HTML5 Semantic Elements 被適當使用(header, section, footer, main...)。

> 📖 [HTML 參考](http://htmlreference.io/)

* [ ] **Error pages (錯誤頁面):** ![High][high_img] 404 錯誤頁面跟存在 5xx 錯誤的情況需要它自己的 CSS 程式碼(不要從當前的服務向外呼叫)。

* [ ] **Noopener:** ![Medium][medium_img] 注意，當你有外部連結且使用`target="_blank"`時，在連結加上`rel="noopener"`，可以避免 tab nabbing(開啟新 tab 時造成原頁面效能低落)。若你要支援舊版 Firefox，使用`rel="noopener noreferrer"`。

> 📖 [關於 rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Clean up comments (清除備註):** ![Low][low_img] 頁面發表前將沒有效果的程式碼清除。

### HTML 測試

* [ ] **W3C compliant (W3C 兼容):** ![High][high_img] 所有頁面都要經過 W3C 檢測器的測試，確保沒有 HTML 程式碼的問題。

> 🛠 [W3C 檢測器](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High][high_img] 我使用工具分析自己的 HTML 程式碼，幫助我發現任何可能的問題。

> 🛠 [髒亂程式碼修飾器](https://dirtymarkup.com/)

* [ ] **Link checker (連結確認器):** ![High][high_img] 使用 Link checker 確保沒有任何無效連結，避免出現任何 404 error。

> 🛠 [W3C 連結確認器](https://validator.w3.org/checklink)

* [ ] **Adblockers test (廣告阻斷程式測試):** ![Medium][medium_img] 測試你的頁面在廣告阻斷程式運作的情況下能正確顯示(你可以顯示訊息慫恿使用者關閉廣告阻斷程式)。



**[⬆ back to top](#table-of-contents)**

---

## 網頁字體

> **補充:** 使用 webfonts 可能會導致 Flash Of Unstyled Text / Flash Of Invisible Text - 考慮使用後備字體和/或利用 webfont 加載器來控制行為。

* [ ] **Webfont format (網頁字體格式):** ![High][high_img] 所有瀏覽器都支援 WOFF、WOFF2 跟 TTF 字體。

> * 📖 [WOFF - 網頁開放字體格式 - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - 網頁開放字體格式 - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType 字體及 OpenTyps 字體的支援狀況](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size (網頁字體大小):** ![High][high_img] 網頁字體檔案大小不能超過 2MB (包含所有字體)。

* [ ] **Webfont loader (網頁字體加載器):** ![Low][low_img] 利用 webfont loader 控制載入的行為。

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ back to top](#table-of-contents)**

---

## CSS

> **補充:** 看看許多前端開法者遵照的 [CSS 指南](https://cssguidelin.es/)與 [Sass 指南](https://sass-guidelin.es/)。 如果你懷疑CSS的效能，可以看 [CSS 參考](http://cssreference.io/).

* [ ] **Responsive Web Design (網站響應式設計):** ![High][high_img] 網站有使用響應式設計。
* [ ] **CSS Print (CSS 列印):** ![Medium][medium_img] 每個頁面都正確設置列印樣式。
* [ ] **Preprocessors (預處理器):** ![Medium][medium_img] 你的頁面有使用 CSS 預處理器 (推薦 [Sass](http://sass-lang.com/))。
* [ ] **Unique ID (ID 獨特性):** ![High][high_img] 使用ID的時候確保個別頁面裡沒有重複。
* [ ] **Reset CSS (初始化 CSS):** ![High][high_img] 確保 CSS reset (reset, normalize or reboot)被使用*(如果你使用 CSS 框架，例如 Bootstrap 或 Foundation，Normalize 已經包含在裡面)*。

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix (JS 前置語言):** ![Low][low_img] 將所有以**js-**開頭命名(或在JS檔案中以 id- 開頭命名)的字符，避免寫入 CSS 檔案中。

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS embed or line (CSS 的嵌入):** ![High][high_img] 除非特別情況(例如: slider, CSS critical 的 background-image)，避免使用 CSS embed 或 inline。

* [ ] **Vendor prefixes (前置語言產生器):** ![High][high_img] 已經使用了 CSS 的 vendor prefixes，且依照瀏覽器支援狀況自動生成相對應的 CSS 前置語言。

> 🛠 [線上 CSS 自動前置語言生成器](https://autoprefixer.github.io/)

### 效能

- [ ] **Concatenation (並列):** ![High][high_img] 已經將所有 CSS 檔案合併成一個*(不適用 HTTP/2)*
- [ ] **Minification (最小化):** ![High][high_img] 已將所有 CSS 檔案壓縮。
- [ ] **Non-blocking (不阻塞):** ![Medium][medium_img] CSS 檔案需要 non-blocking，避免還在抓取 DOM 時就載入。

> * 📖 [透過 filament group 進行 loadCSS](https://github.com/filamentgroup/loadCSS)
> * 📖 [使用 loadCSS 預載入 CSS 的例子](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS (無用的 CSS):** ![Low][low_img] 移除沒用到的 CSS。

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome 開發者工具 Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS 測試

* [ ] **Stylelint:** ![High][high_img] 檢測所有 CSS、SCSS 檔案都沒有錯誤。

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass 指南](https://sass-guidelin.es/)

* [ ] **Responsive web design (響應式網頁設計):** ![High][high_img] 所有頁面至少測試下列節點: 320px, 768px, 1024px (可以依照你的客戶群進行增減)。

* [ ] **CSS Validator (CSS 檢測器):** ![Medium][medium_img] 測試 CSS 並且修正相關錯誤。

> 🛠 [CSS 檢測器](https://jigsaw.w3.org/css-validator/)

* [ ] **Desktop Browsers (桌上瀏覽器):** ![High][high_img] 所有頁面都經過所有桌上瀏覽器的測試(Safari, Firefox, Chrome, Internet Explorer, EDGE...)。
* [ ] **Mobile Browsers (手機瀏覽器):**  ![High][high_img] 所有頁面都經過所有手機瀏覽器的測試(Native browser, Chrome, Safari...)。
* [ ] **OS:**  ![High][high_img] 所有頁面都經過所有作業系統的測試(Windows, Android, iOS, Mac...)。

- [ ] **Pixel perfect (完美像素):** ![High][high_img] 確保頁面的像素最佳化。這取決於你的作品品質，你不需要 100% 準確，但應該盡可能接近當初的設計

> [完美像素 - Chrome 擴充軟件](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Reading direction (閱讀方向):** ![High][high_img] 如果有其他語系會被使用到的話，針對所有頁面都使用 LTR 跟 RTL 閱讀方向測試過。

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#table-of-contents)**

---

## Images

> **補充:** 點擊Addy Osmani 的免費電子書**[Essential Image Optimization](https://images.guide/)**，完整理解圖片(image)的優化

### 最佳寫法

* [ ] **Optimization (優化):** ![High][high_img] 所有圖片都優化過且在瀏覽器中正常渲染。重要的頁面可以使用網頁字體格式(像是首頁)。

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 使用 [ImageOptim](https://imageoptim.com/)免費優化你的圖片

* [ ] **Picture/Srcset:** ![Medium][medium_img] 已經使用 picture/srcset 來提供最適合使用者當前 viewport 的圖片。

> * 📖 [如何使用 srcset 打造響應式圖片](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina (視網膜螢幕):** ![Low][low_img] 提供 x2、x3 的圖檔，用來支援視網膜螢幕等級的顯示。
* [ ] **Sprite (雪碧圖):** ![Medium][medium_img] 小圖片都放在 sprite file 中 (一種將相關小圖排列在一起的圖檔)，以 icon 為例，他們可以集中放在一個 SVG sprite image。
* [ ] **Width and Height (寬與高):** ![High][high_img] 如果你已經知道圖片渲染後的尺寸，在`<img>`中直接設定`width`與`height`的屬性(可以忽略 CSS 的尺寸設定)。
* [ ] **Alternative text (補充文字):** ![High][high_img] 所有`<img>`都有一個 Alternative text，用文字敘述圖片的內容。(註:在無障礙網頁中尤其重要)

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading (懶加載):** ![Medium][medium_img] 照片有設置好 lazyload (總是設置 noscript fallback)。
**[⬆ back to top](#table-of-contents)**

---

## JavaScript

### 最佳寫法

* [ ] **JavaScript Inline(JS 被寫入):** ![High][high_img] 沒有任何 JavaScript 程式碼被寫到 HTML 的程式碼中
* [ ] **Concatenation (並列):** ![High][high_img] JavaScript 檔案已經優化。
* [ ] **Minification (最小化):** ![High][high_img] JavaScript 檔案已經壓縮(可以在檔名最後加上`.min`)。

> [壓縮的資源 (HTML、CSS 跟 JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security (JS 安全性):**

> [利用 JavaScript 開發安全應用程式的指南](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)*

* [ ] **Non-blocking (不阻塞):** ![Medium][medium_img] JavaScript 檔案使用異步加載時，在標籤屬性加上`async`，若是延後加載則使用`defer`。

> 📖 [移除干擾渲染的 JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low][low_img] 如果你需要指定特定的功能，可以使用客製化過的 Modernizr 來增加 class 到你的`<html>`。

> 🛠 [客製化你的 Modernizr](https://modernizr.com/download?setclasses)

### JavaScript 測試

* [ ] **ESLint:** ![High][high_img] 檢驗 JavaScript 中被忽略的錯誤(基本上檢查結構跟基礎規則)

> * 📖 [ESLint - 針對 JavaScript 跟 JSXThe 的實用套件程式](https://eslint.org/)

**[⬆ back to top](#table-of-contents)**

---

## Security

### 檢視你的網站

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - ASP.NET 網頁的安全性自動分析器](https://asafaweb.com/)

### 最佳寫法

* [ ] **HTTPS:** ![Medium][medium_img] HTTPS 使用在所有頁面跟所有外部的內容(插件、圖片...等)。

> * 🛠 [來加密吧 - SSL/TLS 的免費證書](https://letsencrypt.org/)
> * 🛠 [免費的 SSL 服務測試](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [嚴格的傳輸安全](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS) (嚴格的傳輸安全):** ![Medium][medium_img] 在 HTTP header 設置'Strict-Transport-Security'。

> * 🛠 [檢查 HSTS 的預載入狀況與權限](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security 小抄 - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [保護傳輸面的小抄 - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF) (跨網站假請求攻擊):** ![High][high_img] 確認發送到服務端的請求會是合法且確實來自你的網站/app，避免 CSRF 攻擊。

> 📖 [Cross-Site Request Forgery (CSRF) 對抗小抄  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS) (跨網站指令碼):** ![High][high_img] 確認網站或頁面不會發生 XSS 的情況。

> * 📖 [XSS (Cross Site Scripting) 對抗小抄  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [ XSS 基於 DOM 的對抗小抄  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Medium][medium_img] 避免 Google Chrome 及 Internet Explorer 嘗試從服務器聲明的內容類型中察覺響應式內容類型。

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO) (外部框架連結設定)** ![Medium][medium_img] 保護你的使用者免於劫持攻擊。

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ back to top](#table-of-contents)**

---

## Performance

### 最佳寫法

- [ ] **Weight page (頁面大小):** ![High][high_img] 每一個檔案的大小都介於 0 ~ 500KB。

> * 🛠 [網站頁面分析](https://tools.pingdom.com)
> * 📖 [大小限制器: 讓網站更輕點](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified (最小化):** ![Medium][medium_img] HTML 有進行壓縮。
> 🛠 [W3C 檢測器](https://validator.w3.org/)

* [ ] **Lazy loading (懶加載):** ![Medium][medium_img] 讓圖片、腳本跟 CSS 都進行 lazy load，提升當前瀏覽的網頁的反應速度(細節在它們個別的章節中)。

* [ ] **Cookie size (cookie 大小):** 如果你有使用 cookie，確保 cookie 大小不要超過 4096 bytes，且在你的網域內別超過20個。

> * 📖 [Cookie 規格: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [瀏覽器 Cookie 限制](http://browsercookielimits.squawky.net/)

* [ ] **Third party components (第三方組件):** ![Medium][medium_img] 可能的話，以靜態的組件取代第三方 iframe 或依賴外部 JS 的組件(如共享按鈕)，進而限制呼叫外部 APIs 的次數並保護使用者的行動隱私。 

> * 🛠 [簡單的分享按鈕產生器](https://simplesharingbuttons.com/)

### 準備迎接接下來的請求

> 📖 [下方技術的解釋](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution (DNS 解析):** ![Low][low_img] 使用`dns-prefetch`讓第三方 DNS 服務方在空閒時間提前處理域名解析的功能。

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection (預連接):** ![Low][low_img] 使用 `preconnect` 在空閒時間提前完成 DNS 查詢、TCP handshake 以及 TLS協商即將要使用到的服務。

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching (預擷取):** ![Low][low_img] 使用 `prefetch` 在空閒時間提前請求即將使用到的資源(例如 lazy loaded images)。

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading (預載入):** ![Low][low_img] 使用 `preload` 提前載入當前頁面需要的資源(例如 `<body>` 最後面的 script 區域)。

```html
<link rel="preload" href="app.js">
```

> * 📖 [prefetch 與 preload 的不同點](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### 效能測試

* [ ] **Google PageSpeed (Google 頁面速度檢測):** ![High][high_img] 測試過所有的網頁(不只首頁)且分數都至少90分(滿分100)。

> * 🛠 [Google 頁面速度檢測](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [利用 Google 測驗頁面在手機上的速度](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - 網站的優化與效能測試](https://www.webpagetest.org/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **補充:** 你可以看這份清單 [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### 最佳寫法

- [ ] **Progressive enhancement (逐步增強):** ![Medium][medium_img] 網站的重要功能，像是主要的指引或搜尋區塊需要在沒有 JavaScript 的情況下也能運作。

> 📖 [Chrome 開發者工具的 Enable / Disable JavaScript](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast (顏色對比):** ![Medium][medium_img] 顏色對比度最少要通過 WCAG 的　AA 級(手機要達到 AAA)。

> 🛠 [對比值](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] 所有頁面都要一個不是網頁名稱的 H1 標籤(代表頁面的主要功能)。
* [ ] **Headings (標題):** ![High][high_img] 標題標籤要按照等級妥善的使用(H1 to H6)。

> 📹 [為何標題跟地標如此重要 -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High][high_img] `<header>` has `role="banner"`.
- [ ] **Role navigation:** ![High][high_img] `<nav>` has `role="navigation"`.
- [ ] **Role main:** ![High][high_img] `<main>` has `role="main"`.

> 📖 [使用 ARIA landmarks 劃分頁面的區塊](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)


### 語意

- [ ] **Specific HTML5 input types are used (有指定 HTML5 輸入標籤的類型):** ![Medium][medium_img] 這在手機上顯示不同類型的客製化鍵盤或配件時特別重要。

> 📖 [手機 input 標籤類型](http://mobileinputtypes.com/)

### Form

* [ ] **Label (標誌):** ![High][high_img] Lable 各自會與相對的元素產生關聯。如果希望 label 不能被隱藏起來，使用`aria-label`來代替。 

> 📖 [使用 aria-label 屬性 - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility 測試

* [ ] **Accessibility standards testing (親和力標準測試):** ![High][high_img] 利用 Wave 測試你的頁面達到親和力標準。

> 🛠 [Wave 測試](http://wave.webaim.org/)

* [ ] **Keyboard navigation (鍵盤導覽):** ![High][high_img] 測試看看，在你的網站只使用鍵盤按照順序瀏覽，確保所有互動元素都可以點選、使用。
* [ ] **Screen-reader (螢幕閱讀器):** ![Medium][medium_img] 所有頁面都使用 screen-reader 測試過 (VoiceOver、ChromeVox、NVDA 或 Lynx)。
* [ ] **Focus style (專注風格):** ![High][high_img] 如果 focus 無法使用，它會被 CSS 中的視覺部分取代。

> 📹 [管理 Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics (Google 分析):** ![High][high_img] 確認 Google Analytics 已經安裝且確實的架構好。
* [ ] **Headings logic (標題邏輯):** ![Medium][medium_img] Headings 有助於理解這個頁面的內容。
* [ ] **sitemap.xml:** ![High][high_img] 確認有 sitemap.xml 且已經提交給 Google Search Console (Google 搜尋引擎管理者，即之前的 Google 頁面管理者工具)。
* [ ] **robots.txt:** ![High][high_img] Robots.txt 不會破壞網頁。

> * 🛠 利用 [Google Robots 測試工具](https://www.google.com/webmasters/tools/robots-testing-tool)測試你的robots.txt。

* [ ] **Structured Data (結構化資料):** ![High][high_img] 確認所有頁面使用了 Structured Data 且已經測試過沒有出現錯誤。Structured Data 會協助爬蟲理解這個頁面的內容。

> * 📖 [介紹 Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 利用 [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/) 測試你的網頁
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Heirarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML (HTML 網站地圖):** ![Medium][medium_img] 已經設置 HTML sitemap 且透過網站 footer 中的連結可以使用。

> * 📖 [Sitemap 指南 - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap 檢測器](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ back to top](#table-of-contents)**

---

## Translation

The Front-End Checklist is also available in other languages. Thanks for all translators and their awesome work!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
* 🇹🇼 Traditional Chinese: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)

---

## Front-End Checklist 勛章

如果你希望向別人展示你的網站通過這份前端開發者清單，將這個勛章放進你的 README 文件中!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is automatically reflected on the [Front-End Checklist](http://frontendchecklist.com/) website.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

### Contributors

Check out all the super awesome [contributors](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Support

如果你有任何問題或建議，別客氣，使用 Gitter 或 Twitter 讓我知道:

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Facebook](https://www.facebook.com/frontendchecklist/)
* [Twitter](https://twitter.com/thedaviddias)

## Authors

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
