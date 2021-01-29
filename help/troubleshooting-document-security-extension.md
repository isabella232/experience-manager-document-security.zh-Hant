---
title: 疑難排解AEM Document Security Extension for Microsoft Office
description: 如果您在安裝、設定或使用AEM Document Security Extension for Microsoft Office時遇到問題，請依照本檔案中的指示進行。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
translation-type: tm+mt
source-git-commit: ac26ec61f62d7a3db2429c8a9d3f68b82ba8f77a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# 疑難排解AEM Document Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## 安裝和配置問題疑難排解{#troubleshootinginstallationandconfiguration}

如果您在安裝和設定AEM Document Security Extension for Microsoft Office時遇到問題，請務必小心遵循[installation](installing-configuring-aemdsext.md)文章中——之前——一節中所列的指示。

如果您根據說明檔案安裝並設定了所有項目，請檢閱下列章節，以瞭解與您所遇到的問題類似的問題。

### Document Security Extension無法載入Microsoft Office應用程式{#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows註冊表中的LoadBehavior屬性可指定文檔安全插件的運行時行為。 如果LoadBehavior屬性設為3，則會自動載入所有外掛程式。 在安裝Document Security Extension for Microsoft office之前，請確定LoadBehavior屬性的值設定為3。

1. 在對Windows註冊表進行更改之前，請對其進行備份。 有關詳細說明，請參見[如何修改Windows註冊表](https://support.microsoft.com/en-us/kb/136393)。
1. 在註冊表編輯器中，導航toHKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin或HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM。
1. 將&#x200B;**LoadBehavior**&#x200B;屬性的值設為3。

1. 關閉註冊表編輯器。

如需LoadBehavior的詳細資訊，請參閱[VSTO增益集的註冊表項目](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior)文章。

## 管理任務疑難排解{#admintasks}

本節討論您所安裝的AEM Document Security Extension的可能問題。

### 在安裝Document Security Extension {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}時，Microsoft Office應用程式無法順暢地開始

要確保在安裝了Document Security Extension並啟用了McAfee VirusScan的On-Access Scan的電腦上，Office應用程式能夠順利啟動，請禁用McAfee VirusScan控制台中的緩衝區溢出保護選項。
