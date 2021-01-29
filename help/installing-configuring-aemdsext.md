---
title: 安裝與設定AEM Document Security Extension for Microsoft Office
description: 本檔案會引導您完成Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office的安裝與設定。
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
translation-type: tm+mt
source-git-commit: ac385c538cdd7d3bb4772b92ee7a94b003595f56
workflow-type: tm+mt
source-wordcount: '2796'
ht-degree: 0%

---


# 安裝和設定AEM Document Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

本檔案會引導您完成Adobe Experience Manager Document Security Extension for Microsoft Office的安裝與設定。

本檔案包含下列工作的相關資訊：

* 安裝Document Security Extension for Microsoft Office
* 預先設定安裝程式，以指向LiveCycle Rights Management ES2或更新版本，或AEM 6.0 Forms或更新版本的Document Security附加元件。
* 配置預設策略的自動應用程式

## 安裝之前 {#before-you-install}

在安裝Document Security Extension for Microsoft Office之前，請確定：

* 您已閱讀[發行說明](document-security-extension-release-notes.md)。
* Microsoft Office已啟動。 在開啟Microsoft Office應用程式時，不會出現啟動對話方塊。
* 已安裝Microsoft Windows和Microsoft Office的最新Service Pack。
* 如果您要針對不支援的語言安裝Document Security for Microsoft Office，請至少開啟Office應用程式一次。

>[!NOTE]
>
>請勿將軟體安裝在名稱包含雙位元組字元的檔案夾中。 如果您這麼做，AEM Document Security功能表不會出現在Microsoft Office中。

>[!NOTE]
>
>支援在64位元作業系統上安裝32位元版本的Document Security擴充功能，但不支援相反的方式。 您無法在32位元作業系統上安裝64位元版本的Document Security Extension for Microsoft Office。

### 禁用McAfee VirusScan和{#disable-mcafee-virusscan}

要確保在安裝了Document Security Extension並啟用了McAfee VirusScan的On-Access Scan的電腦上，Office應用程式能夠順利啟動，請禁用McAfee VirusScan控制台中的緩衝區溢出保護選項。

### 解除安裝協力廠商增效模組{#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office不支援Microsoft Office應用程式的協力廠商外掛程式。 由於此擴充功能與協力廠商外掛程式衝突，請先解除安裝任何非Adobe的Microsoft Office外掛程式，然後再安裝Document Security for Microsoft Office。 Adobe不支援安裝協力廠商外掛程式的Document Security for Microsoft Office應用程式。

## 系統要求{#system-requirements}

### Document Security Extension Client {#document-security-extension-client}

請確定您要安裝Document Security Extension的下列最低組態：

* 32位元或64位元版本的Microsoft Windows 7或Windows 10，英文、法文、德文、日文、義大利文、西班牙文、巴西葡萄牙文、韓文、簡體中文或繁體中文。
   **注意： Microsoft** *Office的Document安全性擴充功能也預期可在Microsoft Surface裝置上運作。*

* 32位元或64位元版本的Microsoft Office 2013、2016、2019和Microsoft Office案頭應用程式，以英文、法文、德文、日文、義大利文、西班牙文、巴西葡萄牙文、韓文、簡體中文或繁體中文安裝為Office 365的一部分。

   **注意**: *AEM Document Security Extension for Microsoft Office不支援Microsoft Office應用程式的協力廠商外掛程式。由於此擴充功能可能與協力廠商增效模組衝突，因此在安裝Document Security Extension for Microsoft Office之前，必須先解除安裝任何非Adobe Office應用程式的增效模組。 Adobe不支援安裝協力廠商外掛程式的Document Security Extensions for Microsoft Office應用程式。*

* 1.3 GHz或以上的處理器
* 2GB的記憶體
* 100 MB可用硬碟空間

### 文件安全性 {#document-security}

若要使用Document Security Extension，請確定您能夠連線至Adobe LiveCycle Rights Management ES2及更新版本，或AEM 6.0表單的Document Security附加元件或更新版本。

## 安裝Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

您可以從[下載頁面](download-installer.md)下載安裝程式。 您無法直接自訂安裝程式可執行檔，但可以以互動方式或無訊息模式安裝。 要安裝軟體，請以管理員身份登錄Windows。

Microsoft Office的32位元和64位元版本提供個別的安裝程式。 若是32位元版本的Microsoft Office，請下載DocumentSecurityExtensionforMicrosoftOffice.exe。 若為64位元版本的Microsoft Office，請下載DocumentSecurityExtensionforMicrosoftOffice64.exe。

>[!NOTE]
>
>本檔案使用32位元安裝程式檔(DocumentSecurityExtensionforMicrosoftOffice.exe)來說明各種命令和選項。 如果您使用64位元版本的Microsoft Office，請使用64位元安裝程式檔案(DocumentSecurityExtensionforMicrosoftOffice64.exe)來執行本檔案所列的作業。

### 以靜默模式安裝{#install-in-silent-mode}

使用檔案解壓縮公用程式（例如WinZip），從安裝程式檔案解壓縮`DocumentSecurityExtensionforMicrosoftOffice.exe`。 開啟命令提示符，轉到包含設定檔案的資料夾，然後鍵入以下文本：

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

此安裝程式也提供MSI檔案，可用於自訂。

### 以靜默模式{#install-an-msi-file-in-silent-mode}安裝MSI檔案

1. 使用檔案解壓縮公用程式（例如WinZip），從ZIP檔案解壓縮`DocumentSecurityExtensionforMicrosoftOffice.msi`檔案。

1. 開啟命令提示，前往包含MSI檔案的資料夾，然後輸入下列文字：

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## 預先設定安裝程式以連線至Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

您可以預先設定Document Security Extension for Microsoft Office安裝程式，使其指向LiveCycle或AEM伺服器，讓安裝Document Security Extension for Microsoft Office的使用者可以使用這些功能，而不需設定連線。 因此，使用者可以開啟受保護的檔案，而不需進行任何設定。 但是，除非將客戶端配置為使用特定伺服器，否則無法保護新文檔。

下列步驟說明如何建立和設定MSI檔案。 此MSI檔案包含預先設定Document Security Extension for Microsoft Office安裝程式至您企業中安裝之LiveCycle或AEM伺服器時所需的登錄值。

### 自訂安裝程式{#prerequisites-for-customizing-the-installer}的必要條件

使用Orca資料庫編輯器自訂安裝程式。 下列步驟說明如何使用Orca資料庫編輯器修改MSI安裝檔案的復本，以建立自訂MSI檔案。 Orca目前隨附於Windows SDK for Windows Server 2008和。NET Framework 3.5。如需如何使用Orca編輯Microsoft Windows® Installer檔案的詳細資訊，請參閱[Microsoft支援](http://support.microsoft.com/kb/255905/EN-US/)。

>[!NOTE]
>
>建議您在建立自訂MSI檔案之前，先對所有安裝程式檔案進行完整備份。

#### 安裝Orca {#install-orca}

1. 從[Microsoft下載中心](http://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=11310)下載Windows SDK for Windows Server 2008和。NET Framework 3.5。
1. 連按兩下\Microsoft SDK\bin檔案夾中的Orca.msi檔案。

   您也需要安裝程式檔案的MSI變體。 請聯絡Adobe支援以取得最新版的MSI安裝程式。

   >[!NOTE]
   >
   >在執行安裝程式之前，請務必先關閉DocumentSecurityExtensionforMicrosoftOffice.msi檔案。 如果Orca使用MSI檔案，則無法執行安裝程式。

### 建立並配置MSI檔案{#create-and-configure-the-msi-file}

1. 按一下「開始>程式集> Orca ]**」。**[!UICONTROL 

1. 按一下「**[!UICONTROL 檔案>開啟]**」，然後瀏覽至`DocumentSecurityExtensionforMicrosoftOffice.msi`檔案。

1. 從表清單（位於左側）中選擇「屬性」。

1. 編輯下列適用於您企業安裝Rights Management或Document Security的索引鍵名稱值。

<table>
 <tbody>
  <tr>
   <td><p><strong>鍵</strong><strong></strong><strong>名</strong></p> </td>
   <td><p><strong>說明</strong></p> </td>
   <td><p><strong>鍵</strong><strong></strong><strong>值預設值</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>顯示名稱。</p> </td>
   <td><p>預設伺服器</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>主機伺服器URL。</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. 從表清單（位於左側）中選擇「註冊表」。

1. 編輯下列索引鍵名稱值。

   | **密鑰名稱** | **說明** | **索引鍵值預設值** |
   |---|---|---|
   | `IsDefault` | 預設的APS伺服器。 | 預設伺服器 |

1. 將修改的檔案儲存至包含原始MSI安裝程式的相同目錄。

   >[!NOTE]
   >
   >常見的做法是使用與原始MSI檔案相同的檔案名稱（例如`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## 配置預設策略{#configuring-automatic-application-of-a-default-policy}的自動應用程式

在設定中，您可以設定預設原則的自動應用程式，讓Document Security Extension for Microsoft Office可保護儲存的每份檔案。

您可以指定下列其中一個選項：

* 使用預設原則保護所有檔案。
* 允許用戶在無法連接到伺服器時選擇以未受保護的格式保存檔案。 此彈性可讓您在使用者中斷網路連線時（例如在飛機上）建立檔案時，考量使用者的情況。

啟用自動套用原則功能後，在下列情況下，檔案會受到預設原則的保護：

* 使用者編輯並儲存新建立的檔案
* 使用者編輯和儲存未受保護的檔案
* 使用者開啟應用程式，以預設檔案開啟、編輯，然後儲存檔案

### 在MSI檔案中設定自動套用原則功能  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

開始之前，請預先設定安裝程式，以指向您的LiveCycle或AEM表單伺服器，如本文稍早所述。

1. 按一下「開始>程式集> Orca ]**」。**[!UICONTROL 

1. 按一下「**[!UICONTROL 檔案>開啟]**」，然後瀏覽至`DocumentSecurityExtensionforMicrosoftOffice.msi`檔案。

1. 從表清單（位於左側）中選擇「屬性」。

1. 編輯下列適用於您企業安裝Rights Management或Document Security的索引鍵名稱值。

<table>
 <tbody>
  <tr>
   <td><p><strong>密鑰名稱</strong></p> </td>
   <td><p><strong>說明</strong></p> </td>
   <td><p><strong>鍵</strong><strong></strong><strong>值預設值</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>啟用或停用自動套用原則功能。</p> <p><code>1</code>: 啟用</p> <p>0:禁用</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>儲存新檔案時要使用的原則GUID。 套用至自動套用原則功能。</p> </td>
   <td><p>RM伺服器上可見的十六進位策略ID</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>伺服器 URL.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>伺服器埠號。</p> </td>
   <td><p>一二三四年</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>如果用戶端無法連絡伺服器，以在第一次儲存時保護檔案，則判斷是否可在沒有Document Security保護的情況下建立檔案。</p> <p>1:允許未受保護的保存 </p> <p>0:當用戶端無法連絡伺服器以儲存檔案時，避免建立新檔案。</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` 當您想要提醒客戶保護所有檔案而不需要強迫他們這麼做時，此選項會很有用。當您知道使用者在中斷網路連線時建立檔案時，也會很有用。 您不希望阻止他們建立和保存文檔。

1. 將修改過的檔案儲存至包含原始MSI檔案的相同目錄。

   >[!NOTE]
   >
   >常見的做法是使用與原始MSI檔案相同的檔案名稱（例如`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## 啟用對新文檔{#enabling-automatic-protection-of-new-documents}的自動保護

管理員可以啟用自動保護使用者儲存的任何檔案的功能。 管理員可在Document Security Extension for Microsoft Office的安裝程式中設定「自動套用」原則功能。

如果啟用「自動套用原則」，使用者儲存的所有檔案都會受到預設原則的保護。 此操作適用於以下情況：

* 當使用者建立新檔案、進行編輯並儲存時。
* 當使用者開啟未受保護的檔案、進行編輯並儲存時。

有關配置自動應用策略的資訊，請參閱[配置預設策略的自動應用程式](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p)。

## 啟用無功能區的用戶介面{#enable-ribbon-less-user-interface}

通過修改Windows註冊表中的設定，可以啟用／禁用無功能區用戶介面。 執行以下步驟以更新註冊表並啟用無功能區用戶介面：

1. 在對Windows註冊表進行更改之前，請對其進行備份。 有關詳細說明，請參見[如何修改Windows註冊表](https://support.microsoft.com/en-us/kb/136393)。
1. 在註冊表編輯器中，導航至HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0或HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 建立名為&#x200B;**HidePluginUI**&#x200B;的新Dword（32位元）值。

1. 將**HidePluginUI **屬性的值設為1，以啟用無功能區的使用者介面。

1. 關閉註冊表編輯器。

## 在Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}中啟用用於打印的水印

您可以變更Windows註冊表設定，讓動態水印與現有的頁首和頁尾共存。 註冊表設定使水印僅在打印期間可用。 執行以下步驟以在打印過程中更新註冊表並啟用水印：

1. 在對Windows註冊表進行更改之前，請對其進行備份。 有關詳細說明，請參見[如何修改Windows註冊表](https://support.microsoft.com/en-us/kb/136393)。
1. 在註冊表編輯器中，導航至HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0或HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 建立新的註冊表鍵&#x200B;**WatermarkMode**。
1. 在WatermarkMode註冊表鍵中，建立DWORD **WatermarkMode**，並將DWORD **WatermarkMode**&#x200B;的值設定為&#x200B;**1**。

1. 關閉註冊表編輯器。

>[!NOTE]
>
>在Windows檔案總管中，您可以使用「檔案」選單或內容選單來建立Microsoft Excel檔案。 對於使用指定方法建立的文檔，不能檢索或更改打印日期。 這是Microsoft Excel的限制。 AEM Document Security浮水印需仰賴檔案的列印日期。 因此，對於此類文檔，水印將恢復為上一個日期。 此外，頁首和頁尾也不會保留。

## 將自訂封面頁面新增至檔案{#coverpage}

使用者可嘗試在未安裝AEM Document Security for Microsoft Office外掛程式的機器上開啟受保護的檔案。 這些電腦無法開啟文檔。 在這些電腦上，您可以顯示封面頁，其中包含下載AEM Document Security for Microsoft Office外掛程式和其他資訊的指示。

### 在您設定封面{#before-you-configure-a-cover-page}之前

* 備份CommonResources.dll檔案。 預設路徑為：

   * **（適用於32位元機器上的32位元辦公室）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（適用於64位元機器上的32位元辦公室）** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（適用於64位元機器上的64位元辦公室）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* 請確定您已安裝Microsoft Visual Studio 2008或更新版本。 您也可以使用任何其他實用程式來編輯DLL檔案。
* 解壓縮templates.zip檔案。 封面頁面的封存包含。xlsx、.docx和。pptx範本。 僅使用檔案類型。xlsx、.docx和。pptx提供的範本。 您可以為其他檔案類型建立自己的範本。 自訂範本以包含自訂訊息和指示。 您可在以下網址找到template.zip:

[取得檔案](assets/templates.zip)

### CommonResources.dll檔案{#structure-of-the-commonresources-dll-file}的結構

CommonResources.dll檔案包含有關資源模板的資訊。 它包含兩個名稱識別碼TEMPLATE_FILE和RT_MANIFEST。 若要啟用自訂封面頁，會修改TEMPLATE_FILE名稱識別碼。 TEMPLATE_FILE名稱標識符有6個資源：

<table>
 <tbody>
  <tr>
   <td><p><strong>資源</strong></p> </td>
   <td><p><strong>代表 </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### 將範本設定為封面{#configure-the-template-as-a-cover-page}

1. 開啟Microsoft Visual Studio。 瀏覽並開啟CommonResources.dll檔案以進行編輯。

   >[!NOTE]
   >
   >如果檔案未出現在「解決方案瀏覽器」窗口中，請使用「開啟方式」選項重新開啟檔案。 選擇資源編輯器作為編輯器。

1. 在「解決方案總管」視窗中，展開TEMPLATE_FILE目錄，並刪除資源101。

1. 添加資源：

   1. 在「解決方案總管」中選取專案後，在「專案」功能表上，按一下「屬性」。
   1. 選擇「資源」頁籤。
   1. 在資源設計器工具欄上，指向「添加資源」 ，按一下箭頭。 對於資源類型，選擇「模板檔案」，然後按一下「導入」。
   1. 在「新增現有檔案至資源」對話方塊中，瀏覽至Resource.xlsx檔案，然後按一下「開啟」。 檔案將添加到TEMPLATE_FILE目錄。

   >[!NOTE]
   >
   >確保語言設定正確。 使用中性語言刪除資源。

1. 對所有資源類型重複步驟2和3。

   >[!NOTE]
   >
   >請勿以隨機順序刪除和添加資源類型。 在101之後，請設定102等。

### 使用AEM Document Security擴充功能的Microsoft Office {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}安裝程式封裝自訂CommonResources.dll檔案

您可以自訂CommonResources.dll檔案，以加入自訂封面頁。 在自訂檔案後，您可以在所有工作站上以自訂檔案手動取代原始檔案，或選擇自動化方法來取代檔案。

在大型環境中，手動將預設`CommonResources.dll file`取代為自訂`CommonResources.dll`檔案既困難又麻煩。 您可以使用自解壓和封裝工具（例如WinZip Self-Extractor），將自訂CommonResources.dll檔案與AEM Document Security Extension for Microsoft Office安裝程式封裝。 稍後，您可將自訂安裝程式分發至所有工作站。 此方法可縮短將預設`CommonResources.dll`檔案取代為自訂檔案所需的時間。 它還確保所有工作站都具有所需的CommonResources.dll檔案。 自解壓和封裝工具只是許多自動取代檔案的可能方法之一。 您可以選擇適合您環境的任何方法。

您可以執行下列步驟，將自訂的`CommonResources.dll`檔案與AEM Document Security擴充功能的安裝程式一起封裝：

1. 安裝自解壓器和打包工具。 例如，WinZip Self-Extractor。
1. 建立新資料夾。 例如，YOUR_FOLDER_NAME
1. 將AEM Document Security Extension和自訂CommonResources.dll檔案的原始安裝程式置於新建立的檔案夾中。
1. 在資料夾中建立批處理檔案。 例如，YOUR_FOLDER_NAME\Installer.bat
1. 開啟批次檔案以進行編輯，並新增下列程式碼至批次檔案：

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   如果您在JEE上使用除LiveCycle Rights Management ES4和11.0.0版以外的任何其他LiveCycle或AEM Forms版本，請取代註冊表金鑰的路徑，如下所示：

   * （Livecycle Rights Management ES2和9.0版）:*HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * （Livecycle Rights Management ES3和10.0版）
   * （Livecycle Rights Management ES4和11.0版）HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0 Forms on JEE and allear versions)HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. 在上述代碼中，將YOUR_FOLDER_NAME的所有實例替換為在步驟2中建立的資料夾的名稱。
1. **（僅適用於副檔名為。exe的AEM Document Security Extension for Microsoft Office安裝程式）** 取代下列程式碼行：

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
with

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. 儲存並關閉批次檔案。
1. 使用自解壓縮和封裝工具來封裝包含自訂CommonResources.dll檔案的檔案夾、AEM Document Security擴充功能的原始安裝程式(for Microsoft Office)，以及批次檔案。

   >[!NOTE]
   >
   >確保自解壓包設定為以管理員身份運行並自動運行
   >在完成提取時運行批處理檔案。

現在，適用於Microsoft Office的AEM Document Security擴充功能的自解壓安裝程式已封裝自訂CommonResources.dll檔案，並可供散發。
