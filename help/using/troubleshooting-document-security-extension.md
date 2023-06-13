---
title: 疑難排解 Microsoft Office 適用的 AEM Document Security Extension
description: 如果在安裝、設定或使用 Microsoft Office 適用的 AEM Document Security Extension 時遇到問題，請按照本文件所列的說明進行操作。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

---

# 疑難排解 Microsoft Office 適用的 AEM Document Security Extension{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## 安裝和設定問題疑難排解 {#troubleshootinginstallationandconfiguration}

如果在安裝和設定 Microsoft Office 適用的 AEM Document Security Extension 時遇到問題，在安裝之前，請確保仔細按照「[安裝](installing-configuring-aemdsext.md)」文章一節的說明進行。

如果您是根據文件說明安裝並設定所有內容，請查看以下各節來解決與您所遇到類似的問題。

### Microsoft Office 應用程式無法載入 Document Security Extension {#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows 登錄中的 LoadBehavior 屬性會指定 Document Security 外掛程式的執行階段行為。如果 LoadBehavior 屬性設定為 3，則所有外掛程式會自動載入。在安裝 Microsoft Office 適用的 Document Security Extension 以前，請確保將 LoadBehavior 屬性值設定為 3。

1. 在進行變更前，請備份 Windows 登錄。若需要詳細的說明，請參閱 [如何修改 Windows 登錄](https://support.microsoft.com/en-us/kb/136393)。
1. 在「登錄編輯程式」中，瀏覽至 HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin or HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM。
1. 將 **LoadBehavior** 屬值設定為 3。

1. 關閉登錄編輯程式。

若要了解 LoadBehavior 詳細資訊，請參閱 [VSTO 增益集的登錄項目](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior) 文章。

## 疑難排解系統管理工作 {#admintasks}

本節討論已安裝的 AEM Document Security Extension 的可能問題。

### 在安裝 Document Security Extension 時，Microsoft Office 應用程式無法順利啟動 {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

為確保已經安裝 Document Security Extension 並且啟用 McAfee VirusScan 常駐掃描的電腦可以順利啟動 Office 應用程式，請至 McAfee VirusScan 主控台停用「緩衝區溢位保護」選項。
