---
title: Microsoft&reg；的AEM Document Security Extension簡介辦公室
description: 使用Microsoft&reg；的檔案安全性擴充功能Office，您可以將預先定義的機密設定套用至您的Microsoft&reg;辦公室檔案。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: f3456fa7243405a4986ac50540f8b578a6412a6c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 67%

---

# Microsoft® Office的AEM Document Security Extension簡介{#introduction-to-aem-document-security-extension-for-microsoft-office}

Microsoft® Office 適用的 Adobe® Experience Manager Document Security Extension 可確保，只有您授權的人才能使用含有您智慧財產的 Word、Excel 和 PowerPoint 檔案。使用Microsoft® Office的Document Security Extension，您可以將預先定義的機密設定套用至您的檔案。

Microsoft® Office的Document Security Extension擴展了Adobe Experience Manager Forms的LiveCycleRights Management和Document Security附加元件，以保護Word、Excel和PowerPoint檔案，並允許安裝了此軟體的授權用戶根據策略中建立的機密設定使用受策略保護的檔案。

## Document Security 如何保護智慧財產 {#how-document-security-protects-intellectual-property}

文檔安全確保只有您授權的人員才能使用包含您智慧財產權的檔案。 使用 Document Security，即可以透過使用機密性原則來保護檔案。*原則*&#x200B;是包含機密性設定和授權用戶清單的資訊集合。您在原則中指明的設定可確定收件者如何使用您套用原則的檔案。例如，您可以指明收件人是否可以列印或複製文字或儲存變更。

Document Security 管理員和用戶會建立原則。管理員會建立適用於所有授權用戶的組織原則。管理員或原則組專員也可建立稱為&#x200B;*原則組*&#x200B;且適用於部分用戶的原則群組。用戶可以建立他們自己可以使用的原則。管理員、原則組專員和用戶會使用 Document Security 網頁來建立原則。

雖然原則是儲存在 Document Security 上，但是您可以透過 Word、Excel 或 PowerPoint 套用於檔案中。當您將原則套用於檔案時，檔案所含資訊將受到原則所指明的機密性設定的保護。分發受策略保護的檔案時，只有受策略授權的收件人才能訪問檔案的內容。

使用原則來保護檔案，可以讓您持續控制該檔案，即使在分發文件之後也是如此。您可以稽核事件以追蹤收件人何時及如何使用您的檔案、變更原則、防止用戶繼續存取檔案，以及變更附加至檔案的原則。

## 原則如何運作 {#how-policies-work}

原則包含有關授權用戶的資訊，以及套用至智慧財產的機密性設定。用戶可以是透過包含在已連結的 LDAP 或 Active Directory 列表內而被 Document Security 辨識的任何用戶。用戶也可以是被邀請註冊 Document Security 的人，或管理員為他們建立帳戶的人。

原則中的機密性設定可確定收件人如何使用受該原則保護的檔案。例如，原則會指明收件人是否能列印檔案、將內容複製到其他檔案，或是否可儲存變更至受保護的檔案。原則還可以為不同用戶指明不同的機密性設定。

當您將原則套用於檔案時，檔案所含資訊將受到原則所指明的機密性設定的保護。當您分發文件時，Document Security 會對嘗試開啟檔案的收件人進行驗證，並根據原則中指定的權限來授權存取權。

將策略應用到檔案後，可隨時更改策略的機密設定。 這樣可讓您新增或移除已授權的使用者，或在使用者收到檔案後變更其權限。 套用至檔案的原則可以變更，且檔案的存取權可以撤銷，這樣擁有該文檔案副本的任何人都無法再開啟。

如果原則准許離線存取，則收件人也可以在原則指定的時限內離線使用受原則保護的檔案 (沒有有效網際網路或網絡連線)。

## 受原則保護的檔案如何運作 {#how-policy-protected-files-work}

要使用戶開啟和使用受策略保護的Word、Excel和PowerPoint檔案，該策略必須將該用戶作為接收者或允許匿名訪問。此外，使用者必須安裝Microsoft® Office的Document Security Extension。 若要將受策略保護的檔案提供給沒有Microsoft® Office的Document Security Extension的人，請為他們提供軟體副本，或告訴他們如何從您的網站下載該軟體。 如果您沒有安裝程序，可以從 [下載頁面](https://experienceleague.adobe.com/docs/experience-manager-document-security/using/download-installer.html?lang=en)下載。

當用戶嘗試開啟受策略保護的檔案時，Microsoft® Office的Document Security Extension會連接到Document Security以驗證用戶。 如果將 Document Security 設為稽核檔案使用情況，則用戶會看到通知並指明正在稽核檔案使用情況。文件全性會確定授予用戶哪些檔案權限，然後用戶可以根據原則設定使用檔案，但前提為：

* 在原則中指定的有效期限。
* 直到管理員或套用原則的人撤銷檔案存取權或變更原則為止。

   如果應用策略的人更改了策略或撤消了對檔案的訪問，則即使用戶已擁有該檔案，用戶對該檔案的權限也會更改或刪除。 如果檔案本身被撤銷，用戶可能會收到 URL 以取得更新版本。

   如果策略允許離線訪問，則可以在策略中指定的離線租用期間離線開啟受策略保護的檔案（沒有網際網路或網路連接）。 在離線租期結束時，用戶必須上線並與 Document Security 同步處理，這樣便會展開新的租期。

   如果原則允許儲存檔案，且用戶儲存一份受原則保護的檔案，則該原則將自動套用於已儲存的檔案並強制執行。活動 (例如嘗試開啟新檔案的活動) 也將與原始檔案一樣進行稽核和記錄。

## 使用 Document Security 來保護您的檔案 {#using-document-security-to-protect-your-files}

您可在各種情況下使用原則來保護檔案。

例如，製造商接受為新產品提供部件的供應商的出價。 製造商必須向投標人提供專有資訊，以完成其提交。 生產商可使用 Document Security 的原則來保護檔案；該原則是用來允許投標者開啟文件並查看資訊。但是，投標者將無法變更、列印或複製檔案；如果沒有權限，任何人都無法開啟檔案。

在接受其中一項標價後，生產商將更新原則以便為得標者提供權限，讓他們可從本機列印、複製和儲存任何變更內容；同時，生產商會移除非得標者，讓他們再無權限開啟檔案。

與中標者合作時，製造商的工程師會變更檔案中的部分設計規格。 為了發布新規格，生產商會撤銷部分檔案的存取權並發布新版本。當得標者的工程師嘗試開啟檔案時，他們會看到一個訊息指出檔案存取權已被撤銷。這個訊息含有一個 URL，讓他們下載檔案的新版本。

## 其他資訊 {#additional-information}

下表資源可以幫助您了解更多有關 AEM Document Security：

<table >
 <tbody>
  <tr>
   <th><p>關於後述資訊：</p> </th>
   <th><p>請參閱</p> </th>
  </tr>
  <tr>
   <td><p>AEM Forms 管理員說明</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/docs/experience-manager-65/forms/administrator-help/get-started/configure-general-aem-forms-settings.html?lang=en">管理員說明</a>，或在「Document Security」管理頁面上，按一下頁面右上角的「說明」連結。</p> </td>
  </tr>
  <tr>
   <td><p>Patch 更新、技術提示，以及有關此產品版的其他資訊</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home#support">Experience Cloud技術支援</a></p> </td>
  </tr>
 </tbody>
</table>
