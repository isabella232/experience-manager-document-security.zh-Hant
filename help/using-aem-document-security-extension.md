---
title: 使用 Microsoft Office 適用的 AEM Document Security Extension
description: 您可以控制收件人如何使用受原則保護的檔案；無論檔案分發的範圍有多廣，您都可以控制。本文件旨在說明如何保護檔案，以及如何使用受保護的檔案。
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
exl-id: 667a9718-b865-4911-96c2-7c08f75e0732
source-git-commit: 13c487b13acb0d65f02301c881bfade512428bcd
workflow-type: tm+mt
source-wordcount: '6252'
ht-degree: 100%

---

# 使用 Microsoft Office 適用的 AEM Document Security Extension{#using-aem-document-security-extension-for-microsoft-office}

## 使用 AEM Document Security Extension 來保護檔案 {#usingaemdocumentsecurityextensiontoprotectfiles}

您可以控制收件人如何使用受原則保護的檔案；無論檔案分發的範圍有多廣，您都可以控制。

使用 Microsoft Office 適用的 Document Security Extension，您可執行這些工作：

* 設定您與 Document Security 的連線
* 套用原則至檔案中
* 開啟 Document Security 網頁，以建立和管理用戶原則
* 從檔案中移除原則保護
* 變更檔案已套用的原則
* 開啟 Document Security 網頁，撤銷檔案的存取權限或變更檔案所用的原則
* 開啟 Document Security 網頁，檢視檔案的稽核歷史記錄

### 連線至 Document Security 的伺服器 {#connect-to-a-document-security-server}

如果您的目的是要套用原則至檔案中，您必須要設定 Document Security 的連線設定。根據 Microsoft Office 適用的 Document Security Extension 安裝方式，您可能已有預設的連線設定。您可以為一個或多個 Document Security 的執行個體新增連線設定。您可以向 Document Security 管理員取得伺服器資訊。

對於要用來保護檔案或管理受保護檔案的伺服器，您必須將其設定為預設的伺服器。當您在新檔案中套用原則或開啟 Document Security 網頁時，Microsoft Office 適用的 Document Security Extension 將連線至預設的伺服器。如果使用超過一個 Document Security 的執行個體，則伺服器之間切換時必須變更預設的伺服器設定。只要您獲得開啟檔案的授權，您就可以開啟任何受 Document Security 執行個體保護的檔案。

如果您的 Document Security 伺服器採用憑證式驗證，則您需要在本機電腦上安裝您所收到的憑證。您將需依規定選擇憑證驗證，並提供要用來驗證的憑證。

當您在 Microsoft Office 應用程式中設定 Document Security 執行個體的連線設定後，此設定即適用於 Word、Excel 和 PowerPoint 等所有應用程式。

#### 安裝用戶端憑證 {#install-the-client-side-certificate}

如果您需依規定透過憑證式驗證或兩步驟驗證來存取 Document Security 網頁，則您將在本機電腦上收到您必須安裝的憑證。您會收到一個憑證檔案 (.PFX 或 .P12 檔案) 及其密碼。

1. 將憑證檔案儲存在本機電腦中。
1. 按兩次憑證檔案以開啟憑證匯入精靈，並且按一下「**下一步**」。
1. 如果憑證檔案列在檔案名稱方框中，按一下「**下一步**」。如果您想找另一個憑證，按一下「**瀏覽**」。
1. 輸入您收到的密碼，然後按一下「**下一步**」。
1. 在「憑證儲存」對話框中，選取「將所有憑證放在下列存放區中」，然後按一下「**瀏覽**」。
1. 在「選取憑證存放區」對話框中，選取「個人」，按一下「**確定**」，按一下「**下一步**」，然後按一下「**完成**」。

#### 設定連線設定 {#configure-connection-settings}

1. 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**選擇伺服器**」。
1. 按一下「**新增**」以建立新的連線設定；或者，選取現有連線並按一下「**編輯**」。
1. 在「**名稱**」方框中，輸入連線的名稱。您可以使用任何名稱。
1. 在「**伺服器位址**」方框中，輸入伺服器的位址。
1. 在「**連接埠**」方框中，輸入伺服器連接埠。
1. (選項) 如果要記住您的用戶名稱和密碼，請選取「**記住此電腦的密碼**」，並在相關的方框中輸入您的用戶名稱和密碼。如果其他人可以存取此電腦，則建議您不要選取此選項。
1. 按一下「**連線至此伺服器**」。Microsoft Office 適用的 Document Security Extension 嘗試連線到您指定的伺服器。請根據被指定的憑證，執行以下其中一項操作：

   **用戶名稱和密碼**

   輸人您從 Document Security 管理員取得的用戶名稱和密碼。

   **憑證驗證**

   選擇此選項，以選取您收到並安裝在個人憑證存放區中的憑證。

   如果 Document Security 僅設定一種驗證類型，則只會顯示該選項。

>[!NOTE]
>
>如果您無法連線到伺服器，請嘗試在 Internet Explorer 中開啟 Document Security 網頁。如果無法使用 Internet Explorer 連線到伺服器，或者如果對話框顯示有關伺服器憑證的警告，則 Microsoft Office 適用的 Document Security Extension 無法連線到伺服器。請聯絡伺服器管理員取得協助。

>[!NOTE]
>
>如果無法連線到 Document Security，則會顯示一項訊息指出：「用戶名稱和密碼不正確，請查看您的設定，然後重試」。如果由於其他原因無法連線，則可能會顯示此訊息。如果您是第一次連線到伺服器，請驗證您的伺服器名稱和連接埠設定是否正確。

#### 指定預設伺服器 {#specify-the-default-server}

1. 請執行下列動作：

   * 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**選擇伺服器**」。

1. 選取要指定為預設的伺服器，然後按一下「**設定預設**」。預設伺服器旁邊會顯示星號。

### 使用協力驗證服務提供者 {#using-third-party-authentication-providers}

您可以使用有 AEM Forms Document Security 的協力驗證服務提供者。這些驗證服務提供者會幫助您在受保護的文件上另增一個存取層。AEM Forms Document Security 可支援以下的延伸驗證工作流程：

* 使用預設的 AEM Forms URL 的延伸驗證
* 使用自訂 URL 的延伸驗證
* 透過在 JEE 伺服器 AEM Forms 設定的協力身分識別服務提供者，使用預設延伸驗證工作流程
* 透過設定在 JEE 伺服器 AEM Forms 的協力身分識別服務提供者，使用自訂延伸驗證工作流程
* 使用特訂頁面的延伸驗證，以列出 SAML 驗證

#### 使用預設的 AEM Forms URL 的延伸驗證 {#extended-authentication-using-default-aem-forms-url}

您可為延伸驗證使用預設的 AEM Forms URL。預設登陸頁面包含 Adobe 品牌。此外，為延伸驗證使用預設 AEM Forms URL 時，會使用預設的 AEM Forms 設定。

執行以下步驟，透過預設的 Adobe 登陸 URL 啟用延伸驗證：

1. 開啟 AEM Forms 管理 UI。
1. 瀏覽至「服務 > Document Security > 設定 > 伺服器設定」。
1. 啟用「允許延伸驗證」選項
1. 指定預設的 URL 延伸驗證登陸 URL。預設 URL 為 http://localhost:8080/edc/extendedauthentication/welcome.jsp。

   按一下「**[!UICONTROL 儲存]**」。

   >[!NOTE]
   >
   >在 URL 中使用完整主機名稱。建議使用 HTTPS 協定。

   現在，AEM Forms Document Security 設定為使用延伸驗證及預設的 AEM Forms 登陸 URL。

   ![](assets/third-party-authentication.png)

#### 使用自訂登陸 URL 的延伸驗證 {#extended-authentication-with-a-custom-landing-url}

您可為延伸驗證使用自訂 URL。這樣可具備彈性以顯示有自訂品牌的自訂驗證頁面。例如，管理組織的品牌。

您可將自訂驗證頁面封裝在 WAR 檔案中，並將該 WAR 檔案部署至 AEM Forms 伺服器。WAR 檔案含有完整邏輯，可接受對 AEM Forms 伺服器的用戶憑證和驗證。AEM Forms Document Security 有以下對自訂驗證頁面的規定：

* 驗證頁面應發送 j_username 的用戶名稱和 j_password 的密碼。該頁面還應該發送 source_url 和 login_url 的隱藏參數。
* 驗證成功後，頁面應自動關閉。

執行以下步驟，透過自訂的登陸 URL 啟用延伸驗證：

1. 將自訂驗證 War 檔案部署到 AEM Forms 伺服器。
1. 開啟 AEM Forms 管理 UI。
1. 瀏覽至「服務 > Document Security > 設定 > 伺服器設定」。
1. 啟用「允許延伸驗證」選項，並指定自訂的延伸驗證登陸 URL。
1. 將以上項目新增至 SSO 節點下的 config.xml 檔案，但在項目 *&lt;node name=“AllowedUrls“>* 後面：

   >[!NOTE]
   >
   >&lt;entry key=”sso-l” value=”/ sample_/login.jsp”/>!!discoiqbr!!&lt;entry key=”sso-s” value=”/ sample_/welcome.jsp”>!!discoiqbr!!&lt;entry key=”sso-o” value=”/ sample_/logout.jsp”/>!!discoiqbr!!

   關於更新 config.xml 檔案的詳細步驟資訊，請參閱 [手動編輯 Document Security 設定檔案](https://helpx.adobe.com/tw/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file)。

   現在，AEM Forms Document Security 設定為透過自訂 AEM Forms 登陸 URL 使用延伸驗證

#### 透過設定在 AEM Forms 伺服器的協力身分識別服務提供者，使用預設延伸驗證工作流程 {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

延伸驗證可以使用 AEM Forms 伺服器上可用的不同類型驗證。例如，SAML，[還有什麼例子]。

註：如果在 AEM Forms 伺服器上設定 SAML 服務提供者，那麼在顯示登陸 URL 以前，系統會先顯示設定進行 SAML 驗證的全部身分識別服務提供者。

在 Acrobat 開啟受保護文件時，系統將顯示以下畫面。

#### 在 AEM Forms 伺服器上設定 SAML 服務提供者時，使用自訂延伸驗證工作流程 {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

如果在 AEM Forms 伺服器上設定 SAML 服務提供者，那麼在顯示登陸 URL 以前，系統會先顯示設定進行 SAML 驗證的全部身分識別服務提供者。

在 AEM Forms 伺服器上設定 SAML 服務提供者時，要設定自訂延伸驗證工作流程的先決條件：

* 在 AEM Forms 伺服器上設定 SAML 驗證
* 自訂 WAR 檔案含有自訂驗證頁面和完整邏輯，可接受對 AEM Forms 伺服器的用戶憑證和驗證；將自訂 WAR 檔案部署至 AEM Forms 伺服器。

#### 使用特訂頁面列出 SAML 驗證 {#using-custom-page-for-listing-saml-authentications}

您也可顯示自訂頁面，以提供設定在 AEM Forms 伺服器的所有驗證服務提供者。若要建立這類頁面，請執行下列步驟：

1. 將自訂驗證頁面封裝在 WAR 檔案中，並將該 WAR 檔案部署至 AEM Forms 伺服器。WAR 檔案含有完整邏輯，可接受對 AEM Forms 伺服器的用戶憑證和驗證。
1. 開啟 AEM Forms 管理 UI 並瀏覽至「**[!UICONTROL 設定]**> **[!UICONTROL User Management]** > **[!UICONTROL 設定]** > **[!UICONTROL SAML 服務提供者設定]**」。
1. 新增下列至自訂屬性欄位，然後按一下「**[!UICONTROL 儲存]**」。

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   現在，AEM Forms Document Security 已設定為顯示包含所有已設定驗證服務提供者的自訂頁面。

### 取得用戶帳戶 {#obtaining-a-user-account}

如果您還沒有 Document Security 帳戶，則當下列情況發生時，Document Security 功能可能會啟動註冊程序：

* 想將受原則保護的檔案發送給您的 Document Security 用戶要將您加入原則中。
* Document Security 管理員會為您建立帳戶。

當您註冊並啟用帳戶後，即可以使用您已有權使用原則的受原則保護檔案。

>[!NOTE]
>
>如果您收到受原則保護的檔案，且沒有 Document Security 帳戶，或者如果您收到註冊邀請，請與向您發送文件的人聯絡以尋求幫助。

如果您收到來自 Document Security 的電子郵件註冊邀請，則您可以使用電子郵件中的 URL 進行註冊，以便開啟打開線上註冊頁面。註冊後，您將收到關於啟用帳戶的第二次通知。

#### 取得外部用戶帳戶 {#obtain-an-external-user-account}

1. 開啟 Document Security 註冊電子郵件。此訊息提供的 URL 是前往「Document Security外部用戶註冊」頁面的連結。如果您沒有收到註冊訊息，請與向您發送檔案的人聯絡以尋求幫助。
1. 請按一下 URL，或將其複製貼到您的瀏覽器。
1. 在對應的方框中輸入您的姓名、組織和密碼。您的密碼可以是八個字元的任意組合。

   >[!NOTE]
   >
   >確保選擇易記住的密碼；目前沒有方法可以找到忘記的密碼。

1. 按一下「**註冊**」。系統會顯示訊息，通知您查看電子郵件中的啟用電子郵件訊息。
1. 開啟 Document Security 註冊的確認電子郵件。
1. 按一下訊息中顯示的 URL。
1. 按一下連結，即可前往登入頁面。
1. 在「**用戶名稱**」方框中，輸入您在 Document Security 下已註冊的電子郵件地址。該電子郵件地址是您預設的 Document Security 用戶名稱。
1. 在「**密碼**」方框中，輸入您註冊時建立的密碼。
1. 按一下「**登入**」。

### 建立和管理您的原則 {#creating-and-managing-policies}

如果您擁有 Document Security 管理員的權限，則在 Document Security 網頁的「原則」頁面上，您可以建立自己檔案所要套用的原則。

Word、Excel 和 PowerPoint 檔案不支援在 Document Security 網頁中建立原則可用的部分原則設定。以下表格可說明原則權限如何對應到 Word、Excel 和 PowerPoint 功能。

<table>
 <thead>
  <tr>
   <th><p>權限</p></th>
   <th><p>Word、Excel 和 PowerPoint 支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>列印 &gt; 不允許</p></td>
   <td><p>不允許列印檔案。</p></td>
  </tr>
  <tr>
   <td><p>列印 &gt; 允許</p></td>
   <td><p>允許列印檔案。</p><p><strong>注意</strong>：<i>如果原則授予複製權限而不授予列印權限，則可以列印複製到另一個檔案的內容。</i></p></td>
  </tr>
  <tr>
   <td><p>列印 &gt; 低解析度。僅限</p></td>
   <td><p>不適用。</p></td>
  </tr>
  <tr>
   <td><p>變更 &gt; 任何</p></td>
   <td><p>檔案可以變更。</p><p>如果未獲得此權限，則無法修改受保護的 Word 和 Excel 檔案。您可以修改 PowerPoint 檔案，但不能儲存變更或檢視已修改檔案的幻燈片。</p></td>
  </tr>
  <tr>
   <td><p>變更 &gt; 不允許</p></td>
   <td><p>用戶無法修改受保護的檔案。</p></td>
  </tr>
  <tr>
   <td><p>變更 &gt; 修改頁面</p></td>
   <td><p>不適用。</p><p>包含插入、刪除和旋轉頁面。</p></td>
  </tr>
  <tr>
   <td><p>變更 &gt; 填寫與簽署</p></td>
   <td><p>不適用。</p></td>
  </tr>
  <tr>
   <td><p>離線</p></td>
   <td><p>檔案可以離線開啟。</p></td>
  </tr>
  <tr>
   <td><p>複製</p></td>
   <td><p>檔案內容可以復製到其他檔案。</p></td>
  </tr>
  <tr>
   <td><p>螢幕閱讀器 </p></td>
   <td><p>螢幕閱讀器 (視力障礙用戶的裝置) 可以讀取檔案內容。</p></td>
  </tr>
  <tr>
   <td><p>權限有效性</p></td>
   <td><p>支援。</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>一般設定</p></th>
   <th><p>Word、Excel 和 PowerPoint 支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>有效期限</p></td>
   <td><p>支援。</p></td>
  </tr>
  <tr>
   <td><p>審核文件</p></td>
   <td><p>支援。</p></td>
  </tr>
  <tr>
   <td><p>自動離線租期</p></td>
   <td><p>支援。</p></td>
  </tr>
  <tr>
   <td><p>外部授權服務提供者</p></td>
   <td><p>支援。</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>進階設定</p></th>
   <th><p>Word、Excel 和 PowerPoint 支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>動態浮水印</p></td>
   <td><p>支援。</p></td>
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
   <td><p>文件限制</p></td>
   <td><p>無論原則如何設定，所有檔案內容一定會加密。</p></td>
  </tr>
  <tr>
   <td><p>存取被拒的錯誤訊息</p></td>
   <td><p>支援。</p></td>
  </tr>
 </tbody>
</table>

若要了解建立和管理原則的更多資訊，請參閱 [Document Security 用戶說明](http://help.adobe.com/zh_TW/AEMForms/6.1/RMHelp/)。

### 套用原則 {#applying-policies}

您可以將任何可用原則套用至檔案中，包括您所建立的原則，以及您有存取權的原則集所屬的原則。在套用原則之前，您必須儲存檔案。

在套用原則以後，原則會新增至 AEM Document Security 選單上的「最近使用」列表中，這樣您便更易套用最常用的原則。如果您使用多個 Document Security 執行個體，則「最近使用」列表將顯示您目前所連線伺服器或預設伺服器的原則 (如果尚未登至 Document Security 執行個體)。

>[!NOTE]
>
>您只能將原則套用在 Word 文件檔案 (Microsoft Office 2010 和 2013 中的 .doc、also.docx 和 .docm)、Excel 活頁簿檔案 (Microsoft Office 2010 和 2013 中的 .xls、also.xlsx 和 .xlsm)，以及 PowerPoint 簡報檔案 (Microsoft Office 2010 和 2013 中的 .ppt、.pptx 和 .pptm)。您不能將原則套用在 Word 範本檔案 (.dot)、Excel 範本檔案 (.xlt) 和 PowerPoint 範本檔案 (.pot)。

#### 套用一項原則 {#apply-a-policy}

1. 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**安全性 > 選擇原則**」。

   如果您選擇用戶名稱和密碼作為伺服器的驗證方法，且您尚未提供 Document Security 的登入資訊，則會出現對話框提示您輸入用戶名稱和密碼。

1. 從清單中選取一項原則，並按一下「**套用**」。
1. 儲存檔案。

#### 套用最近使用的原則 {#apply-a-recently-used-policy}

1. 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**安全性 > ***[原則名稱]*」。
1. 儲存檔案。

## 使用受原則保護的檔案 {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

受原則保護的檔案包含檔案發佈者擁有並受 Document Security 保護的智慧財產。

無論是在檔案發佈者組織的內部或外部，您都可以使用受原則保護的檔案。若要開啟受原則保護的檔案，您必須獲得 Document Security 認可，方法是透過連結的 LDAP 或 Active Directory 清單內容被新增為 JEE 上的 LiveCycle 或 AEM Forms 本機用戶，或在被邀請後向註冊 Document Security 的用戶。

如果您收到受原則保護的檔案，且沒有 Document Security 帳戶，或者如果您收到註冊邀請，請與向您發送文件的人聯絡以尋求幫助。

### 使用 Microsoft Office 中受原則保護的檔案 {#working-with-policy-protected-files-in-microsoft-office}

Microsoft Office 適用的 Document Security Extension 會限制 Word、Excel 和 PowerPoint 部分功能，這是為了保護檔案發佈者的智慧財產。如果您沒有變更檔案的權限，您就無法儲存修改內容。

如果您是使用受原則保護的檔案，則某些產品功能可能不適用或無法正常使用。如果您還打開了未受保護的檔案，則該檔案的大多數功能都可供使用，但您無法從自己沒有複製或匯出權限的受原則保護檔案中匯入或複製內容。

>[!NOTE]
>
>在使用有 Document Security Extension 支援的 Office 應用程式時，建議您停用 Windows DEP 設定。同時，若電腦有已安裝的 Document Security Extension，並有已啟用即時 (On-Access) 掃描的 McAfee VirusScan，為了確保此電腦能順利啟動 Office 應用程式，請停用 McAfee VirusScan 控制台中的「緩衝區溢位保護」選項。

如果有某個功能無法使用，則選單上的命令名稱和相關的工具欄按鈕將不適用。在 Microsoft Office 適用的 Document Security Extension 中，當您將滑鼠指標停留在命令或按鈕上時，工具提示會指出該命令因 Document Security 而無法使用。

### 開啟受原則保護的檔案 {#opening-policy-protected-files}

您能採用與開啟任何其他檔案相同的方法，開啟受原則保護的檔案。如果您還未登入使用 Document Security，系統會提示您登入並使用；除非您未連線至網際網路，且是在離線下開啟檔案。如果您取消登入程序，您的拒絕就會被拒絕。

如果您沒有開啟檔案的權限，您就會收到存取被拒的通知。如果檔案存取權限被撤銷，系統就會將您導向最新版的檔案 (若有適用版本)。如果無法開啟受原則保護的檔案並需要更多協助，請與檔案發佈者聯絡。

在開啟受保護的檔案時，檔案名稱後的標題列內容會指出該檔案受到 AEM Document Security 的保護。

從 SharePoint 伺服器 Microsoft Office 適用的 Document Security Extension 中開啟受保護的文件時，請確保與該檔案類型有關聯的 Microsoft Office 程式已開啟，如 Microsoft Word、Microsoft Excel 或 Microsoft PowerPoint。如果要試著在不開啟相關應用程式的情况下開啟檔案，檔案可能無法開啟，且系統會顯示錯誤訊息並指出您必須安裝適用的外掛程式。從 SharePoint 伺服器 Microsoft Office 適用的 Document Security Extension 中開啟受保護的文件以前，除了要開啟必要的應用程式以外，另外建議您要先清除快取檔案夾。此外，當您從 SharePoint 伺服器開啟受保護的文件時，不論是否套用原則，文件上所有權限皆為停用狀態。

當您開啟受保護的文件時，系統可能會提示您選擇驗證方法，實際情形取決於 Document Security 所執行的驗證方法。如果 Document Security 支援多種驗證方法，系統會向您顯示驗證選項。例如，如果 Document Security 伺服器同時提供用戶名稱/密碼和憑證驗證的方法，則可以選擇適合的驗證方法。如果啟用憑證式驗證，系統將提示您使用已收到並安裝的憑證。

在開啟受保護檔案時，用戶體驗取決於伺服器上的相互驗證設定。如果只安裝一個有效的用戶端憑證，則不會出現驗證對話框，且檔案會順利開啟。但是，如果一台電腦上安裝了多個用戶端憑證，則會出現驗證對話框。用戶必須選擇有效的憑證，才能開啟受保護的檔案。

### 從檔案中移除原則保護 {#removing-policy-protection-from-a-file}

如果允許，您可以從已受保護的檔案中移除原則保護。如果這樣做，檔案將不再受 Document Security 的保護。

1. 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**移除**」。

   如果您尚未提供 Document Security 的登入資訊，則會出現對話框提示您輸入用戶名稱和密碼。

>[!NOTE]
>
>如果您無法從已受保護的檔案中移除原則，請與文件安全管理員聯絡。


### 檢視安全性設定 {#viewing-security-settings}

您可以檢視目前檔案的列印、複製、變更和離線存取等權限以及檔案有效期限。

在 Microsoft Office 2010 適用的 Document Security Extension 中，在「Document Security」標籤上的安全性狀態群組會顯示您的檔案權限。

請執行下列動作：

* 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在&#x200B;**「Document Security」標籤**&#x200B;的「**安全性狀態**」群組上，按一下任何項目。

### 當啟用自動套用原則時儲存文件 {#saving-documents-when-auto-apply-policy-is-enabled}

如果管理員已啟用「自動套用原則」功能，當您儲存檔案時，您建立或編輯的任何文件皆會自動受到保護。

如果啟用自動套用原則，Microsoft Office 適用的 Document Security Extension 將提示您登入 Document Security 伺服器。您需要提供用戶名稱和密碼，才能獲得伺服器的驗證。如果您提供了正確的登入憑證，文件將會儲存並受到保護。

>[!NOTE]
>
>如果您無法登入使用 Document Security，則文件可能會或不會儲存；實際情形取決於管理員如何設定自動套用原則。向管理員查詢，在這種情況下會如何處理文件。

### 離線存取的同步處理 {#synchronizing-for-offline-access}

原則可讓您在離線且未連線到 Document Security 時開啟檔案。在離線工作之前，您必須先登入使用 Document Security，並在伺服器上建立您的憑證。如果您打算離線處理檔案，建議您在中斷連線以前與 Document Security 同步處理，以確保伺服器上的檔案使用最新的原則設定。在離線開啟檔案以前，建議您也在線上開啟該檔案一次。如果您未在線上開啟檔案或未與伺服器同步處理，您仍然可在離線時使用受原則保護的檔案。但是，離線租期不得過期，且在上次手動或自動與伺服器同步處理後，檔案的原則設定不得有任何變更。

請執行下列動作：

* 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**離線同步處理**」。

   ***注意**：即使用戶沒有文件的離線權限，也可以使用「離線同步處理」按鈕。但是，選取按鈕不會起任何作用。*

### 使用動態浮水印 {#working-with-dynamic-watermarks}

Microsoft Office 適用的 Document Security Extension 支援受原則保護文件含有的文字式浮水印。動態浮水印可以包含可能變更的資訊，例如日期、時間、用戶名稱或原則名稱。如果用戶列印受原則保護的檔案，且該檔案包含動態浮水印和列印權限，則浮水印將顯示在輸出中。

檔案 Document Security Extension 不支援豐富的浮水印功能，例如 PDF 式浮水印、浮水印中的多個元素、文字格式選項和頁面範圍。

您可以使用 Document Security 網頁建立動態浮水印。若要更多了解如何在受原則保護文件中建立並納人動態浮水印，請參閱 [Document Security 用戶說明](http://www.adobe.com/go/learn_lc_euRightsMgmt_11)。

Microsoft Office 適用的 Document Security Extension 可提供這些浮水印功能的支援：

<table>
 <thead>
  <tr>
   <th><p>Document Security 浮水印選項</p></th>
   <th><p>Word、Excel 和 PowerPoint 支援</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>原則名稱</p></td>
   <td><p>支援。</p></td>
  </tr>
  <tr>
   <td><p>浮水印名稱</p></td>
   <td><p>支援。</p></td>
  </tr>
  <tr>
   <td><p>使用為背景</p></td>
   <td><p>無論是否選取「用作背景」，動態浮水印的顯示行為均相同。</p><p>若是 Word 2010 和 2013，動態浮水印僅會顯示在「列印版面」和「預覽列印」視圖中。 </p><p>若是 Excel 2010 和 2013，同樣地，動態浮水印僅會顯示在「列印版面」和「頁面版面」視圖中。</p></td>
  </tr>
  <tr>
   <td><p>垂直定位</p></td>
   <td><p>支援</p></td>
  </tr>
  <tr>
   <td><p>水平定位</p></td>
   <td><p>支援</p><p>若是 Excel 2010 和 2013，使用點的浮水印水平定位不能使用。</p></td>
  </tr>
  <tr>
   <td><p>縮放</p></td>
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

### 開啟 Document Security 註冊網頁 {#opening-the-document-security-web-pages}

您可以開啟 Document Security 網頁來建立和更新用戶原則，並可檢視受原則保護檔案的狀態和審核資訊。
您也可以使用 Document Security 網頁，變更原則或撤銷受原則保護檔案的存取權。

若要開啟 Document Security 網頁，在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**建立和管理原則**」。如果您尚未提供登入資訊，瀏覽器會開啟伺服器登入頁面。

### 變更原則 {#changing-policies}

如果您擁有權限 (通常是 Document Security 管理員或檔案發佈者的權限)，您可稍後在檔案中套用不同原則或變更目前已套用原則的設定。

若要變更原則的設定，請使用 Document Security 網頁。

1. 請執行下列動作：

   * 在 Microsoft Office 2010 或 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**安全性 > 變更安全性**」。

1. 從清單中選取一項原則，並按一下「**套用**」。

### 撤銷檔案存取權限 {#revoking-file-access-privileges}

您可以撤銷開啟受保護檔案的功能。當您撤銷檔案的存取權限時，還可以指定向任何試圖開啟該檔案者顯示的訊息；同時，如果要以修訂版本取代該檔案，還可以指定該檔案更新版的 URL。

1. 請執行下列動作：

   * 在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤下，選取「**撤銷**」。

   Document Security 網頁會開啟至撤銷文件頁面。

1. 指定要顯示的訊息，並指定更新版的 URL (若有)，然後按一下「**確定**」。

若要了解撤銷檔案存取權限的更多資訊，請參閱 [Document Security 用戶說明](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/)。

存取權限可透過 Document Security 網頁恢復。

### 檢視檔案審核歷史記錄 {#viewing-the-file-audit-history}

Document Security 可以儲存受原則保護檔案的審核歷史記錄，這樣您便能審核用戶執行您檔案的操作。

Word、Excel 和 PowerPoint 檔案的已審核活動包含以下這些：

**保護新文件** 套用在檔案中的原則

**檢視文件** 檔案已開啟

**關閉文件** 檔案已關閉

**撤銷文件** 已移除檔案的存取權限

**解除撤銷文件** 歸還給檔案的存取權限

**修訂文件** 變更並儲存在本機的檔案

**列印高解析度** 列印的檔案

**變更安全性處理常式** 從檔案移除的原則保護

**切換文件原則** 從文件安全網頁應用在檔案的新原則

### 檢視檔案的審核歷史記錄 {#view-the-audit-history-for-a-file}

在 Microsoft Office 2010 和 Office 2013 適用的 Document Security Extension 中，在「**Document Security**」標籤上，選取「**審核歷史記錄**」。

Document Security 網頁會開啟至活動頁面，並顯示目前檔案的已審核活動。

### Microsoft Office 受限制功能 {#microsoft-office-restricted-features}

為了保護您的智慧財產，當受原則保護的檔案開啟時，有些 Microsoft Office 功能不適用。不適用功能清單取決於目前用戶獲得的權限。有些功能僅不適用於受保護的檔案；而當您在受保護工作階段時，其他功能則不適用所有檔案。通常，從您開啟受原則保護的檔案起，您都是在受保護工作階段中，直到您關閉應用程式或工作階段到期為止。

大多數原則會授予完整權限給發佈者。其他用戶可能會注意到其他功能限制。

如果命令不適用，則選單中命令名稱和相關的工具欄按鈕會呈現灰色。

>[!NOTE]
>
>若套用原則的檔案中含有前往嵌入式檔案的連結時，該原則不會套用在所連結的檔案中。Microsoft Office 適用的 Document Security 功能不會將保護延伸至所連結的檔案。


* 受原則保護的 Word、Excel 和 PowerPoint 檔案會被封鎖，而無法在 Internet Explorer 瀏覽器視窗中開啟。
* 如果用戶只獲得「變更」權限，他們法使用 Windows 剪貼簿將內容複製至其他應用程式的檔案。用戶可以啟用 Microsoft Office 剪貼簿選項，然後將內容複製到檔案中。
* 在 Microsoft Office 開啟受原則保護的檔案時，列印螢幕鍵會變為無法使用，直到您關閉應用程式或工作階段到期為止。
* Microsoft Office 適用的 Document Security 功能不支援 Web 架構的分散式撰寫和版本設定 (WebDAV)。在大多數情况下，您無法從 WebDAV 檔案夾開啟受原則保護的檔案。如果您可以開啟受原則保護的檔案，您沒有儲存、列印、變更或複製該檔案的權限。

適用於受原則保護檔案的一般安全性包括以下限制：

在受保護的工作階段中，Word、Excel 和 PowerPoint 許多常見功能可能會受到限制。

如果不允許用戶變更的受原則保護檔案已打開，則以任何方式變更檔案的命令均無法使用。只有開啟或建立新文件以及變更應用程式偏好設定的命令可使用。

#### Word 2010 和 Word 2013 限制 {#word-2010-and-word-2013-restrictions}

在 Word 開啟受原則保護的檔案時，儲存自動檔案修復的資訊會變為無法使用，直到您關閉和重新啟動 Word 為止。此外，下列功能在所述情况下會受到限制：

**檔案 > 新增 > 從現有新增** 可使用，但是在任何受原則保護的檔案打開時使用此命令建立的檔案無法儲存。無法將新檔案中的內容複製到其他檔案。

**檔案 > 儲存** 受到變更權限的限制。

**檔案 > 另存新檔** 所有選限受到變更權限的限制。

**檔案 > 列印** 所有選限受到列印權限的限制。除非原則允許高解析度列印，否則無法使用。

**檔案 > 儲存並傳送&#x200B;&#x200B;** 在受保護工作階段中，所有選項都無法使用。

**檔案 > 資訊 > 保護文件 > 以密碼
加密、新增數位簽名、標示為完稿、依人員限制
權限** 在受保護工作階段中無法使用。

**檔案 > 工作流程&#x200B;&#x200B;** 在受保護工作階段中無法使用。

***注意&#x200B;**：只有在 Office Professional Plus 2010、Office Enterprise 2010 和 Office Ultimate 2010 套件，以及這些程式的獨立 2010 Office 版本中，2010 Microsoft Office 系統版的 Word、Excel 和 PowerPoint 的啟動工作流程才可使用。*

**部落文章 > 發佈** 在受保護工作階段中無法使用。

**檔案 > 伺服器 > 檔案伺服器工作功能表&#x200B;&#x200B;** 在受保護工作階段中無法使用。

**首頁 > 剪貼簿 > 複製** 受到複製權限的限制。如果不允許複製，則無法將複製的內容貼至任何其他檔案中或 Office 剪貼簿中。
如果用戶擁有變更權限，則可以在受保護檔案中複製內容。

**首頁 > 剪貼簿 > 貼上** 受到變更權限的限制。

**首頁 > 剪貼簿 > 選擇性貼上** 受到變更權限的限制。

**插入 > 文字 > 物件** 在受保護工作階段中無法使用。任何時候都不能插入受原則保護的檔案。

**郵件&#x200B;&#x200B;** 在受保護工作階段中，此標籤的多數選項都無法使用。

**檢閱 > 校樣 > 搜尋** 受到複製權限的限制。如果不允許複製，則無法使用。

**檢視 > 校樣 > 搜尋** 受到複製權限的限制。如果不允許複製，則無法使用。

**檢閱 > 語言 > 翻譯 > 翻譯
文件** 已啟用並有複製權限。


**檢閱 > 語言 > 翻譯 > 翻譯
選取的文字** 已啟用並有複製權限。

**檢閱 > 語言 > 翻譯 > 迷你翻譯工具** 已啟用並有複製權限。


**檢閱 > 比較 > 比較** 在受保護工作階段中無法使用。任何時候都不能比較受原則保護的檔案。

**檢閱 > 保護 > 封鎖作者** 在受保護工作階段中無法使用。

**檢閱 > 保護 > 限制編輯** 在受保護工作階段中無法使用。

**檢視 > 巨集** 有些巨集受到複製權限的限制，除非允許複製，否則無法使用。

**增益集** 在受保護工作階段中無法新增或移除。

**線上共同作業** 在受保護工作階段中無法使用。

**主控文件和子文件** 在主控文件中開啟子文件時，子文件會受主控文件原則的控制。
如果子文件單獨開啟，該文件則無法列印、複製或修改。

**重新摘要** 在受保護工作階段中無法使用。

**畫面 (和所有相關命令)&#x200B;** 在受保護工作階段中，所有選項都無法使用。

**文件面板** 在受保護工作階段中無法使用。

**開發商 > 文件範本** 在受保護工作階段中無法使用。要存取此命令，請選取「檔案 > 選項 > 自訂 > 開發人員標籤 > 範本 > 文件範本」。

**大綱 > 主控文件 > 建立子文件
插入子文件** 在受保護工作階段中無法使用。

#### Excel 2010 和 Excel 2013 限制 {#excel-2010-and-excel-2013-restrictions}

下列功能在所述情况下會受到限制：

**檔案 > 新增 > 從現有新增** 可使用，但是在受保護工作階時使用此命令建立的檔案無法儲存。無法將新檔案中的內容複製到其他檔案。

**檔案 > 儲存、另儲新檔** 受到變更權限的限制。

**檔案 > 另存新檔 > PDF** 在受保護工作階段中無法使用。

**檔案 > 列印** 受到列印權限的限制。除非原則允許高解析度列印，否則無法使用。

**檔案 > 資訊 > 受保護文件** 在受保護工作階段中無法使用。

**檔案 > 資訊 > 保護活頁簿** 在受保護工作階段中無法使用。

**檔案 > 儲存並傳送&#x200B;&#x200B;** 在受保護工作階段中無法使用。

**檔案 > 選項 > 增益集** 在受保護工作階段中無法新增或移除。

**檔案 > 工作流程&#x200B;&#x200B;** 在受保護工作階段中無法使用。

***注意&#x200B;**：只有在 Office Professional Plus 2010、Office Enterprise 2010 和 Office Ultimate 2010 套件，以及這些程式的獨立 2010 Office 版本中，2010 Microsoft Office 系統版的 Word、Excel 和 PowerPoint 的啟動工作流程才可使用。*

**檔案 > 伺服器 > 檔案伺服器工作功能表&#x200B;&#x200B;** 在受保護工作階段中無法使用。

**首頁 > 剪貼簿 > 複製** 受到複製權限的限制。如果不允許複製，則無法將複製的內容貼至任何其他檔案中或 Microsoft Office 剪貼簿中。如果用戶擁有變更權限，則可以在受保護檔案中複製內容。

**首頁 > 剪貼簿 > 貼上** 受到變更權限的限制。

**首頁 > 剪貼簿 > 選擇性貼上** 受到變更權限的限制。

**首頁 > 儲存格 > 格式 > 移動或複製工作表** 在受保護工作階段中無法使用。

**首頁 > 儲存格 > 插入 > 插入工作表** 在受保護工作階段中無法使用。

**首頁 > 儲存格 > 刪除 > 刪除工作表** 在受保護工作階段中無法使用。

**首頁 > 編輯 > 填滿 > 填滿工作表** 受到變更權限的限制。

**插入 > 表格 > 表格** 受到變更權限的限制。

**插入 > 表格 > PivotTable** 無法在建立精靈中選取受原則保護的檔案。

**插入 > 文字 > 物件** 在受保護工作階段中無法使用。任何時候都不能插入受原則保護的檔案。

**插入 > 文字 > 頁首及頁尾** 受到變更權限的限制。受原則保護的文件無法使用。

**Data > Get External Data** 無法匯入受原則保護檔案的資料。

**資料 > 大綱 > 小計** 受到變更權限的限制。

**資料 > 資料工具 > 資料驗證** 受到變更權限的限制。

**檢閱 > 校樣 > 搜尋** 受到複製權限的限制。

**檢視 > 校樣 > 搜尋** 受到複製權限的限制。

**檢視 > 語言 > 翻譯** 受到複製權限的限制。

**檢閱 > 變更 > 保護工作表** 在受保護工作階段中無法使用。

**檢閱 > 變更 > 保護活頁簿** 在受保護工作階段中無法使用。

**檢閱 > 變更 > 分享活頁簿** 在受保護工作階段中無法使用。

**檢閱 > 變更 > 保護和分享活頁簿** 在受保護工作階段中無法使用。

**檢閱 > 變更 > 允許使用者編輯範圍** 在受保護工作階段中無法使用。

**檢閱 > 變更 > 追蹤變更 > 醒目提示
Changes** 含有動態浮水印的受原則檔案無法使用。

**檢視 > 巨集** 受到變更權限的限制。

**檢視 > 儲存工作區** 命令不能使用。

**開發人員 > XML > 擴充套件** 有些巨集受到複製權限的限制除，除非允許複製，否則無法使用。

**公式 > 公式稽核 > 公式稽核** 受到變更權限的限制。除非允許複製，否則無法使用。

**線上共同作業** 在受保護工作階段中無法使用。

**儲存自動復原資訊&#x200B;&#x200B;** 在受保護工作階段中無法使用。

***注意&#x200B;**：如果您試圖變更受原則保護檔案中的儲存格，但您無權對該儲存格進行變更，Excel 將顯示一個錯誤的警告訊息，指示您必須使用「取消保護工作表」命令從該檔案中移除保護。使用「取消保護工作表」命令不會從檔案中移除原則保護。*

#### PowerPoint 2010 和 PowerPoint 2013 限制 {#powerpoint-2010-and-powerpoint-2013-restrictions}

下列功能在所述情况下會受到限制：

**檔案 > 新增 > 從現有新增** 可使用，但是在受保護工作階時使用此命令建立的檔案無法儲存。無法將新檔案中的內容複製到其他檔案。

**檔案 > 儲存** 受到變更權限的限制。

**檔案 > 另存新檔** 所有選限受到變更權限的限制。

**檔案 > 列印** 所有選限受到列印權限的限制。除非原則允許高解析度列印，否則無法使用。

**檔案 > 儲存並傳送&#x200B;&#x200B;** 在受保護工作階段中無法使用。

**檔案 > 資訊 > 保護簡報 > 以密碼
加密、新增數位簽名、標示為完稿、依人員限制
權限** 在受保護工作階段中無法使用。

**檔案 > PowerPoint 選項 > 儲存自動復原
資訊** 在受保護工作階段中無法使用。

**檔案 > 伺服器 > 檔案伺服器工作功能表&#x200B;&#x200B;** 在受保護工作階段中無法使用。

**首頁 > 剪貼簿 > 複製** 受到複製權限的限制。如果不准複製，則無法將複製的內容貼在文件內、任何其他檔案中或 Office 剪貼簿中。如果用戶擁有變更權限，則可以在受保護檔案中複製內容。

**首頁 > 剪貼簿 > 貼上** 受到變更權限的限制。如果不允許複製，則無法將複製的內容貼在文件內。

**首頁 > 剪貼簿 > 選擇性貼上** 受到變更權限的限制。

**首頁 > 幻燈片 > 新增幻燈片 > 從大綱插入幻燈片、
重複使用幻燈片** 在受保護工作階段中無法使用。

**插入 > 文字 > 物件** 在受保護工作階段中無法使用。任何時候都不能插入受原則保護的檔案。

**設計 > 背景 > 背景樣式，隱藏
背景圖形、格式背景** 含有動態浮水印的受原則檔案無法使用。

**幻燈片 > 設定 > 錄製幻燈片放映** 受到變更權限的限制。

**檢視 > 校樣 > 搜尋** 受到複製權限的限制。

**檢視 > 語言 > 翻譯** 受到複製權限的限制。

**檢閱 > 語言 > 翻譯 > 迷你翻譯工具** 已啟用並有複製權限。


**檢視 > 簡報檢視 > 幻燈片放映** 受到變更權限的限制。如果不允許變更，且檔案經過修改，即無法檢視幻燈片放映。

**檢視 > 巨集** 有些巨集受到複製權限的限制，除非允許複製，否則無法使用。

**增益集** 在受保護工作階段中無法新增或移除。

**線上共同作業** 在受保護工作階段中無法使用。

## 使用協力驗證服務提供者 {#use-third-party-authentication-providers}

您可以使用有 AEM Forms Document Security 的協力驗證服務提供者。這些驗證服務提供者會幫助您在受保護的文件上另增一個存取層。AEM Forms Document Security 可支援以下的延伸驗證工作流程：

* 使用預設的 AEM Forms URL 的延伸驗證
* 使用自訂 URL 的延伸驗證
* 透過在 JEE 伺服器 AEM Forms 設定的協力身分識別服務提供者，使用預設延伸驗證工作流程
* 透過設定在 JEE 伺服器 AEM Forms 的協力身分識別服務提供者，使用自訂延伸驗證工作流程
* 使用特訂頁面的延伸驗證，以列出 SAML 驗證

## 字彙表 {#glossary}

關於 JEE 術語的 LiveCycle 和 AEM Forms 資訊，請參閱 [字彙表](http://www.adobe.com/go/learn_aemforms_designer_65)。
