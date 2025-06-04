# Trading Strategy Generator
使用深度學習和技術分析工具的自動交易策略生成與回測系統。本專案支持從 Binance 獲取市場數據，訓練基於 LSTM 的策略模型，並進行策略回測與績效評估。
---
## **功能特點**
- 從 Binance 自動抓取歷史數據
- 使用技術指標進行特徵工程（RSI、MACD、SMA 等）
- 基於 LSTM 模型的交易策略分類（Buy, Hold, Sell）
- 支援回測和績效指標計算（例如最大回撤和 Sharpe 比率）
---
## **安裝指南**
### **1. 環境準備**
確保你已安裝以下軟體：
- Python 3.8 或以上版本
- pip 套件管理工具
### **2. 克隆專案**
```bash
git clone https://github.com/your-username/trading-strategy-generator.git
cd trading-strategy-generator
```
### **3. 安裝依賴**
建議使用虛擬環境來管理依賴：
```bash
python -m venv env
source env/bin/activate  # Windows: env\Scripts\activate
pip install -r requirements.txt
```---
## **使用方式**
### **1. 訓練模型**
運行以下命令以抓取數據並訓練模型：
```bash
python strategy_generator.py
```
成功後，模型將儲存在 `models/strategy_generator_lstm.h5` 中。
### **2. 生成交易信號**
使用訓練好的模型產生交易信號：
```bash
python signal_generator.py
```
結果將顯示在終端，並生成對應的信號 DataFrame。
### **3. 回測策略**
運行回測引擎以評估策略表現：
```bash
python backtest_engine.py
```
結果將存儲於 `backtest_result.csv`，並顯示績效曲線。
### **4. 績效評估**
查看回測結果並計算績效指標：
```bash
python performance_analyzer.py
```
指標（總回報率、最大回撤、Sharpe 比率）將顯示於終端。
---
## **專案結構**
```
trading-strategy-generator/
├── data/                       # 數據抓取與處理模組
│   └── data_fetcher.py         # Binance 數據獲取與特徵工程
├── models/                     # 訓練後的模型存放路徑
├── strategy_generator.py       # 策略生成與模型訓練
├── signal_generator.py         # 訊號生成模組
├── backtest_engine.py          # 回測引擎
├── performance_analyzer.py     # 績效分析模組
├── requirements.txt            # 依賴列表
└── README.md                   # 專案說明文件
```
---
## **未來計畫**
- 支援更多技術指標
- 提升模型泛化能力（引入 Transformer 模型）
- 支援即時交易執行與監控
---
## **版權聲明**
本專案基於 [MIT License](LICENSE) 授權。使用時請註明原始作者。
