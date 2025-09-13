# Tech Odyssey: 未來之旅 - 心理測驗網站

一個具有科技感的心理測驗網站，幫助用戶探索專題興趣取向並推薦相關專題項目。

## 📋 項目簡介

Tech Odyssey 是一個互動式心理測驗平台，通過三個關鍵問題分析用戶的興趣傾向，並推薦最適合的專題項目。網站採用星空科技主題設計，提供沉浸式的用戶體驗。

### 🎯 核心功能

- **心理測驗系統**：3道題目，8種結果組合
- **智能推薦**：根據測驗結果推薦對應專題
- **詳細展示**：每個專題包含簡介、動機、介紹三個部分
- **響應式設計**：支持手機和電腦端使用
- **科技風格**：星空背景 + 科技字體 + 現代化 UI

## 🚀 快速開始

### 環境需求

- Python 3.7+
- Flask
- 現代瀏覽器（支持 CSS Grid 和 Flexbox）

### 安裝步驟

1. **克隆項目**
   ```bash
   git clone <your-repository-url>
   cd tech-odyssey
   ```

2. **安裝依賴**
   ```bash
   pip install flask
   ```

3. **準備背景圖片**
   ```
   項目根目錄/
   ├── static/
   │   └── images/
   │       └── lovepik-starry-background-of-science-and-technology-image_500400275.jpg
   ```

4. **運行應用**
   ```bash
   python app.py
   ```

5. **訪問網站**
   打開瀏覽器訪問：`http://localhost:5000`

## 📁 項目結構

```
tech-odyssey/
├── app.py                 # Flask 主應用
├── templates/
│   └── index.html         # 主頁面模板
├── static/
│   └── images/
│       └── lovepik-starry-background-of-science-and-technology-image_500400275.jpg
└── README.md             # 項目說明文件
```

## 🧠 測驗邏輯

### 測驗問題

1. **能力選擇**：導航系統 vs 船員管理
2. **探索方式**：資料派 vs 人本派  
3. **任務傾向**：打造工具 vs 引導夥伴

### 結果分類

| 組合 | 分類路徑 | 推薦專題數量 |
|------|----------|-------------|
| A | 導航系統 → 資料派 → 打造工具 | 2個 |
| B | 導航系統 → 資料派 → 引導夥伴 | 2個 |
| C | 導航系統 → 人本派 → 打造工具 | 2個 |
| D | 導航系統 → 人本派 → 引導夥伴 | 2個 |
| E | 船員管理 → 資料派 → 打造工具 | 2個 |
| F | 船員管理 → 資料派 → 引導夥伴 | 2個 |
| G | 船員管理 → 人本派 → 打造工具 | 2個 |
| H | 船員管理 → 人本派 → 引導夥伴 | 2個 |

## 📊 包含專題

網站收錄了 16 個專題項目，涵蓋以下領域：

- **AI 與機器學習**：GaAsBi 預測、TradeNova 投資平台、AI 面試系統
- **物聯網與硬體**：遠端機械手臂、智慧路牌系統
- **教育科技**：AI 學習同伴、未來造物島、VR 社交學習
- **健康醫療**：PiCare、樂活無齡教具
- **遊戲化應用**：EAPic、防災桌遊、Inner Speech
- **生活應用**：Snap Plate 食譜識別、摺紙數學
- **社交輔助**：WingChat 社交教練

## 🎨 設計特色

### 視覺設計
- **星空背景**：營造科技感氛圍
- **科技字體**：Orbitron + Rajdhani 字體組合
- **現代配色**：藍青色調為主的科技配色方案
- **玻璃質感**：backdrop-filter 創造深度感

### 交互設計
- **平滑動畫**：按鈕懸浮、縮放效果
- **狀態反饋**：選中狀態的視覺變化
- **響應式布局**：適配不同螢幕尺寸
- **無障礙支援**：鍵盤導航和動畫偏好設定

## ⚙️ 自定義配置

### 修改專題資料

在 `templates/index.html` 中找到 `projects` 對象，可以：

```javascript
const projects = {
  '專題名稱': {
    id: 'unique-id',
    cat: 'A', // A-H 分類
    team: '組員：姓名1、姓名2',
    intro: '專題簡介文字...',
    motive: '專題動機文字...',
    desc: '專題介紹文字...'
  }
};
```

### 修改測驗問題

修改 HTML 中的問題文字和選項：

```html
<div class="section-title">你的問題</div>
<button class="btn" data-q="q1" data-v="選項值">選項文字</button>
```

### 更換背景圖片

將新圖片放入 `static/images/` 資料夾，並修改 CSS：

```css
background: url("/static/images/your-image.jpg") no-repeat center center fixed;
```

## 🔧 技術實現

### 前端技術
- **HTML5**：語義化標籤結構
- **CSS3**：Grid、Flexbox、backdrop-filter
- **JavaScript**：ES6+、DOM 操作
- **字體**：Google Fonts API

### 後端技術
- **Flask**：輕量級 Web 框架
- **Jinja2**：模板引擎

### 瀏覽器兼容性
- Chrome 88+
- Firefox 94+
- Safari 14+
- Edge 88+

## 🚀 部署指南

### 本地開發
```bash
python app.py
```

### 生產環境
推薦使用 Gunicorn：
```bash
pip install gunicorn
gunicorn -w 4 app:app
```

### Docker 部署
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["gunicorn", "-b", "0.0.0.0:5000", "app:app"]
```

## 📝 待改進功能

- [ ] 添加結果分享功能
- [ ] 加入用戶反饋系統
- [ ] 實現深色/淺色主題切換
- [ ] 添加更多動畫效果
- [ ] 支援多語言介面
- [ ] 加入資料分析儀表板

## 🤝 貢獻指南

1. Fork 此項目
2. 創建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

## 📄 授權資訊

此項目僅供學術和教育用途。請確保：
- 背景圖片的版權使用符合相關法規
- 專題資料的使用已獲得相關授權
- 字體授權符合使用條款

## 📞 聯絡資訊

如有問題或建議，請透過以下方式聯絡：
- 電子郵件：[your-email@example.com]
- GitHub Issues：[項目議題頁面]

---

*讓科技與人文在此相遇，探索無限可能的未來之旅！* 🌟
