---
title: AEM Document Security for Microsoft Office —— 發行說明
description: 在安裝AEM Document Security 6.2 Extension for Microsoft Office之前，請先閱讀版本注意事項。
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
translation-type: tm+mt
source-git-commit: 403b800eab086d131beb65a496836158778954ee
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 0%

---


# AEM Document Security for Microsoft Office —— 發行說明{#aem-document-security-for-microsoft-office-release-notes}

## AEM Document Security for Microsoft Office的新增功能{#whats-new-in-aem-document-security-for-microsoft-office}

* **支援Office 2019**:Document Security Extension for Microsoft Office已新增對Microsoft Office 2019的支援。此外，它還可與作為Office 365一部分安裝的Microsoft Office 2019案頭應用程式搭配使用。

>[!NOTE]
>
>本檔案可交替使用Adobe Experience Manager Document Security for Microsoft Office、Adobe Experience Manager Document Security Extension for Microsoft Office和Document Security Extension for Microsoft Office的術語。

## 安裝和設定AEM Document Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

此版本的Document Security Extension for Microsoft Office與Adobe LiveCycle Rights Management ES2及更新版本以及AEM表單的Document Security附加元件相容。

在安裝AEM Document Security Extension for Microsoft Office之前，請先檢閱本檔案中的資訊。 如需詳細的安裝指示，請參閱[「安裝與設定AEM Document Security Extension for Microsoft Office](installing-configuring-aemdsext.md)」文章。

## 已修正的問題 {#fixed-issues}

* 字串會垂直顯示，而內容會加上錯誤的分行符號。 (參考編號 CQ-4201054)

## 已知問題 {#known-issues}

### 不支援協力廠商外掛程式{#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office無法與協力廠商外掛程式搭配使用。 在安裝Document Security Extension for Microsoft Office之前，請先解除安裝任何Microsoft Office的協力廠商外掛程式。

### Microsoft Word、Excel和PowerPoint {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}中停用的功能表選項

AEM Document Security Extension for Microsoft Office使用內建的保護功能來保護檔案、工作表和簡報。 它會停用一些Excel、Word和PowerPoint功能表選項。

### Microsoft Office 2013、2016和2019的限制{#restrictions-for-microsoft-office}

在Microsoft Office中，受保護作業階段期間無法使用下列選項：

* Microsoft Office 2016或Microsoft Office 2019

   * 「檔案>另存新檔」
   * 「檔案>步驟記錄」
   * 「檔案>共用」
   * 「檔案>匯出」
   * 「檔案>發佈」
   * 「檔案>帳戶」
   * 「檔案>資訊>保護檔案／活頁簿／簡報>使用密碼加密」
   * 「檔案>資訊>保護檔案>新增數位簽章」
   * 「檔案>資訊>保護檔案>標示為完稿」
   * 右上角的購股權

* Microsoft Office 2013

   * 「檔案>另存新檔」
   * 「檔案>共用」
   * 「檔案>匯出」
   * 「檔案>帳戶」
   * 「檔案>資訊>保護檔案／活頁簿／簡報>使用密碼加密」
   * 「檔案>資訊>保護檔案>新增數位簽章」
   * 「檔案>資訊>保護檔案>標示為完稿」

### 從SharePoint Server {#opening-a-protected-document-from-sharepoint-server}開啟受保護的文檔

開啟受保護的檔案：如果您嘗試從SharePoint伺服器在Document Security Extension for Microsoft Office中開啟受保護的檔案，而未先開啟與檔案類型（例如Microsoft Word、Microsoft Excel或Microsoft PowerPoint）相關的Microsoft Office程式，則檔案可能無法開啟。 會顯示錯誤訊息，指出您已安裝適用的外掛程式。 因此，建議您在從SharePoint伺服器開啟Document Security Extension for Microsoft Office中受保護的檔案之前，先開啟相關的Microsoft Office程式。

（可選）建議您在Document Security Extension for Microsoft Office中從SharePoint伺服器開啟受保護的檔案之前，先清除快取資料夾。

當您從SharePoint伺服器開啟受保護的檔案時，無論套用的原則為何，檔案的所有權限都會停用。

### 在未安裝{#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}印表機的情況下，將含動態浮水印的原則套用至Microsoft Excel 2013、Microsoft Excel 2016和Microsoft Excel 2019檔案

當您在未安裝任何印表機的電腦上，將含動態浮水印的原則套用至Microsoft Excel 2013、Microsoft Excel 2016和Microsoft Excel 2019檔案，然後儲存檔案時，會出現下列錯誤：&quot;應用動態水印時出現內部錯誤。&quot; 當您重新開啟受保護的檔案時，也會出現此錯誤。 水印不會套用，且不會從「檢視>頁面配置」中顯示。

### 針對支援的Office應用程式禁用Windows資料執行預防{#disable-windows-data-execution-prevention-for-supported-office-applications}

建議您在使用Document Security Extension for Microsoft Office應用程式時停用Windows資料執行預防(DEP)設定。

### 使用Document Security Extension {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}無法保護共用的Microsoft Office檔案

當您使用Document Security Extension保護任何共用的Microsoft Office檔案時，會發生錯誤，而且共用檔案未受到保護。

### 在包含Document Security Extension for Microsoft Office和McAfee VirusScan {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}的機器上啟動Office應用程式

要確保在安裝了Document Security且啟用了McAfee VirusScan的On-Access Scan的電腦上能夠順暢地啟動Office應用程式，請禁用McAfee VirusScan控制台中的「緩衝區溢出保護」選項。

### 在具有不支援之Microsoft Office語言{#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}的機器上安裝Document Security Extension for Microsoft Office

在具有不支援語言之Microsoft Office應用程式的機器上安裝Document Security Extension for Microsoft Office之前，請至少開啟一次Office應用程式。

### 即使使用者沒有離線權限{#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions},「離線同步」按鈕仍會啟用

即使使用者沒有檔案的離線權限，「離線同步化」按鈕仍可供使用。 但是，選擇該按鈕將不起作用。

### 不支援Microsoft Office {#no-support-for-trial-versions-of-microsoft-office}試用版

Document Security extension for Microsoft Office不支援Microsoft Office的試用版。 在安裝擴充功能之前，請確定您已安裝Microsoft Office的授權副本，並且已啟動。

### 無法開啟受保護的Microsoft Office檔案{#unable-to-open-a-protected-microsoft-office-files}

如果Microsoft Office的受保護檢視已啟用，Right Management Extension無法從遠端位置開啟受保護的Microsoft Excel檔案(XLS、XLSX)和受保護的Microsoft PowerPoint(PPT)檔案。

### 包含影像或背景顏色的Microsoft Excel檔案儲存格會出現在浮水印{#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}上方

如果Microsoft Excel文檔的單元格包含影像或填充了背景顏色，並且動態水印策略應用於文檔，則填充到單元格中的影像或背景顏色將出現在水印的頂部並覆蓋水印。

### 多個憑證{#usability-issue-with-multiple-certificates}的可用性問題

如果客戶機上存在多個證書，並且用戶取消證書選擇對話框，則對話框將再次出現，用戶必須取消對話框兩次。

### Microsoft PowerPoint可讓您編輯受保護的檔案{#microsoft-powerpoint-allows-editing-protected-documents}

嘗試編輯受保護的檔案時，Microsoft PowerPoint會顯示一則訊息，「您不允許修改此檔案。 您將無法儲存您所做的變更。」 在關閉訊息後，使用者可以繼續新增文字或編輯檔案。 但是，對受保護檔案所做的變更不會儲存。

上述行為與PowerPoint 2013、PowerPoint 2016和PowerPoint 2019中的預期一樣。
