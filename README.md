這是一個測試練習本。使用 Next.js(Reactjs + Typescript)

### Requirements

- Node.js v14.21.2 or newer

### Install

```
npm i
```

### How to Start

1. 啟動 server(http://localhost:3000)

```bash
npm run dev
```

2. 在資料夾`pages/__tests__/exercise`開始練習 (資料夾 `pages/__tests__/final` 是參考答案)

```bash
npm run test:watch
```

### 2025/12/26 更新

- 解決相依性警告驗證紀錄
  我們已成功消除了執行 npm i 時出現的棄用警告，並確保專案功能依然正常。

變更項目

1. 移除過時套件
   移除 mdx.macro：此套件已不再維護，且是 core-js@1.x/2.x 警告的主要來源。經檢查，專案已改用 mdx-bundler，因此可安全移除。
2. 更新相依性版本
   next: 升級至 12.3.4。
   @testing-library/jest-dom: 升級至 5.17.0。
   jest-styled-components: 升級至 7.1.1。 這些更新有助於消除 source-map-resolve 的警告。
3. 修復測試回歸
   新增 @babel/preset-react：移除 mdx.macro 後發現測試環境缺少此 preset，已手動將其加入 devDependencies 以維持測試運作。
