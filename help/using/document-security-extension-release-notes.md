---
title: Microsoft Office 適用的 AEM Document Security Extension - 版本注意事項
description: 在安裝 Microsoft Office 適用的 AEM Document Security 6.2 Extension，請閱讀版本注意事項。
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: ht
source-wordcount: '1051'
ht-degree: 100%

---

# Microsoft Office 適用的 AEM Document Security Extension - 版本注意事項{#aem-document-security-for-microsoft-office-release-notes}

## Microsoft Office 適用的 AEM Document Security 新增功能 {#whats-new-in-aem-document-security-for-microsoft-office}

* **Office 2019 的支援服務**：Microsoft Office 適用的 Document Security Extension 新增了 Microsoft Office 2019 所需支援。此項支援應該適用於安裝成為 Office 365 一部分的 Microsoft Office 2019 桌面應用程式。

>[!NOTE]
>
>本文件會交換使用以下用語：Microsoft Office 適用的 Adobe Experience Manager Document Security、Microsoft Office 適用的 Adobe Experience Manager Document Security Extension，以及 Microsoft Office 適用的 Document Security Extension。

## 安裝和設定 Microsoft Office 適用的 AEM Document Security Extension {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

本版本 Microsoft Office 適用的 Document Security Extension 相容於 Adobe LiveCycle Rights Management ES2 或以上版本，以及 AEM Forms 適用的 Document Security 附加元件。

在安裝 Microsoft Office 適用的 AEM Document Security Extension 以前，請閱讀本文件資訊。有關詳細的安裝指示，請參閱 [安裝和設定 Microsoft Office 適用的 AEM Document Security Extension](installing-configuring-aemdsext.md) 文章。

## 已修正的問題 {#fixed-issues}

* 垂直顯示的字串和錯誤的分行符號已新增至內容中。(參考編號 CQ-4201054)

## 已知問題 {#known-issues}

### 不支援協力廠商的外掛程式 {#third-party-plug-ins-not-supported}

Microsoft Office 適用的 AEM Document Security Extension 不適用於協力廠商的外掛程式。在安裝 Microsoft Office 適用的 Document Security Extension 以前，先解除安裝 Microsoft Office 適用的協力廠商外掛程式。

### Microsoft Word、Excel 和 PowerPoint 中已停用的選單選項 {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

Microsoft Office 適用的 AEM Document Security Extension 使用內建的保護功能，可保護文件、活頁簿和簡報。此功能會停用一些 Excel 、Word 和 PowerPoint 功能表選項。

### Microsoft Office 2013、2016 和 2019 的限制 {#restrictions-for-microsoft-office}

在 Microsoft Office 中，以下選項在受保護工作階段中均無法使用：

* Microsoft Office 2016 或 Microsoft Office 2019

   * 檔案 > 另存新檔
   * 檔案 > 歷程記錄
   * 檔案 > 共用
   * 檔案 > 匯出
   * 檔案 > 發佈
   * 檔案 > 帳戶
   * 檔案 > 資訊 > 保護文件/活頁簿/簡報 > 以密碼加密
   * 檔案 > 資訊 > 保護文件 > 新增數位簽名
   * 檔案 > 資訊 > 保護文件 > 標示為完稿
   * 右上方的共用選項

* Microsoft Office 2013

   * 檔案 > 另存新檔
   * 檔案 > 共用
   * 檔案 > 匯出
   * 檔案 > 帳戶
   * 檔案 > 資訊 > 保護文件/活頁簿/簡報 > 以密碼加密
   * 檔案 > 資訊 > 保護文件 > 新增數位簽名
   * 檔案 > 資訊 > 保護文件 > 標示為完稿

### 開啟 SharePoint 伺服器的受保護文件 {#opening-a-protected-document-from-sharepoint-server}

開啟受保護的文件：嘗試從 SharePoint 伺服器 Microsoft Office 適用的 Document Security Extension 中開啟受保護的文件時，而不開啟與該檔案類型有關聯的 Microsoft Office 程式 (如 Microsoft Word、Microsoft Excel 或 Microsoft PowerPoint) 時，該文件可能不會開啟。錯誤訊息顯示您安裝了適用的外掛程式。因此，從 SharePoint 伺服器 Microsoft Office 適用的 Document Security Extension 中開啟受保護的文件以前，建議您要先開啟相關的 Microsoft Office 程式。

(選項) 從 SharePoint 伺服器 Microsoft Office 適用的 Document Security Extension 中開啟受保護的文件以前，建議您要先清除快取檔案夾。

當您從 SharePoint 伺服器開啟受保護的文件時，不論是否套用原則，文件上所有權限皆為停用狀態。

### 套用一項原則，在未安裝印表機的情況下，對 Microsoft Excel 2013、Microsoft Excel 2016 和 Microsoft Excel 2019 檔案套用附動態浮水印 {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

當您在未安裝印表機的電腦上，針對 Microsoft Excel 2013、Microsoft Excel 2016 和 Microsoft Excel 2019 檔案套用附動態浮水印的原則，會出現下列錯誤：「套用動態浮水印時發生內部錯誤。」當您重新開啟受保護檔案時，也會出現此錯誤。浮水印未套用，且在「檢視 > 頁面配置」無法看見。

### 停用所支援 Office 應用程式適用的 Windows 資料執行防止 {#disable-windows-data-execution-prevention-for-supported-office-applications}

在使用 Microsoft Office 應用程式適用的 Document Security Extension 時，建議您停用 Windows 資料執行防止 (DEP)。

### 使用 Document Security Extension 無法保護共用的 Microsoft Office 檔案 {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

當您使用 Document Security Extension 保護任何共用的 Microsoft Office 檔案時，發生錯誤且未保護到共用的檔案。

### 在含有 Microsoft Office 適用的 Document Security Extension 和 McAfee VirusScan 的電腦中啟動 Office 應用程式 {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

為確保已經安裝 Document Security 並且啟用 McAfee VirusScan 常駐掃描的電腦可以順利啟動 Office 應用程式，請至 McAfee VirusScan 主控台停用「緩衝區溢位保護」選項。

### 在含有不受支援的 Microsoft Office 語言的電腦上安裝 Microsoft Office 適用的 Document Security Extension {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

電腦上安裝的 Microsoft Office 應用程式若含有不受支援的語言，在安裝 Microsoft Office 適用的 Document Security Extension 以前，要先開啟 Office 應用程式至少一次。

### 即使用戶沒有離線權限，「離線同步處理」按鈕仍會啟用 {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

即使用戶沒有文件的離線權限，也可以使用「離線同步處理」按鈕。但是，選取按鈕不會起任何作用。

### 不支援 Microsoft Office 試用版 {#no-support-for-trial-versions-of-microsoft-office}

Microsoft Office 適用的 Document Security Extension 不支援試用版的 Microsoft Office。在安裝此擴充功能以前，請確保您已安裝授權版的 Microsoft Office 且將其啟用。

### 無法開啟受保護的 Microsoft Office 檔案 {#unable-to-open-a-protected-microsoft-office-files}

如果已啟用 Microsoft Office 的受保護檢視，則 Right Management Extension 無法開啟遠端位置的受保護 Microsoft Excel 檔案 (XLS、XLSX) 和受保護 Microsoft PowerPoint (PPT) 檔案。

### 含有影像或背景顏色的 Microsoft Excel 文件儲存格會出現在浮水印上方 {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

如果 Microsoft Excel 文件儲存格含有影像或填滿背景顏色，而且文件已套用動態浮水印原則，則該儲存格的影像或填滿的背景顏色將顯示在浮水印上方並遮蓋浮水印。

### 多個憑證的可用性問題 {#usability-issue-with-multiple-certificates}

如果用戶端電腦上存在多個憑證，而用戶取消憑證選取對話方塊，則該對話方塊會再次出現，用戶必須取消對話方塊兩次。

### Microsoft PowerPoint 允許編緝受保護的文件 {#microsoft-powerpoint-allows-editing-protected-documents}

在嘗試編輯受保護的文件時，Microsoft PowerPoint 將顯示訊息：「您無權修改此文件。」您無法儲存您的變更。」訊息關閉後，用戶可以繼續新增文字或編輯文件。但是，受保護文件所做的變更無法儲存。

PowerPoint 2013、PowerPoint 2016 和 PowerPoint 2019 會產生上述行為。
