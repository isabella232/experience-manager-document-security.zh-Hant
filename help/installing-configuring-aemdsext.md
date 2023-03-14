---
title: 安裝和設定 Microsoft Office 適用的 AEM Document Security Extension
description: 此文件會指引您安裝和設定 Microsoft Office 適用的 Adobe Experience Manager Document Security Extension 6.2。
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
source-git-commit: 13c487b13acb0d65f02301c881bfade512428bcd
workflow-type: tm+mt
source-wordcount: '2764'
ht-degree: 100%

---

# 安裝和設定 Microsoft Office 適用的 AEM Document Security Extension{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

此文件會指引您安裝和設定 Microsoft Office 適用的 Adobe Experience Manager Document Security Extension。

本文件包含有關以下工作的資訊：

* 安裝 Microsoft Office 適用的 Document Security Extension
* 將安裝程式預先設定為指向安裝 LiveCycle Rights Management ES2 或以上版本，以及 AEM 6.0 Forms 或以上版的 Document Security 附加元件。
* 設定自動套用預設原則

## 安裝之前 {#before-you-install}

在安裝 Microsoft Office 適用的 Document Security Extension 以前，請確保：

* 您已閱讀 [版本注意事項](document-security-extension-release-notes.md)。
* Microsoft Office 已啟用。開啟 Microsoft Office 應用程式時不會出現啟用對話框。
* 已安裝 Microsoft Windows 和 Microsoft Office 適用的最新 Service Pack。
* 如果您未安裝不支援語言的 Microsoft Office 適用 Document Security，則要開啟 Office 應用程式至少一次。

>[!NOTE]
>
>不要將軟體安裝在名稱含有全形字元的檔案夾中。如果這樣做，AEM Document Security 功能表不會將出現在 Microsoft Office 中。


>[!NOTE]
>
>支援在 64 位元作業系統上安裝 32 位元版的 Document Security，但反之則不支援。您無法在 32 位元作業系統上安裝 Microsoft Office 適用的 64 位元版本 Document Security。

### 停用 McAfee VirusScan&amp; {#disable-mcafee-virusscan}

若電腦有已安裝的 Document Security Extension，並有已啟用即時 (On-Access) 掃描的 McAfee VirusScan，為了確保此電腦能順利啟動 Office 應用程式，請停用 McAfee VirusScan 控制台中的「緩衝區溢位保護」選項。

### 解除安裝協力廠商外掛程式 {#uninstall-third-party-plug-ins}

Microsoft Office 適用的 AEM Document Security Extension 不支援 Microsoft Office 應用程式適用的協力廠商外掛程式。由於此擴充功能與協力廠商外掛程式有衝突，在安裝 Microsoft Office 適用的 Document Security 以前，請先解除安裝 Microsoft Office 適用的非 Adobe 外掛程式。Adobe 不支援已安裝協力廠商外掛程式的 Microsoft Office 適用的 Document Security。

## 系統需求 {#system-requirements}

### Document Security Extension 用戶端 {#document-security-extension-client}

確保您要安裝 Document Security Extension 的以下基本設定：

* 32 位元或 64 位元版的 Microsoft Windows 7 或 Windows 10 - 英文版、法文版、德文版、日文版、義大利文版、西班牙文版、葡萄牙文 (巴西) 版、韓文版、簡體中文版和繁體中文版。
   **注意：***Microsoft Office 適用的 Document Security Extension 也預計可在 Microsoft Surface 裝置上使用。*

* 32 位元或 64 位元版的 Microsoft Office 2013、2016、2019 和安裝為 Office 365 一部分的 Microsoft Office 桌面應用程式 - 英文版、法文版、德文版、日文版、義大利文版、西班牙文版、葡萄牙文 (巴西) 版、韓文版、簡體中文版和繁體中文版。

   **注意**：*Microsoft Office 適用的 AEM Document Security Extension 不支援 Microsoft Office 應用程式適用的協力廠商外掛程式。由於此擴充功能與協力廠商外掛程式可能有衝突，在安裝 Microsoft Office 適用的 Document Security Extension 以前，必須先解除安裝 Microsoft Office 塵用程式適用的非 Adobe 外掛程式。Adobe 不支援已安裝協力廠商外掛程式的 Microsoft Office 適用的 Document Security Extension。*

* 1.3 GHz 或更快處理器
* 2 GB RAM
* 100 MB 的可用硬碟空間

### 文件安全性 {#document-security}

若要使用 Document Security Extension，您可以連線至 Adobe LiveCycle Rights Management ES2 及以上版本，或 AEM 6.0 Forms 或以上版本適用的 Document Security 附加元件。

## 安裝 Microsoft Office 適用的 Document Security Extension {#installing-document-security-extension-for-microsoft-office}

您可以從[下載頁面](download-installer.md)下載安裝程式。您不能直接自訂安裝程式可執行的檔案，但可以互動方式或無訊息模式安裝。若要安裝該軟體，請以管理員身份登入 Windows。

32 位元和 64 位元版的 Microsoft Office 有不同的安裝程式可用。若是 32 位元版的 Microsoft Office，可下載 DocumentSecurityExtensionforMicrosoftOffice.exe。若是 64 位元版的 Microsoft Office，可下載 DocumentSecurityExtensionforMicrosoftOffice64.exe。

>[!NOTE]
>
>本文件是使用 32 位元安裝程式檔案 (DocumentSecurityExtensionforMicrosoftOffice.exe) 來說明不同命令和選項。如果您是使用 64 位元版 Microsoft Office，請使用 64 位元安裝程式檔案 (DocumentSecurityExtensionforMicrosoftOffice64.exe) 來執行本文件所列的操作。

### 以無訊息模式安裝 {#install-in-silent-mode}

使用檔案擷取器公用程式 (例如 WinZip) 從安裝程式檔案解壓縮 `DocumentSecurityExtensionforMicrosoftOffice.exe`。開啟命令提示，前往含有設定檔案的檔案夾，然後輸入以下文字：

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

安裝程式也可作為 MSI 文件提供；此程式可用來自訂。

### 以無訊息模式安裝 MSI 檔案 {#install-an-msi-file-in-silent-mode}

1. 使用檔案擷取器公用程式 (例如 WinZip) 從 ZIP 檔案來解壓縮 `DocumentSecurityExtensionforMicrosoftOffice.msi` 檔案。

1. 開啟命令提示，前往含有 MSI 檔案的檔案夾，然後輸入以下文字：

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## 將安裝程式預先設定為連線至 Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

您可以將 Microsoft Office 安裝程式適用的 Document Security Extension 預先設定為指向 LiveCycle 或 AEM 伺服器，以便 Microsoft Office 適用的 Document Security Extension 安裝用戶可以使用功能而無需設定連線。這樣，用戶無需任何設定即可開啟受保護的文件。但是，除非用戶將客戶端設定為使用特定伺服器，否則他們無法保護新文件。

下列步驟說明如何建立和設定 MSI 檔案。本 MSI 檔案含有將「Microsoft Office 安裝程式適用的 Document Security Extension」預先設定為 LiveCycle 或 AEM 伺服器 (即安裝在您的企業中) 所需的登錄值。

### 自訂安裝程式的先決條件 {#prerequisites-for-customizing-the-installer}

使用 Orca 資料庫編輯器來自訂安裝程式。下列步驟說明如何使用 Orca 資料庫編輯器來修改 MSI 安裝檔案，進而建立自訂的 MSI 檔案。Orca 做為 Windows Server 2008 和 .NET Framework 3.5 之 Windows SDK 的一部分提供。

<!--

For more information about how to edit Microsoft Windows® Installer files using Orca, see [Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/).

-->

>[!NOTE]
>
>在建立自訂 MSI 檔案以前，建議您將所有安裝程式檔案進行完整備份。

#### 安裝 Orca {#install-orca}

1. 下載 Windows Server 2008 和 .NET Framework 3.5 的 Windows SDK。
1. 在 \Microsoft SDK\bin 檔案夾中按兩下 Orca.msi 檔案。

   您還需要安裝程式檔案的 MSI 變數。若要獲得最新版 MSI 安裝程式，請與 Adobe 支援人員聯絡。

   >[!NOTE]
   >
   >在執行安裝程式以前，請務必關閉 DocumentSecurityExtensionforMicrosoftOffice.msi 檔案。如果 Orca 正在使用 MSI 檔案，就無法執行此安裝程式。

### 建立和設定 MSI 檔案 {#create-and-configure-the-msi-file}

1. 按一下「**[!UICONTROL 開啟 > 程式 > Orca]**」。

1. 按一下「**[!UICONTROL 檔案 > 開啟]**」，然後瀏覽 `DocumentSecurityExtensionforMicrosoftOffice.msi` 檔案。

1. 從標籤清單 (左側) 中選取「屬性」。

1. 編輯以下適用於您企業安裝的 Rights Management 或 Document Security 的金鑰名稱值。

<table>
 <tbody>
  <tr>
   <td><p><strong>金</strong><strong>鑰</strong><strong>名稱</strong></p> </td>
   <td><p><strong>說明</strong></p> </td>
   <td><p><strong>金</strong><strong>鑰</strong><strong>值預設</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>顯示名稱</p> </td>
   <td><p>預設伺服器</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>主機伺服器 URL。</p> </td>
   <td><p>https://default.corp.com：1234</p> </td>
  </tr>
 </tbody>
</table>

1. 從標籤清單 (左側) 中選取「登錄」。

1. 編輯下列金鑰名稱值。

   | **金鑰名稱** | **說明** | **金鑰值預設** |
   |---|---|---|
   | `IsDefault` | 預設 APS 伺服器。 | 預設伺服器 |

1. 將修改後的檔案儲存到含有原始 MSI 安裝程式的同一個目錄中。

   >[!NOTE]
   >
   >使用與原始 MSI 檔案 (例如 `DocumentSecurityExtensionforMicrosoftOffice.msi`) 相同檔案名稱的一般方法。

## 設定自動套用預設原則 {#configuring-automatic-application-of-a-default-policy}

在設定過程中，您可以設定自動套用預設原則，這樣 Microsoft Office 適用的 Document Security Extension 便會保護每個已儲存的文件。

您可以指定下列其中一個選項：

* 使用預設原則保護所有文件。
* 當用戶無法連線到伺服器時，允許用戶選擇以不受保護的格式儲存檔案。這種靈活性可讓您解決用戶在無法連線到網絡 (例如在飛機上) 時建立文件的情況。

在啟用自動套用原則功能後，若有以下情況時，可以預設原則來保護文件：

* 用戶編輯和儲存新建立的文件
* 用戶編輯和儲存未受保護的文件
* 用戶開啟以預設文件開啟的應用程式，進行編輯後儲存該文件

### 在 MSI 檔案中設定自動套用原則功能  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

在開始之前，請將安裝程式預先設定為指向您的 LiveCycle 或 AEM Forms 伺服器 (如本文前面所述)。

1. 按一下「**[!UICONTROL 開啟 > 程式 > Orca]**」。

1. 按一下「**[!UICONTROL 檔案 > 開啟]**」，然後瀏覽 `DocumentSecurityExtensionforMicrosoftOffice.msi` 檔案。

1. 從標籤清單 (左側) 中選取「屬性」。

1. 編輯以下適用於您企業安裝的 Rights Management 或 Document Security 的金鑰名稱值。

<table>
 <tbody>
  <tr>
   <td><p><strong>金鑰名稱</strong></p> </td>
   <td><p><strong>說明</strong></p> </td>
   <td><p><strong>金</strong><strong>鑰</strong><strong>值預設</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>啟用或停用自動套用原則功能。</p> <p><code>1</code>：啟用</p> <p>0：停用</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>儲存新文件時要使用的原則 GUID。套用至自動套用原則功能。</p> </td>
   <td><p>在 RM 伺服器所見的十六進位原則 ID</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>伺服器 URL。</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>伺服器連接埠號碼。</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>如果客戶端無法連線伺服器來保護首度儲存的文件，則要先確定是否可以在沒有 Document Security 保護的情況下建立文件。</p> <p>1：允許未受保護的儲存 </p> <p>0：當用戶端無法連線伺服器來儲存文件時，請防止建立新文件。</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>當您要提醒客戶保護所有文件但不強迫他們這樣做時，`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` 選項很有用。當您知道用戶在無法連線網絡下建立文件時，這個選項也很有用。您不想阻止他們建立和儲存文件。

1. 將修改後的檔案儲存到含有原始 MSI 檔案的同一個目錄中。

   >[!NOTE]
   >
   >使用與原始 MSI 檔案 (例如 `DocumentSecurityExtensionforMicrosoftOffice.msi`) 相同檔案名稱的一般方法。

## 啟用自動保護新文件 {#enabling-automatic-protection-of-new-documents}

管理員可以啟用自動保護用戶所儲存的任何文件的功能。在 Microsoft Office 適用的 Document Security Extension 的安裝程式中，管理員可設定自動套用原則功能。

如果啟用了「自動套用原則」，則用戶儲存的所有文件都將受到預設原則的保護。此操作適用於以下情況：

* 當用戶建立新文件時，可編輯並儲存文件。
* 當用戶開啟未受保護文件時，可編輯並儲存文件。

若要了解設定自動套用原則的資訊，請參閱 [設定自動套用預設原則](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p)。

## 啟用較少功能區的用戶介面 {#enable-ribbon-less-user-interface}

您可以修改 Windows 登錄設定，進而啟用/停用較少功能區的用戶介面。執行以下步驟來更新登錄，並啟用較少功能區的用戶介面：

1. 在進行變更前，請備份 Windows 登錄。若需要詳細的說明，請參閱 [如何修改 Windows 登錄](https://support.microsoft.com/en-us/kb/136393)。
1. 在登錄編輯程式內，瀏覽至 HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 or HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 建立名稱為 **HidePluginUI** 的新 Dword (32 位元) 值。

1. 將 **HidePluginUI** 屬性的值設定為 1，以啟用較少功能區的用戶介面。

1. 關閉登錄編輯程式。

## 啟用浮水印，以便在 Microsoft Excel 中列印 {#enable-watermark-for-printing-in-microsoft-excel}

您可以變更 Windows 登錄設定，使動態浮水印與現有的頁首頁尾同時存在。登錄設定可讓浮水印只適用於列印期間。執行以下步驟來更新登錄，並在列印期間啟用浮水印：

1. 在進行變更前，請備份 Windows 登錄。若需要詳細的說明，請參閱 [如何修改 Windows 登錄](https://support.microsoft.com/en-us/kb/136393)。
1. 在登錄編輯程式內，瀏覽至 HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 or HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. 建立新的登錄機碼 **WatermarkMode**。
1. 在 WatermarkMode 登錄機碼中，建立 DWORD **WatermarkMode**，並將 DWORD **WatermarkMode** 值設定為 **1**。

1. 關閉登錄編輯程式。

>[!NOTE]
>
>在 Windows Explorer 中，您可以使用「檔案」功能表或內容功能表來建立 Microsoft Excel 文件。若是使用規定方法來建立文件，則無法擷取或變更列印日期。這是 Microsoft Excel 的局限性。AEM Document Security 浮水印取決於文件的列印日期。因此，對於此類文件，浮水印將還原為早一天的日期。此外，頁頭和頁尾也不會受到限制。

## 新增自訂封面頁至文件 {#coverpage}

用戶可以嘗試在未安裝 Microsoft Office 適用 AEM Document Security 外掛程式的電腦上開啟受保護的文件。這類電腦無法開啟文件。在這類電腦上，您可以顯示一個封面頁，內容含下載 Microsoft Office 適用 AEM Document Security 外掛程式的說明和其他資訊。

### 在您設定封面頁以前 {#before-you-configure-a-cover-page}

* 進行 CommonResources.dll 檔案備份。預設路徑為：

   * **(適用於 32 位元電腦上的 32 位元 Office)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(適用於 32 位元電腦上的 64 位元 Office)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(適用於 64 位元電腦上的 64 位元 Office)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* 確保您已安裝 Microsoft Visual Studio 2008 或更高版本。您也可以在使用任何公用程式來編輯 DLL 檔案。
* 解壓縮 templates.zip 封存。封存包含用於封面頁的 .xlsx、.docx 和 .pptx 範本。僅將獲得的範本用於 .xlsx、.docx 和 .pptx 等檔案類型。您可以自己建立適用於其他檔案類型的範本。自訂範本以含有自訂訊息和說明。您可在此找到 template.zip：

[取得檔案](assets/templates.zip)

### CommonResources.dll 檔案的結構 {#structure-of-the-commonresources-dll-file}

CommonResources.dll 檔案含有關於資源範本的資訊。檔案含有兩個名稱識別碼：TEMPLATE_FILE 和 RT_MANIFEST。若要啟用自訂封面頁，要修改 TEMPLATE_FILE 名稱識別碼。TEMPLATE_FILE 名稱識別碼有六個資源：

<table>
 <tbody>
  <tr>
   <td><p><strong>資源</strong></p> </td>
   <td><p><strong>表示 </strong></p> </td>
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

#### 設定封面頁的範本 {#configure-the-template-as-a-cover-page}

1. 開啟 Microsoft Visual Studio。瀏覽並開啟 CommonResources.dll 檔案以進行編輯。

   >[!NOTE]
   >
   >如果該檔案未出現在「方案總管」視窗中，請使用「開啟檔案」選項重新開啟該檔案。選取以資源編輯器作為編輯器。

1. 在「方案總管」視窗中，擴展 TEMPLATE_FILE 目錄，並刪除資源 101。

1. 新增資源：

   1. 在「方案總管」中選取一個專案後，在「專案」功能表上，按一下「屬性」。
   1. 選取「資源」標籤。
   1. 在「資源設計工具」工具列上，指向「新增資源」，按一下箭頭。若是資源類型，選取 TEMPLATE_FILE，並按一下「匯入」。
   1. 在「將現有的檔案加入資源」對話框中，瀏覽至 Resource.xlsx 檔案，然後按一下「開啟」。直接將該檔案新增至 TEMPLATE_FILE。

   >[!NOTE]
   >
   >確保語言設定正確無誤。刪除中性語言的資源。

1. 針對所有資源類型，重複步驟 2 和 3。

   >[!NOTE]
   >
   >不要以隨機順序刪除和新增資源類型。在 101 以後，設定 102，依此類推。

### 使用 Microsoft Office 適用 AEM Document Security Extension 的安裝程式，封裝自訂的 CommonResources.dll 檔案  {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

您可以自訂 CommonResources.dll 檔案，以包含新增自訂封面頁。在自訂檔案後，您可以手動方式在所有工作站上以自訂檔案取代原始檔案，也可以選擇自動方式來取代檔案。

在大規模環境中，採用手動方式以自訂 `CommonResources.dll` 檔案取代預設 `CommonResources.dll file` 既困難又繁瑣。您可以使用自動解壓縮和封裝工具 (例如 WinZip 自動解壓縮程式)，封裝自訂的 CommonResources.dll 檔案與 Microsoft Office 適用的 AEM Document Security Extension。稍後，您可以將自訂安裝程式分發到所有工作站。此方式可以減少自訂檔案取代預設 `CommonResources.dll` 檔案所需的時間。此方式還可以確保所有工作站都具備必要的 CommonResources.dll 檔案。自動解壓縮和封裝工具只是自動代替檔案的多種可能方法之一。您可以選擇適合您環境的任何方法。

您可以執行以下步驟，透過 Microsoft Office 適用的 AEM Document Security Extension 安裝程式來封裝自訂 `CommonResources.dll` 檔案。

1. 安裝自動解壓縮程式和封裝工具。例如，WinZip 自動解壓縮程式。
1. 建立新的檔案夾。例如，YOUR_FOLDER_NAME
1. 將 AEM Document Security Extension 的原始安裝程式和自訂的 CommonResources.dll 檔案放在新建檔案夾。
1. 在檔案夾建立一個批次檔案。例如，YOUR_FOLDER_NAME\Installer.bat
1. 開啟批次檔案進行編輯，並新增下列代碼至批次檔案：

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

   如果要在 JEE 上使用 LiveCycle Rights Management ES4 和 11.0.0 版以外的任何其他版本 LiveCycle 或 AEM Forms，請以下列取代登錄機碼的路徑：

   * (Livecycle Rights Management ES2 和 9.0 版)：*HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (Livecycle Rights Management ES3 和 10.0 版)
   * (Livecycle Rights Management ES4 和 11.0 版) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (JEE 和以上版本的 AEM 6.0 Forms) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. 在上面程式碼中，以您在步驟 2 中建立的檔案夾名稱來取代 YOUR_FOLDER_NAME 的所有執行個體。
1. **(限附有 .exe 副案名的 Microsoft Office 適用 AEM Document Security Extension 安裝程式)** 取代下列程式碼列：

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
替換為

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. 儲存並關閉批次檔案。
1. 使用自動解壓縮和封裝工具來封裝含有後述的檔案夾：自訂 CommonResources.dll 檔案、Microsoft Office 適用的 AEM Document Security Extension 原始安裝程式和批次檔案。

   >[!NOTE]
   >
   >確保將自動解壓縮程式套件設定為以管理員身分來執行，以及
   >完成解壓縮後自動執行批次檔案。

現在，Microsoft Office 適用的 AEM Document Security Extension 的自動解壓縮安裝程式會封裝自訂 CommonResources.dll 檔案，並準備供分發。
