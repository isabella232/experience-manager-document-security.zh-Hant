---
title: 使用AEM Document Security Extension for Microsoft Office
description: 無論您散布檔案的範圍有多廣，您都可以控制收件者使用受原則保護檔案的方式。 本檔案說明如何保護檔案以及如何使用受保護的檔案。
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
translation-type: tm+mt
source-git-commit: 21288f7f1c8f786d3c4c363986226038bdb03e26
workflow-type: tm+mt
source-wordcount: '6270'
ht-degree: 0%

---


# 使用AEM Document Security Extension for Microsoft Office{#using-aem-document-security-extension-for-microsoft-office}

## 使用AEM Document Security Extension {#usingaemdocumentsecurityextensiontoprotectfiles}保護檔案

無論您散布檔案的範圍有多廣，您都可以控制收件者使用受原則保護檔案的方式。

使用Document Security Extension for Microsoft Office，您可以執行下列工作：

* 設定您與Document Security的連線
* 將原則套用至檔案
* 開啟Document Security網頁以建立和管理使用者原則
* 從檔案中刪除策略保護
* 變更套用至檔案的原則
* 開啟Document Security網頁以廢止檔案的存取權或變更檔案的原則
* 開啟Document Security網頁以檢視檔案的稽核記錄

### 連線至Document Security伺服器{#connect-to-a-document-security-server}

如果您要將原則套用至檔案，則必須設定Document Security的連線設定。 視Document Security Extension for Microsoft Office的安裝方式而定，您可能已有預設的連線設定。 您可以新增一或多個Document Security例項的連線設定。 您可以從Document Security管理員取得伺服器資訊。

您必須將要用來保護檔案或管理受保護檔案的伺服器設定為預設伺服器。 當您將原則套用至新檔案或開啟Document Security網頁時，Document Security Extension for Microsoft Office會連線至預設伺服器。 如果您使用多個Document Security實例保護檔案，在伺服器間切換時，必須變更預設伺服器設定。 只要您擁有開啟檔案的授權，就可以開啟受Document Security任何例項保護的檔案。

如果您的Document Security伺服器採用憑證式驗證，您將需要安裝在本機電腦中收到的憑證。 您必須選擇憑證驗證，並提供您要用來驗證的憑證。

在一個Microsoft Office應用程式中設定Document Security例項的連線設定後，就會針對所有Word、Excel和PowerPoint進行設定。

#### 安裝客戶端證書{#install-the-client-side-certificate}

如果您需要透過認證驗證或雙向驗證來存取Document Security網頁，您將會收到必須安裝在本機電腦上的認證。 您會收到憑證檔案（.PFX或。P12檔案）及其密碼。

1. 將憑證檔案儲存在本機電腦中。
1. 連按兩下憑證檔案以開啟憑證匯入精靈，然後按一下「下一步」。****
1. 如果檔案名框中列出了證書檔案，請按一下「**Next**」。 如果要查找其他證書，請按一下&#x200B;**瀏覽**。
1. 輸入您收到的密碼，然後按一下&#x200B;**Next**。
1. 在「認證存放區」對話方塊中，選取「將所有認證置於下列存放區」，然後按一下「瀏覽&#x200B;****」。
1. 在「選擇證書儲存」對話框中，選擇「個人」，按一下「確定」，按一下「****」，按一下「下一步」，然後按一下「完成」。********

#### 配置連接設定{#configure-connection-settings}

1. 在Document Security Extension for Microsoft Office 2010和Office 2013的&#x200B;**Document Security**&#x200B;標籤上，選取&#x200B;**選擇伺服器**。
1. 按一下&#x200B;**新建**&#x200B;以建立新連接設定，或選擇現有連接並按一下&#x200B;**編輯**。
1. 在&#x200B;**Name**&#x200B;框中鍵入連接的名稱。 您可以使用任何名稱。
1. 在&#x200B;**伺服器地址**&#x200B;框中鍵入伺服器的地址。
1. 在&#x200B;**Port**&#x200B;框中鍵入伺服器埠。
1. （可選）如果您想記住您的用戶名和密碼，請選擇&#x200B;**「記住此電腦上的密碼」，並在相應的框中鍵入您的用戶名和密碼。**&#x200B;如果其他人可以存取電腦，建議您不要選取此選項。
1. 按一下&#x200B;**連接到此伺服器**。 Document Security Extension for Microsoft Office會嘗試連線至您指定的伺服器。 根據指定的驗證類型，執行下列操作之一：

   **使用者名稱與密碼**

   輸入您從Document Security管理員收到的使用者名稱和密碼。

   **憑證驗證**

   選擇此選項，以選擇您收到並安裝在個人憑證商店中的憑證。

   如果Document Security上只設定了一種驗證類型，則只會顯示該選項。

>[!NOTE]
>
>如果您無法連線至伺服器，請嘗試在Internet Explorer中開啟Document Security網頁。 如果您無法使用Internet Explorer連線至伺服器，或對話方塊顯示有關伺服器憑證的警告，Document Security Extension for Microsoft Office將無法連線至伺服器。 請連絡伺服器管理員以取得協助。

>[!NOTE]
>
>如果您無法連線至Document Security，會出現訊息，指出「使用者名稱和密碼不正確，請檢查您的組態設定，然後再試一次。」 如果您因其他原因而無法連線，可能會出現此訊息。 如果您是首次連接到伺服器，請驗證您是否正確設定了伺服器名稱和埠。

#### 指定預設伺服器{#specify-the-default-server}

1. 執行下列動作：

   * 在&#x200B;**Document Security**&#x200B;標籤上的Document Security Extension for Microsoft Office 2010和Office 2013中，選取&#x200B;**選擇伺服器**。

1. 選擇要指定為預設的伺服器，然後按一下「設定預設值」。 ****&#x200B;預設伺服器旁會出現星號。

### 使用第三方驗證提供者{#using-third-party-authentication-providers}

您可以搭配AEM Forms Document Security使用協力廠商驗證提供者。 這些驗證提供者可協助您新增額外的存取層至受保護的檔案。 AEM Forms Document Security支援下列延伸驗證工作流程：

* 使用預設AEM Forms URL的擴充驗證
* 使用自訂URL的擴充驗證
* 在JEE伺服器上的AEM Forms上設定協力廠商身分提供者的預設延伸驗證工作流程
* 自訂擴充驗證工作流程，其中第三方身分提供者已設定在JEE伺服器上的AEM Forms
* 使用自訂頁面列出SAML驗證的擴充驗證

#### 使用預設AEM Forms URL {#extended-authentication-using-default-aem-forms-url}的擴充驗證

您可以使用預設的AEM Forms URL進行延伸驗證。 預設登陸頁面包含Adobe品牌。 此外，預設的AEM Forms設定也會用於使用預設的AEM Forms URL進行延伸驗證。

請執行下列步驟，以啟用預設Adobe Landing URL的擴充驗證：

1. 開啟AEM Forms管理員UI。
1. 導覽至「服務> Document Security >設定>伺服器設定」。
1. 啟用「允許擴展驗證」選項。
1. 指定預設的URL Extended Authentication Landing URL。 預設URL為http://localhost:8080/edc/extendedauthentication/welcome.jsp。

   按一下&#x200B;**[!UICONTROL 「儲存」]**。

   >[!NOTE]
   >
   >在URL中使用完全限定的主機名稱。 建議使用HTTPS通訊協定。

   現在，AEM Forms檔案安全性已設定為使用延伸驗證與預設的AEM Forms著陸URL。

   ![](assets/third-party-authentication.png)

#### 使用自訂著陸URL {#extended-authentication-with-a-custom-landing-url}的延伸驗證

您可以使用自訂URL進行擴充驗證。 它提供以自訂品牌顯示自訂驗證頁面的彈性。 例如，您組織的品牌。

您可以將自訂驗證頁面封裝為war檔案，並將war檔案部署至AEM Forms伺服器。 war檔案包含接受使用者認證並針對AEM Forms伺服器進行驗證的完整邏輯。 AEM Forms Document Security對自訂驗證頁面有下列需求：

* 驗證頁面應以j_username和j_password的形式傳送用戶名。 該頁還應將source_url和login_url作為隱藏參數發送。
* 成功驗證時，頁面應自動關閉。

執行下列步驟，以啟用自訂著陸URL的擴充驗證：

1. 將自訂驗證war檔案部署至AEM Forms伺服器。
1. 開啟AEM Forms管理員UI。
1. 導覽至「服務> Document Security >設定>伺服器設定」。
1. 啟用「允許延伸驗證」選項並指定自訂的延伸驗證著陸URL。
1. 在&#x200B;*&lt;node name=&quot;AllowedUrls&quot;>*&#x200B;項目後，將下列項目新增至SSO節點下的config.xml檔案：

   >[!NOTE]
   >
   >&lt;entry>!!迪斯科布！!&lt;entry>!!迪斯科布！!&lt;entry>!!迪斯科布！!

   如需有關更新config.xml檔案的逐步資訊，請參閱[手動編輯Document Security設定檔案](https://helpx.adobe.com/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file)。

   現在，AEM Forms檔案安全性已設定為使用擴充驗證與自訂著陸URL

#### 在AEM Forms伺服器{#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}上設定協力廠商身分提供者的預設延伸驗證工作流程

擴充驗證可使用AEM Forms伺服器上可用的不同驗證類型。 例如，SAML, [更多範例]。

注意：如果SAML提供者是在AEM Forms伺服器上設定，則在顯示著陸URL之前，會顯示包含為SAML驗證設定之所有身分提供者的頁面。

在Acrobat中開啟受保護的檔案時，會顯示下列畫面。

#### 在AEM Forms伺服器{#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}上設定SAML提供者時的自訂擴充驗證工作流程

如果SAML提供者是在AEM Forms伺服器上設定，則在顯示著陸URL之前，會顯示包含為SAML驗證設定之所有身分提供者的頁面。

在AEM Forms伺服器上設定SAML提供者時，可設定自訂擴充驗證工作流程的網站有：

* SAML驗證是在AEM Forms伺服器上設定
* 自訂war（包含自訂驗證頁面和完整邏輯，以接受使用者認證並針對AEM Forms伺服器進行驗證）會部署至AEM Forms伺服器。

#### 使用自訂頁面列出SAML驗證{#using-custom-page-for-listing-saml-authentications}

您也可以顯示自訂頁面，以包含AEM Forms伺服器上所有設定的驗證提供者。 執行下列步驟以建立此類頁面：

1. 將自訂驗證頁面封裝為war檔案，並將war檔案部署至AEM Forms伺服器。 war檔案包含接受使用者認證並針對AEM Forms伺服器進行驗證的完整邏輯。
1. 開啟AEM Forms管理員UI，並導覽至「**[!UICONTROL 設定]**> **[!UICONTROL 使用者管理]** > **[!UICONTROL 設定]** > **[!UICONTROL SAML服務提供者設定]**」。
1. 將下列內容新增至「自訂屬性」欄位，然後按一下「儲存&#x200B;**[!UICONTROL 」。]**

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   現在，AEM Forms檔案安全性已設定為顯示包含所有已設定驗證提供者的自訂頁面。

### 取得使用者帳戶{#obtaining-a-user-account}

如果您尚未擁有Document Security帳戶，Document Security可能會在發生下列事件時啟動註冊程式：

* 想要傳送受原則保護檔案給您的Document Security使用者會將您新增至原則。
* Document Security管理員會為您建立帳戶。

在您註冊並啟用帳戶後，您可以使用受原則保護的檔案，您已獲得透過原則使用的授權。

>[!NOTE]
如果您收到受原則保護的檔案但沒有Document Security帳戶，或如果您收到註冊的邀請，請連絡將檔案傳送給您的人員以尋求協助。

如果您收到Document Security寄送的電子郵件註冊邀請，可使用電子郵件中的URL開啟線上註冊頁面進行註冊。 在您註冊後，您將會收到有關啟用帳戶的第二份通知。

#### 取得外部使用者帳戶{#obtain-an-external-user-account}

1. 開啟Document Security註冊電子郵件。 訊息包含的URL是「Document Security外部使用者註冊」頁面的連結。 如果您未收到註冊訊息，請連絡將檔案傳送給您的人員以尋求協助。
1. 按一下URL或複製URL並貼至您的瀏覽器。
1. 在適當的方塊中輸入您的名稱、組織和密碼。 您的密碼可以是8個字元的任意組合。

   >[!NOTE]
   請確定您選擇的密碼易記；找不到找出忘記密碼的方法。

1. 按一下&#x200B;**註冊**。 會出現一則訊息，通知您檢查您的電子郵件是否有啟動電子郵件訊息。
1. 開啟Document Security註冊確認電子郵件。
1. 按一下訊息中顯示的URL。
1. 按一下「登入」頁面的連結。
1. 在&#x200B;**Username**&#x200B;方塊中，輸入您在Document Security中註冊的電子郵件地址。 此電子郵件地址是您預設的Document Security使用者名稱。
1. 在&#x200B;**Password**&#x200B;方塊中，輸入您在註冊時建立的密碼。
1. 按一下&#x200B;**Login**。

### 建立和管理策略{#creating-and-managing-policies}

如果您擁有Document Security管理員的權限，則可以在Document Security網頁的「原則」頁面上建立要套用至您自己檔案的原則。

Word、Excel和PowerPoint檔案不支援在Document Security網頁中建立原則時的部分原則設定。 下表說明原則權限如何對應至Word、Excel和PowerPoint功能。

<table>
 <thead>
  <tr>
   <th><p>權限</p></th>
   <th><p>Word、Excel和PowerPoint支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>「列印&gt;不允許」</p></td>
   <td><p>不允許列印檔案。</p></td>
  </tr>
  <tr>
   <td><p>列印&gt;允許</p></td>
   <td><p>允許打印檔案。</p><p><strong>注意</strong>: <i>如果原則授予「複製」權限，但沒有「列印」權限，則可列印複製至其他檔案的內容。</i></p></td>
  </tr>
  <tr>
   <td><p>列印&gt;低解析度。 僅限</p></td>
   <td><p>不適用。</p></td>
  </tr>
  <tr>
   <td><p>變更&gt;任何</p></td>
   <td><p>可以更改檔案。</p><p>未授予此權限時，您無法修改受保護的Word和Excel檔案。 您可以修改PowerPoint檔案，但無法儲存修改檔案的變更或檢視幻燈片。</p></td>
  </tr>
  <tr>
   <td><p>變更&gt;不允許</p></td>
   <td><p>使用者無法修改受保護的檔案。</p></td>
  </tr>
  <tr>
   <td><p>變更&gt;變更頁面</p></td>
   <td><p>不適用。</p><p>包括插入、刪除和旋轉頁面。</p></td>
  </tr>
  <tr>
   <td><p>變更&gt;填寫及簽署</p></td>
   <td><p>不適用。</p></td>
  </tr>
  <tr>
   <td><p>離線</p></td>
   <td><p>檔案可離線開啟。</p></td>
  </tr>
  <tr>
   <td><p>複製</p></td>
   <td><p>檔案內容可以複製到其他檔案。</p></td>
  </tr>
  <tr>
   <td><p>螢幕閱讀程式 </p></td>
   <td><p>螢幕閱讀程式（視障使用者專用的裝置）可讀取檔案內容。</p></td>
  </tr>
  <tr>
   <td><p>權限有效性</p></td>
   <td><p>支援.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>一般設定</p></th>
   <th><p>Word、Excel和PowerPoint支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>有效期</p></td>
   <td><p>支援.</p></td>
  </tr>
  <tr>
   <td><p>審核檔案</p></td>
   <td><p>支援.</p></td>
  </tr>
  <tr>
   <td><p>自動離線租用期</p></td>
   <td><p>支援.</p></td>
  </tr>
  <tr>
   <td><p>外部授權提供者</p></td>
   <td><p>支援.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>進階設定</p></th>
   <th><p>Word、Excel和PowerPoint支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>動態水印</p></td>
   <td><p>支援.</p></td>
  </tr>
  <tr>
   <td><p>認證外掛程式</p></td>
   <td><p>不適用。</p></td>
  </tr>
  <tr>
   <td><p>加密算法和密鑰長度 </p></td>
   <td><p>支援所有選項。</p></td>
  </tr>
  <tr>
   <td><p>檔案限制</p></td>
   <td><p>不論原則中的設定為何，所有檔案內容一律會加密。</p></td>
  </tr>
  <tr>
   <td><p>存取拒絕錯誤訊息</p></td>
   <td><p>支援.</p></td>
  </tr>
 </tbody>
</table>

有關建立和管理策略的詳細資訊，請參閱[Document Security最終用戶幫助](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/)。

### 應用策略{#applying-policies}

您可以將任何可用原則套用至檔案，包括您建立的原則，以及您有權存取的屬於原則集的原則。 在套用原則之前，您必須先儲存檔案。

套用原則後，它會新增至「AEM Document Security」功能表上的「最近使用」清單，讓您更輕鬆地套用最常使用的原則。 如果您使用多個Document Security實例，「最近使用」清單只會顯示您目前連線至的伺服器的原則，或如果您尚未登入Document Security實例，則會顯示預設伺服器的原則。

>[!NOTE]
您只能將原則套用至Word檔案檔案（Microsoft Office 2010和2013中的。doc、也是。docx和。docm）、Excel活頁簿檔案（Microsoft Office 2010和2013中的。xlsx和。xlsm）以及PowerPoint簡報檔案（.ppt，也是。pptx，和。pptm）。 您無法將原則套用至Word範本檔案(.dot)、Excel範本檔案(.xlt)和PowerPoint設計範本檔案(.pot)。

#### 應用策略{#apply-a-policy}

1. 在&#x200B;**Document Security**&#x200B;標籤上的Document Security Extension for Microsoft Office 2010和2013中，選取&#x200B;**「保全>選擇原則」**。

   如果您選擇使用者名稱和密碼作為伺服器上的驗證方法，但尚未提供Document Security的登入資訊，則會出現對話方塊提示您輸入使用者名稱和密碼。

1. 從清單中選擇策略，然後按一下&#x200B;**Apply**。
1. 儲存檔案。

#### 應用最近使用的策略{#apply-a-recently-used-policy}

1. 在Document Security Extension for Microsoft Office 2010和2013的&#x200B;**「Document Security」**&#x200B;標籤上，選取「**保全> ***[原則名稱]*」。
1. 儲存檔案。

## 使用受原則保護的檔案{#usingaemdocumentsecurityextensionpolicyprotectedfiles}

受原則保護的檔案包含檔案發行者所擁有的智慧財產，且受Document Security保護。

不論您是檔案發佈者組織的內部或外部，都可以使用受原則保護的檔案。 若要開啟受原則保護的檔案，Document Security必須識別您，方法是將您加入連結的LDAP或Active Directory清單中，以本機使用者身分新增至JEE上的LiveCycle或AEM表單，或是在受邀為使用者後向Document Security註冊。

如果您收到受原則保護的檔案但沒有Document Security帳戶，或如果您收到註冊的邀請，請連絡將檔案傳送給您的人員以尋求協助。

### 在Microsoft Office {#working-with-policy-protected-files-in-microsoft-office}中使用受原則保護的檔案

Document Security Extension for Microsoft Office會限制某些Word、Excel和PowerPoint功能，以保護檔案發佈者的智慧財產。 如果您沒有變更檔案的權限，則無法儲存檔案的修改。

如果您使用受原則保護的檔案，有些產品功能可能無法使用或無法正常運作。 如果您也開啟未受保護的檔案，則未受保護的檔案會啟用大部分功能，但允許您從沒有複製或匯出權限的受原則保護檔案匯入或複製內容的功能除外。

>[!NOTE]
使用Document Security Extension支援的Office應用程式時，建議您停用Windows DEP設定。 此外，要確保在安裝了Document Security Extension並啟用了McAfee VirusScan的On-Access Scan的電腦上能夠順暢地啟動Office應用程式，請禁用McAfee VirusScan控制台中的「緩衝區溢出保護」選項。

如果功能不可用，則菜單上的命令名稱和相關工具欄按鈕將不可用。 在Document Security Extension for Microsoft Office中，當您將滑鼠指標暫留在命令或按鈕上時，工具提示會指出Document Security無法使用該命令。

### 開啟受原則保護的檔案{#opening-policy-protected-files}

您可以使用開啟任何其他檔案時所用的相同方法來開啟受原則保護的檔案。 如果您尚未登入Document Security，系統會提示您登入，除非您未連線至網際網路，而且可以離線開啟檔案。 如果您取消登入程式，存取權將遭拒。

如果您沒有開啟檔案的權限，則會通知您存取遭拒。 如果已撤銷檔案存取權限，您也可以將您導向至檔案的更新版本（如果有的話）。 如果您無法開啟受原則保護的檔案，請連絡檔案發行者以取得其他協助。

當受保護的檔案開啟時，標題列中緊接在檔案名稱后的文字會指出檔案受到AEM Document Security的保護。

從SharePoint伺服器在Document Security Extension for Microsoft Office中開啟受保護的檔案時，請確定已開啟與檔案類型（例如Microsoft Word、Microsoft Excel或Microsoft PowerPoint）相關的Microsoft Office程式。 如果您嘗試在未開啟相關應用程式的情況下開啟檔案，檔案可能無法開啟，並會顯示錯誤訊息，指出您必須安裝適用的外掛程式。 除了開啟所需的應用程式外，建議您先清除快取資料夾，再從SharePoint伺服器開啟Document Security Extension for Microsoft Office中的受保護檔案。 此外，當您從SharePoint伺服器開啟受保護的檔案時，不論套用的原則為何，檔案的所有權限都會停用。

視Document Security上實作的驗證方法而定，在開啟受保護的檔案時，可能會提示您選擇驗證方法。 如果Document Security支援多種驗證方法，就會提供驗證選項給您。 例如，如果Document Security伺服器同時提供使用者名稱／密碼和憑證驗證，您可以選擇適當的驗證方法。 如果啟用認證式驗證，系統會提示您使用您收到並安裝的認證。

開啟受保護檔案時的使用者體驗取決於伺服器上的相互驗證組態。 如果只安裝了一個有效的客戶端證書，則不會顯示驗證對話框，並且檔案會成功開啟。 但是，如果一台電腦上安裝了多個客戶端證書，則會出現驗證對話框。 使用者必須選擇有效的憑證才能開啟受保護的檔案。

### 從檔案{#removing-policy-protection-from-a-file}中刪除策略保護

如果您獲准，您可以移除已保護檔案的原則保護。 如果您這麼做，檔案將不再受到Document Security的保護。

1. 在Document Security Extension for Microsoft Office 2010和2013的&#x200B;**Document Security**&#x200B;標籤上，選取&#x200B;**Remove**。

   如果您尚未提供Document Security的登入資訊，會出現對話方塊提示您輸入使用者名稱和密碼。

>[!NOTE]
如果您無法從受保護的檔案移除原則，請連絡Document Security管理員。

### 查看安全設定{#viewing-security-settings}

您可以檢視目前檔案的列印、複製、變更和離線存取權限，以及檔案的有效期間。

在Document Security Extension for Microsoft Office 2010中，「Document Security」標籤上的「安全性狀態」群組會顯示您對檔案的權限。

執行下列動作：

* 在Document Security Extension for Microsoft Office 2010和2013的&#x200B;**「Document Security」標籤**&#x200B;中，按一下「**保全狀態**」群組中的任何項目。

### 啟用「自動套用」原則時儲存檔案{#saving-documents-when-auto-apply-policy-is-enabled}

如果您的管理員已啟用「自動套用」原則功能，當您儲存檔案時，您建立或編輯的任何檔案都會受到自動保護。

如果啟用「自動套用」原則，Document Security Extension for Microsoft Office將提示您登入Document Security伺服器。 您必須提供您的使用者名稱和密碼，才能由伺服器驗證。 如果您已提供正確的登入認證，檔案將會儲存並受到保護。

>[!NOTE]
如果您無法登入Document Security，則檔案可能會儲存，也可能不儲存。 這取決於管理員如何配置自動應用策略。 請向管理員洽詢此情況下如何處理檔案。

### 正在同步以離線訪問{#synchronizing-for-offline-access}

原則可讓您在離線且未連線至Document Security時開啟檔案。 您必須先登入Document Security，才能建立您與伺服器的認證，才能離線工作。 如果您打算離線處理檔案，建議您在中斷連線之前先與Document Security同步，以確保檔案的原則設定與伺服器保持最新狀態。 建議您在離線開啟檔案之前，先線上上開啟檔案一次。 如果您未線上上開啟檔案或與伺服器同步化，則離線時仍可使用受原則保護的檔案。 但是，離線租用期間不得已過期，而且自您上次手動或自動與伺服器同步後，檔案的原則設定不得變更。

執行下列動作：

* 在Document Security Extension for Microsoft Office 2010和2013的&#x200B;**「Document Security」**&#x200B;標籤上，選取「離線同步化」**。**

   ***附註**:即使使用者沒有檔案的離線權限，「離線同步化」按鈕仍可供使用。 但是，選擇該按鈕將不起作用。*

### 使用動態水印{#working-with-dynamic-watermarks}

Document Security Extension for Microsoft Office支援在受原則保護的檔案中加入動態文字水印。 動態水印可包含可能變更的資訊，例如日期、時間、使用者名稱或原則名稱。 如果使用者列印受原則保護的檔案，且該檔案包含動態浮水印和列印權限，則浮水印會出現在輸出中。

Document Security Extension不支援多樣化水印功能，例如PDF浮水印、浮水印中的多個元素、文字格式選項和頁面範圍。

您可使用Document Security網頁建立動態水印。 如需在受原則保護的檔案中建立和包含動態浮水印的詳細資訊，請參閱[Document Security一般使用者說明](http://www.adobe.com/go/learn_lc_euRightsMgmt_11)。

Document Security Extension for Microsoft Office提供下列浮水印功能的支援：

<table>
 <thead>
  <tr>
   <th><p>Document Security浮水印選項</p></th>
   <th><p>Word、Excel和PowerPoint支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>原則名稱</p></td>
   <td><p>支援.</p></td>
  </tr>
  <tr>
   <td><p>水印名稱</p></td>
   <td><p>支援.</p></td>
  </tr>
  <tr>
   <td><p>用作背景</p></td>
   <td><p>無論您是否選擇「用作背景」，動態水印的顯示行為都相同。</p><p>對於Word 2010和2013，動態水印只會出現在「列印版面」和「列印預覽」檢視中。 </p><p>對於Excel 2010和2013，它也會出現在「列印預覽」和「頁面配置」檢視中。</p></td>
  </tr>
  <tr>
   <td><p>垂直位置</p></td>
   <td><p>支援</p></td>
  </tr>
  <tr>
   <td><p>水準位置</p></td>
   <td><p>支援</p><p>在Excel 2010和2013中，水準放置使用點的浮水印無法運作。</p></td>
  </tr>
  <tr>
   <td><p>規模</p></td>
   <td><p>支援</p></td>
  </tr>
  <tr>
   <td><p>位置</p></td>
   <td><p>支援</p></td>
  </tr>
  <tr>
   <td><p>不透明度</p></td>
   <td><p>支援</p></td>
  </tr>
 </tbody>
</table>

### 開啟Document Security網頁{#opening-the-document-security-web-pages}

您可以開啟Document Security網頁來建立和更新您的使用者原則，以及檢視受原則保護檔案的狀態和稽核資訊。 您也可以使用Document Security網頁來變更原則或廢止受原則保護檔案的存取權。

若要開啟Document Security網頁，請在Document Security Extension for Microsoft Office 2010和2013的&#x200B;**Document Security**&#x200B;標籤上，選取&#x200B;**建立和管理原則**。 如果您尚未提供登入資訊，瀏覽器會開啟至伺服器登入頁面。

### 更改策略{#changing-policies}

如果您擁有權限（通常是Document Security管理員或檔案發行者），您稍後可以將不同的原則套用至檔案，或變更目前套用之原則的設定。

若要變更原則的設定，請使用Document Security網頁。

1. 執行下列動作：

   * 在Document Security Extension for Microsoft Office 2010或2013的&#x200B;**Document Security**&#x200B;標籤上，選取「**保全>變更保全**」。

1. 從清單中選擇策略，然後按一下&#x200B;**Apply**。

### 廢止檔案存取權限{#revoking-file-access-privileges}

您可以撤銷開啟您所保護之檔案的能力。 當您廢止檔案的存取權限時，您也可以指定對嘗試開啟檔案的任何人顯示的訊息，以及如果以修訂副本取代檔案的更新版本的URL。

1. 執行下列動作：

   * 在Document Security Extension for Microsoft Office 2010和2013的&#x200B;**Document Security**&#x200B;標籤上，選取&#x200B;**Revoke**。

   Document Security網頁會開啟至「廢止檔案」頁面。

1. 指定要顯示的訊息，以及更新版本的URL（如果有的話），然後按一下「確定」。****

如需廢止檔案存取權限的詳細資訊，請參閱[Document Security一般使用者說明](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/)。

存取權限可透過Document Security網頁恢復。

### 查看檔案審計歷史記錄{#viewing-the-file-audit-history}

Document Security可儲存受原則保護檔案的稽核記錄，讓您可以稽核使用者對檔案執行的動作。

Word、Excel和PowerPoint檔案的已審核事件包括：

**保護套用至** 檔案的新DocumentPolicy

**檢視已** 開啟的DocumentFile

**關閉** DocumentFile已關閉

**撤銷** 檔案的DocumentAccess權限

**取消撤** 銷傳回檔案的DocumentAccess權限

**修改** DocumentFile已變更並儲存在本機

**列印高解析度** 檔案列印

**從檔案中刪** 除Change Security HandlerPolicy保護

**Document Security網頁** 上的切換原則套用至檔案的新原則

### 查看檔案{#view-the-audit-history-for-a-file}的審計歷史記錄

在Document Security Extension for Microsoft Office 2010和2013的&#x200B;**Document Security**&#x200B;標籤上，選取&#x200B;**檢查步驟記錄**。

Document Security網頁會開啟至「事件」頁面，其中顯示目前檔案的已審核事件。

### Microsoft Office限制功能{#microsoft-office-restricted-features}

為保護智慧財產，當開啟受原則保護的檔案時，有些Microsoft Office功能將無法使用。 無法使用功能的清單取決於授予目前使用者的權限。 有些功能僅對受保護的檔案無法使用，而其他功能則對您處於受保護作業階段時的所有檔案無法使用。 一般而言，從開啟受原則保護的檔案到關閉應用程式或作業階段過期，您都處於受保護的作業階段。

大部分原則會授與檔案發行者完整權限。 其他使用者可能會注意到其他功能限制。

如果命令不可用，則菜單中的命令名稱和相關工具欄按鈕將呈灰色顯示。

>[!NOTE]
將原則套用至包含內嵌檔案連結的檔案時，不會將原則套用至連結的檔案。 Document Security for Microsoft Office不會將保護延伸至連結的檔案。

* 受原則保護的Word、Excel和PowerPoint檔案無法在Internet Explorer瀏覽器視窗中開啟。
* 僅獲得「更改」權限的用戶不能使用Windows剪貼簿將內容複製到其他應用程式中的檔案。 使用者可以啟用「Microsoft Office剪貼簿」選項，將內容複製到檔案。
* 在Microsoft Office中開啟受原則保護的檔案會使列印畫面金鑰無法使用，直到您關閉應用程式或工作階段過期為止。
* Document Security for Microsoft Office不支援Web型分散式製作與版本修訂(WebDAV)。 在大多數情況下，您無法從WebDAV資料夾開啟受原則保護的檔案。 如果您可以開啟受原則保護的檔案，則您沒有儲存、列印、變更或複製檔案的權限。

套用至受原則保護檔案的一般安全性包括下列限制：

在受保護作業階段期間，Word、Excel和PowerPoint中的許多常見功能可能會受到限制。

如果開啟不允許使用者進行變更的受原則保護檔案，則無法使用以任何方式變更檔案的命令。 只有開啟或建立新檔案並變更應用程式偏好設定的指令才可使用。

#### Word 2010和Word 2013限制{#word-2010-and-word-2013-restrictions}

在Word中開啟受原則保護的檔案，會使自動檔案復原資訊的儲存無法使用，直到您關閉並重新啟動Word為止。 此外，下列功能在上述情況下受到限制：

**「檔案>新增>從現有** 新增可用」，但在開啟受原則保護的檔案時，使用此命令建立的檔案無法儲存。無法將新檔案中的內容複製到其他檔案。

**「檔案>儲** 存」受「變更」權限限制。

**「檔案>另存新** 檔」(Save AsAll)選項受「變更」(Change)權限的限制。

**「檔案>列** 印」所有選項受「列印」權限的限制。無法使用，除非原則允許高解析度列印。

**「檔案>儲存與傳** 送全部」選項在受保護作業階段期間無法使用。

**「檔案>資訊>保護檔案>使用密碼加密」、「新增數位簽章」、「標示為完稿」、「依人員限制權限」在受保護的工作階段** 期間無法使用。

**「檔案>工** 作流程在受保護作業階段期間無法使用」。

***注意&#x200B;**:從2010年Microsoft Office系統版本的Word、Excel和PowerPoint開始工作流程的功能，僅適用於Office Professional Plus 2010、Office Enterprise 2010和Office Ultimate 2010套件，以及2010年Office獨立版本這些計畫。*

**在受保護作業階** 段期間，部落格文章> PublishUnavailable。

**「檔案>伺服器>檔案伺服器工作功能表」** 在受保護作業階段期間無法使用。

**「首頁」>「剪貼簿」>「** 複製受到複製」權限的限制。如果不允許複製，則複製的內容無法貼至任何其他檔案或Office剪貼簿。 如果使用者擁有變更權限，則可在受保護檔案中複製內容。

**「首頁」>「剪貼簿」>「** 貼上受變更」權限限制。

**「首頁」>「剪貼簿」>「貼上特殊」** 受「變更」權限的限制。

**在受保護作業階段期** 間，「插入>文字>物件不可用」。受原則保護的檔案無法隨時插入。

**郵** 件在受保護作業階段期間，此標籤上的大多數選項都無法使用。

**「檢閱>校對>研** 究受複製權限限制」。如果不允許複製，則無法使用。

**「檢閱>校對>同義** 字」受「複製」權限限制。如果不允許複製，則無法使用。

**「檢閱>語言>翻譯>使用「復** 制」權限翻譯DocumentEnabled」。

**「檢閱>語言>翻譯>使用「複製」權限** 翻譯選取的文字」。

**「檢閱>語言>翻譯>使用「復** 制」權限啟用迷你翻譯器」。

**在受保護作業階段期** 間，「檢閱>比較>不可用比較」。受原則保護的檔案無法隨時比較。

**「檢閱>保護>封鎖作** 者在受保護作業期間無法使用」。

**「檢閱>保護>限制編輯」** 在受保護作業階段期間無法使用。

**「查看」>「** 宏」某些宏受到「複製」權限的限制，除非允許複製，否則無法使用。

**增益集** 無法在受保護作業階段期間新增或移除。

**線上協** 作在受保護作業階段期間無法使用。

**主檔案和** 子檔案在主檔案中開啟時，子檔案受主檔案原則的規範。如果單獨開啟，則無法打印、複製或修改子文檔。

**在受保** 護的作業階段期間重新總結無法使用。

**幀（和所有相關命令）在受保** 護會話期間不可用。

**檔案面** 板在受保護作業階段期間無法使用。

**「開發人員>檔案范** 本」在受保護作業階段期間無法使用。若要存取此命令，請選取「檔案>選項>自訂>開發人員標籤>範本>檔案範本」。

**「大綱>主檔案>建立子檔案」、「在受保護作業階** 段期間插入子檔案無法使用」。

#### Excel 2010和Excel 2013限制{#excel-2010-and-excel-2013-restrictions}

下列功能在上述情況下受到限制：

**「檔案>新增>從現有可用** 新增」，但無法儲存在受保護作業階段期間使用此命令建立的檔案。無法將新檔案中的內容複製到其他檔案。

**「檔案>儲存」、「另** 存為受變更」權限限制。

**「檔案>另存新檔>** PDF」在受保護作業階段期間可用。

**「檔案>列** 印」受「列印」權限限制。無法使用，除非原則允許高解析度列印。

**「檔案>資訊>保護文** 件在受保護作業階段期間無法使用」。

**「檔案>資訊>保護活頁簿」** 在受保護作業階段期間無法使用。

**「檔案>儲存與傳送** 不可用」（在受保護作業階段期間）。

**「檔案>選項>增益集」** 在受保護作業階段期間無法新增或移除。

**「檔案>工** 作流程在受保護作業階段期間無法使用」。

***注意&#x200B;**:從2010年Microsoft Office系統版本的Word、Excel和PowerPoint開始工作流程的功能，僅適用於Office Professional Plus 2010、Office Enterprise 2010和Office Ultimate 2010套件，以及2010年Office獨立版本這些計畫。*

**「檔案>伺服器>檔案伺服器工作功能表」** 在受保護作業階段期間無法使用。

**「首頁」>「剪貼簿」>「** 複製受到複製」權限的限制。如果不允許複製，則複製的內容無法貼至任何其他檔案或Microsoft Office剪貼簿。 如果使用者擁有變更權限，則可在受保護檔案中複製內容。

**「首頁」>「剪貼簿」>「** 貼上受變更」權限限制。

**「首頁」>「剪貼簿」>「貼上特殊」** 受「變更」權限的限制。

**「首頁>儲存格>格式>移動或複製工作表」** 在受保護作業階段期間無法使用。

**「首頁>儲存格>插入>插入工作表」** 在受保護作業階段期間無法使用。

**「首頁>儲存格>刪除>刪除工作** 表在受保護作業階段期間無法使用」。

**「首頁>編輯>填滿>跨工作表」** 受「變更」權限的限制。

**「插入」(Insert)>「表格」(Tables)>「表格」(** Table)「受到更改」(Change)權限的限制。

**無法在「建立向** 導」中選擇「插入」>「表」>「透視表受策略保護的檔案」。

**在受保護作業階段期** 間，「插入>文字>物件不可用」。受原則保護的檔案無法隨時插入。

**「插入>文字>頁首和頁尾」** 受「變更」權限的限制。受原則保護的檔案無法使用。

**無法匯入「資料>從受** 原則保護的檔案取得外部資料」。

**「資料>大綱>小** 計」受「變更」權限限制。

**「資料>資料工具>資料驗** 證」受「變更」權限限制。

**「檢閱>校對>研** 究受複製權限限制」。

**「檢閱>校對>同義** 字」受「複製」權限限制。

**「檢閱>語言>轉** 譯受複製權限限制」。

**「檢閱>變更>保護工作** 表在受保護作業階段期間無法使用」。

**「檢閱>變更>保護活頁簿」** 在受保護作業階段期間無法使用。

**「檢閱>變更>共用活頁簿」** 在受保護作業階段期間無法使用。

**「檢閱>變更>保護並共用活頁簿」在受保** 護的作業階段期間無法使用。

**「檢閱>變更>允許使用者在受保護作業階** 段期間編輯範圍無法使用」。

**「檢閱>變更>追蹤變更>反白顯示變** 更無法用於包含動態浮水印的受原則保護檔案。

**「查看」>「** 宏」受「更改」權限的限制。

**「檢視>儲存工** 作區命令」無法運作。

**開發人員> XML >擴展包** 某些宏受到「複製」權限的限制，除非允許複製，否則無法使用。

**「公式」>「公式審計」>「錯** 誤檢查」受「更改」權限限制。除非允許變更，否則無法使用。

**線上協** 作在受保護作業階段期間無法使用。

**在受保護作業階** 段期間儲存自動復原資訊無法使用。

***注意&#x200B;**:如果您嘗試變更您無權變更之受原則保護檔案中的儲存格，Excel會顯示錯誤的警告訊息，指出您必須使用「取消保護工作表」命令，從檔案中移除保護。使用「取消保護工作表」命令不會從檔案中刪除策略保護。*

#### PowerPoint 2010和PowerPoint 2013限制{#powerpoint-2010-and-powerpoint-2013-restrictions}

下列功能在上述情況下受到限制：

**「檔案>新增>從現有可用** 新增」，但無法儲存在受保護作業階段期間使用此命令建立的檔案。無法將新檔案中的內容複製到其他檔案。

**「檔案>儲** 存」受「變更」權限限制。

**「檔案>另存新** 檔」(Save AsAll)選項受「變更」(Change)權限的限制。

**「檔案>列** 印」所有選項受「列印」權限的限制。無法使用，除非原則允許高解析度列印。

**「檔案>儲存與傳送** 不可用」（在受保護作業階段期間）。

**「檔案>資訊>保護簡報>使用密碼加密、新增數位簽章、標示為完稿、依人員限制權限在受保護作業階** 段期間無法使用」。

**「檔案> PowerPoint選項>儲存自動復原資訊」在受** 保護的作業階段期間無法使用。

**「檔案>伺服器>檔案伺服器工作功能表」** 在受保護作業階段期間無法使用。

**「首頁」>「剪貼簿」>「** 複製受到複製」權限的限制。如果不允許複製，則複製的內容無法貼在檔案、任何其他檔案或Office剪貼簿中。 如果使用者擁有變更權限，則可在受保護檔案中複製內容。

**「首頁」>「剪貼簿」>「** 貼上受變更」權限限制。如果不允許複製，則複製的內容無法貼在檔案中。

**「首頁」>「剪貼簿」>「貼上特殊」** 受「變更」權限的限制。

**「首頁>投影片>新增投影片>來自外框的投影片、重複使用投** 影片在受保護作業階段期間無法使用」。

**在受保護作業階段期** 間，「插入>文字>物件不可用」。受原則保護的檔案無法隨時插入。

**設計>背景>背景樣式、隱藏背景圖形、格式** 背景不可用於包含動態水印的受原則保護檔案。

**「投影片放映>設定>錄制投影片放映」** 受變更權限限制。

**「檢閱>校對>同義** 字」受「複製」權限限制。

**「檢閱>語言>轉** 譯受複製權限限制」。

**「檢閱>語言>翻譯>使用「復** 制」權限啟用迷你翻譯器」。

**「檢視>簡報檢視>投影片放映」** 受「變更」權限的限制。如果不允許變更，則無法在修改檔案時檢視投影片。

**「查看」>「** 宏」某些宏受到「複製」權限的限制，除非允許複製，否則無法使用。

**增益集** 無法在受保護作業階段期間新增或移除。

**線上協** 作在受保護作業階段期間無法使用。

## 使用協力廠商驗證提供者{#use-third-party-authentication-providers}

您可以搭配AEM Forms Document Security使用協力廠商驗證提供者。 這些驗證提供者可協助您新增額外的存取層至受保護的檔案。 AEM Forms Document Security支援下列延伸驗證工作流程：

* 使用預設AEM Forms URL的擴充驗證
* 使用自訂URL的擴充驗證
* 在JEE伺服器上的AEM Forms上設定協力廠商身分提供者的預設延伸驗證工作流程
* 自訂擴充驗證工作流程，其中第三方身分提供者已設定在JEE伺服器上的AEM Forms
* 使用自訂頁面列出SAML驗證的擴充驗證

如需設定延伸驗證工作流程的詳細步驟，請參閱[延伸驗證藍本](http://blogs.adobe.com/livecycle/2011/12/extended-authentication-scenarios.html)文章

## 字彙表 {#glossary}

如需有關JEE術語的LiveCycle和AEM表單資訊，請參閱[辭彙表](http://www.adobe.com/go/learn_aemforms_designer_65)。
