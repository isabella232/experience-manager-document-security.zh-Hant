---
title: 疑難排解 Microsoft Office 適用的 AEM Document Security Extension
description: 如果在安裝、設定或使用 Microsoft Office 適用的 AEM Document Security Extension 時遇到問題，請按照本文件所列的說明進行操作。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
translation-type: ht
source-git-commit: ac26ec61f62d7a3db2429c8a9d3f68b82ba8f77a
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

---


# 疑難排解 Microsoft Office 適用的 AEM Document Security Extension{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## 疑難排解安裝和設定問題 {#troubleshootinginstallationandconfiguration}

如果在安裝和設定 Microsoft Office 適用的 AEM Document Security Extension 時遇到問題，在安裝之前，請確保仔細按照「[安裝](installing-configuring-aemdsext.md)」文章一節的說明進行。

如果您是根據文件說明安裝並設定所有內容，請查看以下各節來解決與您所遇到類似的問題。

### 無法為 Microsoft Office 應用程式載入 Document Security Extension {#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows 登錄中的 LoadBehavior 屬性會指定 Document Security 外掛程式的執行階段行為。如果 LoadBehavior 屬性設定為 3，則所有外掛程式會自動載入。在安裝 Microsoft Office 適用的 Document Security Extension 以前，請確保將 LoadBehavior 屬性值設定為 3。

1. 在進行變更前，請備份 Windows 登錄。若需要詳細的說明，請參閱 [如何修改 Windows 登錄](https://support.microsoft.com/en-us/kb/136393)。
1. 在「登錄編輯程式」中，瀏覽至 HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin or HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM。
1. 將 **LoadBehavior** 屬值設定為 3。

1. 關閉登錄編輯程式。

若要了解 LoadBehavior 詳細資訊，請參閱 [VSTO 增益集的登錄項目](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior) 文章。

## 疑難排解系統管理工作 {#admintasks}

本節將討論已安裝 AEM Document Security Extension 的可能問題。

### 在安裝 Document Security Extension 時，Microsoft Office 應用程式不會順利啟動 {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

若電腦有已安裝的 Document Security Extension，並有已啟用即時 (On-Access) 掃描的 McAfee VirusScan，為了確保此電腦能順利啟動 Office 應用程式，請停用 McAfee VirusScan 控制台中的「緩衝區溢位保護」選項。
