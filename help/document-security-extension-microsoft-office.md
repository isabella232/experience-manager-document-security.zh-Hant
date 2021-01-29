---
title: AEM Document Security Extension for Microsoft Office簡介
description: 使用Document Security Extension for Microsoft Office，您可以將預先定義的機密設定套用至Microsoft Office檔案。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
translation-type: tm+mt
source-git-commit: 19de0b62ac493c7507581abb607b008c64f77597
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%

---


# AEM Document Security Extension for Microsoft Office{#introduction-to-aem-document-security-extension-for-microsoft-office}簡介

Adobe® Experience Manager Document Security Extension for Microsoft® Office可確保只有您授權的人員才能使用包含智慧財產的Word、Excel和PowerPoint檔案。 使用Document Security Extension for Microsoft Office，您就可將預先定義的機密設定套用至檔案。

Document Security Extension for Microsoft Office擴充了Adobe Experience Manager Forms的LiveCycle Rights Management和Document Security附加元件，以保護Word、Excel和PowerPoint檔案，並讓已安裝此軟體的授權使用者根據原則中建立的機密設定，使用受原則保護的檔案。

## Document Security如何保護智慧財產{#how-document-security-protects-intellectual-property}

Document Security可確保只有您授權的人員才能使用包含智慧財產的檔案。 使用Document Security，您可以使用機密原則保護檔案。 *原則*&#x200B;是包含機密設定和授權使用者清單的資訊集合。 您在原則中指定的設定會決定收件者如何使用您套用原則的檔案。 例如，您可以指定收件者是可以列印、複製文字或儲存變更。

Document Security管理員和使用者建立原則。 管理員建立可供所有授權使用者使用的組織原則。 管理員或原則集協調者也可以建立名為&#x200B;*原則集*&#x200B;的原則群組，供使用者子集使用。 使用者可建立自己的原則，只有他們可以使用。 管理員、原則集協調者和使用者都可使用Document Security網頁來建立原則。

雖然原則儲存在Document Security中，但您仍可透過Word、Excel或PowerPoint將原則套用至檔案。 將原則套用至檔案時，檔案包含的資訊會受到原則中指定的機密設定保護。 當您分發受原則保護的檔案時，只有經過原則授權的收件者才能存取檔案的內容。

使用原則保護檔案可讓您持續控制該檔案，即使在您分發檔案後亦然。 您可以稽核事件來追蹤收件者使用檔案的時間和方式、變更原則、防止使用者繼續存取檔案，以及變更檔案所附加的原則。

## 策略的運作方式{#how-policies-work}

原則包含授權使用者的相關資訊以及要套用至智慧財產的機密設定。 使用者可以是Document Security透過連結的LDAP或Active Directory清單中內含項目識別的任何使用者。 使用者也可以是受邀向Document Security註冊或管理員為其建立帳戶的人員。

原則中的機密設定會決定收件者如何使用受原則保護的檔案。 例如，原則會指定收件者是否可列印檔案、將內容複製到其他檔案，或儲存對受保護檔案的變更。 策略還可以為各種用戶指定不同的機密設定。

將原則套用至檔案時，檔案包含的資訊會受到原則中指定的機密設定保護。 當您分發檔案時，Document Security會驗證嘗試開啟檔案的收件者，並根據原則中指定的權限授與存取權。

將原則套用至檔案後，可隨時變更原則的機密設定，讓您新增或移除已授權的使用者，或在使用者收到檔案後變更其權限。 可以更改應用於檔案的策略，並可以撤銷對檔案的訪問，以便擁有檔案副本的任何人都不能再開啟該檔案。

如果原則允許離線存取，收件者也可以在原則中指定的時段離線使用受原則保護的檔案（沒有作用中的網際網路或網路連線）。

## 受原則保護檔案的運作方式{#how-policy-protected-files-work}

若為要開啟和使用受原則保護之Word、Excel和PowerPoint檔案的使用者，原則必須將使用者納入為收件者或允許匿名存取，且使用者必須已安裝Document Security Extension for Microsoft Office。 若要將受原則保護的檔案提供給沒有Document Security Extension for Microsoft Office的使用者，請提供軟體副本或告知他們如何從您的網站下載。 如果您沒有安裝程式，則可從[下載頁面](https://www.adobe.com/products/livecycle/rightsmanagement/extension/downloads.html)下載。

當使用者嘗試開啟受原則保護的檔案時，Document Security Extension for Microsoft Office會連線至Document Security以驗證使用者。 如果Document Security已設定為稽核檔案使用情形，使用者會看到通知，指出正在稽核檔案使用情形。 Document Security會決定授與使用者的檔案權限，然後使用者可以根據原則設定，在下列情況下使用檔案：

* 對於策略中指定的有效期。
* 在管理員或套用原則的人員廢止檔案的存取權或變更原則之前。

   如果套用原則的人員變更原則或廢止檔案的存取權，即使使用者已擁有檔案，使用者對檔案的權限也會變更或移除。 如果檔案本身已撤銷，則可提供URL給使用者以取得更新的復本。

   如果原則允許離線存取，則可在原則中指定的離線租用期間離線開啟受原則保護的檔案（沒有網際網路或網路連線）。 離線租用期間結束時，使用者必須上線並與Document Security同步，Document Security會啟動新的租用期間。

   如果原則允許儲存檔案，而使用者儲存受原則保護檔案的副本，則會自動套用並強制儲存的檔案使用原則。 也會檢查並記錄與原始檔案相同的事件，例如嘗試開啟新檔案。

## 使用Document Security保護您的檔案{#using-document-security-to-protect-your-files}

您可以在各種情況下使用原則來保護檔案。

例如，製造商接受將為新產品提供部件的供應商的投標。 製造商必須向投標者提供其完成提交所需的專有資訊。 製造商使用Document Security來保護檔案，其原則允許投標者開啟檔案並檢視資訊。 但是，投標者無法變更、列印或複製檔案，而沒有權限的任何人也無法開啟檔案。

在接受其中一個競標後，製造商會更新原則，以授與成功競標者在本機列印、複製和儲存變更的權限，並移除不成功的競標者，以便他們不再擁有開啟檔案的權限。

在與成功競標者合作時，製造商的工程師會變更檔案中的部分設計規格。 為發佈新規格，製造商會廢止部分檔案的存取權並發佈新版本。 當成功競標者的工程師嘗試開啟檔案時，他們會看到訊息，表示檔案的存取權已撤銷。 訊息包含URL，供他們下載新檔案版本。

## 其他資訊 {#additional-information}

此表格中的資源可協助您進一步瞭解AEM Document Security:

<table >
 <tbody>
  <tr>
   <th><p>如需相關資訊</p> </th>
   <th><p>請參閱</p> </th>
  </tr>
  <tr>
   <td><p>AEM Forms Administrator說明</p> </td>
   <td><p><a href="http://www.adobe.com/go/learn_aemforms_admin_65">管</a> 理員說明，在Document Security管理頁面上，按一下頁面右上角的「說明」連結。</p> </td>
  </tr>
  <tr>
   <td><p>修補程式更新、技術說明，以及有關此產品版本的其他資訊</p> </td>
   <td><p><a href="https://helpx.adobe.com/tw/marketing-cloud/contact-support.html">Marketing Cloud技術支援</a></p> </td>
  </tr>
 </tbody>
</table>

