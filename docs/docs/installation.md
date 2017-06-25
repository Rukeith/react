---
id: installation
title: 安裝
permalink: docs/installation.html
redirect_from:
  - "download.html"
  - "downloads.html"
  - "docs/tooling-integration.html"
  - "docs/package-management.html"
  - "docs/language-tooling.html"
  - "docs/environments.html"
next: hello-world.html
---
<style>
  .tab-hidden {
    display: none;
  }
</style>

React 具有彈性可被用於多種專案中。你可以使用它建議新的應用程式，也可以逐步的加入現有的程式碼中，而不需要重寫。

<div class="toggler">
  <style>
    .toggler li {
       display: inline-block;
       position: relative;
       top: 1px;
       padding: 10px;
       margin: 0px 2px 0px 2px;
       border: 1px solid #05A5D1;
       border-bottom-color: transparent;
       border-radius: 3px 3px 0px 0px;
       color: #05A5D1;
       background-color: transparent;
       font-size: 0.99em;
       cursor: pointer;
    }
    .toggler li:first-child {
      margin-left: 0;
    }
    .toggler li:last-child {
      margin-right: 0;
    }
    .toggler ul {
      display: inline-block;
      list-style-type: none;
      margin: 0;
      border-bottom: 1px solid #05A5D1;
      cursor: default;
    }
    @media screen and (max-width: 960px) {
      .toggler li,
      .toggler li:first-child,
      .toggler li:last-child {
        display: block;
        border-bottom-color: #05A5D1;
        border-radius: 3px;
        margin: 2px 0px 2px 0px;
      }
      .toggler ul {
        border-bottom: 0;
      }
    }
    .display-target-fiddle .toggler .button-fiddle:focus,
    .display-target-newapp .toggler .button-newapp:focus,
    .display-target-existingapp .toggler .button-existingapp:focus {
      background-color: #046E8B;
      color: white;
    }
    .display-target-fiddle .toggler .button-fiddle,
    .display-target-newapp .toggler .button-newapp,
    .display-target-existingapp .toggler .button-existingapp {
      background-color: #05A5D1;
      color: white;
    }
    block {
      display: none;
    }
    .display-target-fiddle .fiddle,
    .display-target-newapp .newapp,
    .display-target-existingapp .existingapp {
      display: block;
    }
  </style>
  <script>
    document.querySelector('.toggler').parentElement.className += ' display-target-fiddle';
  </script>
  <span>以下哪個選項最貼近你想做的事呢？</span>
  <br />
  <br />
   <ul role="tablist" >
      <li id="fiddle" class="button-fiddle" aria-selected="false" role="tab" tabindex="0" aria-controls="fiddletab"
          onclick="display('target', 'fiddle')" onkeyup="keyToggle(event, 'fiddle', 'existingapp', 'newapp')">
        嘗試 React
      </li>
      <li id="newapp" class="button-newapp" aria-selected="false" role="tab" tabindex="-1" aria-controls="newapptab"
          onclick="display('target', 'newapp')" onkeyup="keyToggle(event, 'newapp', 'fiddle', 'existingapp')">
        建立一個新的應用程式
      </li>
      <li id="existingapp" class="button-existingapp" aria-selected="false" role="tab" tabindex="-1" aria-controls="existingapptab"
          onclick="display('target', 'existingapp')" onkeyup="keyToggle(event, 'existingapp', 'newapp', 'fiddle')">
        把 React 添加到現有的應用程式
      </li>
    </ul>
</div>

<block id="fiddletab" role="tabpanel" class="fiddle"/>

## 嘗試 React

如果你只是想嘗試一下 React，你可以使用 CodePen。首先從[這個 Hello World 範例程式碼](http://codepen.io/gaearon/pen/rrpgNB?editors=0010)開始。你不需要安裝任何東西，你可以只修改程式碼並看它如何運作的。

如果你比較喜歡使用你個人的編輯器，你也可以<a href="/react/downloads/single-file-example.html" download="hello.html">下載這個 HTML 檔案</a>來編輯，再用你的瀏覽器從本地的檔案系統打開它。它會執行一個緩慢的程式碼轉換，所以不要再生產環境中使用。

如果你想要在一整個應用程式中使用，有兩種主要的方式：建立 React 應用程式或添加 React 到現有應用程式。

<block id="newapptab" role="tabpanel" class="newapp" />

## 建立一個新的應用程式

[建立 React 應用程式](http://github.com/facebookincubator/create-react-app) 是開始建立新的 React 單頁應用程式的最好方法。它設置好了你的開發環境，所以你可以使用最新的 JavaScript 特性，提供一個好的開發體驗並為了生產環境優化你的應用程式。

```bash
npm install -g create-react-app
create-react-app my-app

cd my-app
npm start
```

建立 React 應用程式不會處理後端邏輯或資料庫。它只會建立一個前端建構通道，所以你可以使用它來串接任何你想要的後端。它可以使用像是 Babel 和 Webpack 的建構工具，也可以在沒有配置的，也可以在沒有配置之下運作。

當你準備要部署到生產環境時，執行 `npm run build` 將會在 `build` 目錄中建立一個優化好的應用程式。你可以從 [README](https://github.com/facebookincubator/create-react-app#create-react-app-) 和[使用者指南](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#table-of-contents)暸解更多資訊。

<block id="existingapptab" role="tabpanel" class="existingapp" />

## 把 React 添加到現有的應用程式

你不需要為了使用 React 而重構你的應用程式。

我們建議先將 React 添加到應用程式中的一小部分，例如一個獨立的小插件，以便你查看是否運作正常。

雖然 React [可以使用](/react/docs/react-without-es6.html)在沒有任何建構通道的情況。但為了有更多的生產力，我們建議還是要設置它。現今的建構通道包括：

* **套件管理器**，例如 [Yarn](https://yarnpkg.com/) 或 [npm](https://www.npmjs.com/)。它能讓你使用龐大的第三方套件生態系統，並且能輕鬆的安裝或升級這些套件。
它可以让你使用庞大的第三方软件包生态系统，还能很方便的安装或升级。
* **包裝器**，例如 [webpack](https://webpack.js.org/) 或 [Browserify](http://browserify.org/)。它能讓你編寫模組化程式碼並且壓縮檔案來優化載入時間。
* **編譯器**，例如 [Babel](http://babeljs.io/)。它能讓你用含有最新特性的 JavaScript 程式碼運行在舊版的瀏覽器。

### 安裝 React

>**注意:**
>
>一旦安裝後，我們強烈建議設置[生產建構程序](/react/docs/optimizing-performance.html#use-the-production-build)以確保你在生產環境使用最新版的 React。

我們建議使用 [Yarn](https://yarnpkg.com/) 或 [npm](https://www.npmjs.com/) 來管理前端相依性。如果你還未使用過套件管理器，[Yarn 文件](https://yarnpkg.com/en/docs/getting-started) 會是一個不錯的開始。

使用 Yarn 安裝 React，執行:

```bash
yarn init
yarn add react react-dom
```

使用 npm 安裝 React，執行:

```bash
npm init
npm install --save react react-dom
```

Yarn 和 npm 都會從 [npm registry](http://npmjs.com/) 下載套件。

### 使用 ES6 和 JSX

我們建議使用 [Babel](http://babeljs.io/) 搭配 React，來讓你可以在你的 JavaScript 程式碼中使用 ES6 和 JSX。ES6 是一系列最新 JavaScript 特性，能讓開發變得更簡單，而 JSX 是與 React 搭配使用的 JavaScript 語言的擴展。

[Babel 設置說明](https://babeljs.io/docs/setup/) 說明如何在不同的建構環境中做設定。確認你已經安裝 [`babel-preset-react`](http://babeljs.io/docs/plugins/preset-react/#basic-setup-with-the-cli-) 和 [`babel-preset-es2015`](http://babeljs.io/docs/plugins/preset-es2015/#basic-setup-with-the-cli-) 並且在 [`.babelrc` configuration](http://babeljs.io/docs/usage/babelrc/) 中啟動它們，接下來你就準備好接下去了。

### 在 Hello Wrorld 中使用 ES6 的 JSX

我們建議使用包裝器如 [webpack](https://webpack.js.org/) 或 [Browserify](http://browserify.org/) 以便於編寫模組程式碼並將其壓縮成小套件，優化載入時間。

下面是最基本的 React 範例：

```js
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

这段代码会将其渲染入一个 ID 为 root 的 DOM 元素，所以在你的 HTML 文件中需要有 <div id="root"></div>。

类似以上，你可以在任何由其他 JavaScript UI 库编辑的现有应用中，将 React 渲染进一个 DOM 元素。
這段程式碼會在一個 id 為 `root` 的 DOM 元素中渲染，所以你需要在你的 HTML 檔案中有 `<div id="root"></div>`。

同樣地，你可以將 React 渲染到任何由其他 JavaScript UI library 寫成的現有應用程式中的一個 DOM 元素。

[暸解更多 React 集成現有程式碼的資訊](/react/docs/integrating-with-other-libraries.html#integrating-with-other-view-libraries)

### 開發和生產版本

預設情況下，React 含有很多有用的警告，這些警告在開發中非常有用。

**然而，這些將使開發版本的 React 體積更大且運行較慢，所以你應該在部署應用程式時使用生產版本。**

暸解[如何判斷你的網站是否使用合適的版 React 版本](/react/docs/optimizing-performance.html#use-the-production-build)，以及如何設置更有效率的生產建構程序：

* [使用 Create React App 建立應用程式](/react/docs/optimizing-performance.html#create-react-app)
* [使用單一檔案建立應用程式](/react/docs/optimizing-performance.html#single-file-builds)
* [使用 Brunch 建立應用程式](/react/docs/optimizing-performance.html#brunch)
* [使用 Browserify 建立應用程式](/react/docs/optimizing-performance.html#browserify)
* [使用 Rollup 建立應用程式](/react/docs/optimizing-performance.html#rollup)
* [使用 Webpack 建立應用程式](/react/docs/optimizing-performance.html#webpack)

### 使用 CDN

如果你不想使用 npm 来管理套件，`react` 和 `react-dom` npm 套件也提供發佈在 `dist` 目錄的單一檔案並託管在 CDN 上。

```html
<script src="https://unpkg.com/react@15/dist/react.js"></script>
<script src="https://unpkg.com/react-dom@15/dist/react-dom.js"></script>
```

以上版本僅適用於開發環境，不適合生產環境。壓縮和優化後的 React 生產環境版本如下：

```html
<script src="https://unpkg.com/react@15/dist/react.min.js"></script>
<script src="https://unpkg.com/react-dom@15/dist/react-dom.min.js"></script>
```

如果想要載入特定版本的 `react` 和 `react-dom`，用版本號替换 `15`。

如果你使用 Bower，可以透過 `react` 套件來使用 React。

<script>
/**
 * The code below is based on a snippet from React Native Getting Started page.
 */

// Convert <div>...<span><block /></span>...</div>
// Into <div>...<block />...</div>
var blocks = document.getElementsByTagName('block');
for (var i = 0; i < blocks.length; ++i) {
  var block = blocks[i];
  var span = blocks[i].parentNode;
  var container = span.parentNode;
  container.insertBefore(block, span);
  container.removeChild(span);
}
// Convert <div>...<block />content<block />...</div>
// Into <div>...<block>content</block><block />...</div>
blocks = document.getElementsByTagName('block');
for (var i = 0; i < blocks.length; ++i) {
  var block = blocks[i];
  while (block.nextSibling && block.nextSibling.tagName !== 'BLOCK') {
    block.appendChild(block.nextSibling);
  }
}

function setSelected(value){
  var tabs = document.querySelectorAll('li[role="tab"]');
  for (var i = 0; i < tabs.length; ++i) {
    var tab = tabs[i];
    if (tab.className === 'button-' + value) {
      tabs[i].setAttribute('aria-selected', 'true');
      tabs[i].setAttribute('tabindex', '0');
    } else {
      tabs[i].setAttribute('aria-selected', 'false');
      tabs[i].setAttribute('tabindex', '-1');
    }
  }
}

function keyToggle(e, value, prevTab, nextTab){
  if (e.keyCode === 37) {
    document.getElementById(prevTab).focus();
    display('target', prevTab);
  }
  if (e.keyCode === 39) {
    document.getElementById(nextTab).focus();
    display('target', nextTab);
  }
}

function display(type, value) {
  setSelected(value);
  var container = document.getElementsByTagName('block')[0].parentNode;
  container.className = 'display-' + type + '-' + value + ' ' +
    container.className.replace(RegExp('display-' + type + '-[a-z]+ ?'), '');
}

// If we are coming to the page with a hash in it (i.e. from a search, for example), try to get
// us as close as possible to the correct platform and dev os using the hashtag and block walk up.
var foundHash = false;
if (window.location.hash !== '' && window.location.hash !== 'content') { // content is default
  // Hash links are added a bit later so we wait for them.
  window.addEventListener('DOMContentLoaded', selectTabForHashLink);
}

function selectTabForHashLink() {
  var hashLinks = document.querySelectorAll('a.hash-link');
  for (var i = 0; i < hashLinks.length && !foundHash; ++i) {
    if (hashLinks[i].hash === window.location.hash) {
      var parent = hashLinks[i].parentElement;
      while (parent) {
        if (parent.tagName === 'BLOCK') {
          var target = null;
          if (parent.className.indexOf('fiddle') > -1) {
            target = 'fiddle';
          } else if (parent.className.indexOf('newapp') > -1) {
            target = 'newapp';
          } else if (parent.className.indexOf('existingapp') > -1) {
            target = 'existingapp';
          } else {
            break; // assume we don't have anything.
          }
          display('target', target);
          foundHash = true;
          break;
        }
        parent = parent.parentElement;
      }
    }
  }
}
</script>
