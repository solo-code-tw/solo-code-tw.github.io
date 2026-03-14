---
title: "專案筆記：Windows 系統監測開發實錄"
date: 2026-03-14
description: "關於 RemoteDesktopWatch 專案中 DXGI 畫面擷取的技術細節。"
tags: ["C++", "Windows API", "開發日記"]
categories: ["技術"]
image: "/images/taipei-work.jpg" # 如果你有放圖片的話
draft: false
---

## 🚀 今日開發進度
今天在台北漢來飯店的辦公桌前，重新整理了關於遠端桌面畫面擷取的邏輯。

### 1. 核心代碼片段
使用 DXGI 進行畫面擷取時，這段邏輯是關鍵：

```cpp
// 範例：取得輸出設備
IDXGIOutput* pOutput = nullptr;
hr = pAdapter->EnumOutputs(0, &pOutput);
if (SUCCEEDED(hr)) {
    // 這裡處理後續的擷取邏輯
    std::cout << "Successfully connected to output device." << std::endl;
}
