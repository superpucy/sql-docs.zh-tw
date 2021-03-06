---
title: 連接至 Access 資料庫 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.service: ''
ms.component: connection-manager
ms.reviewer: ''
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Access [Integration Services]
- Access databases [Integration Services]
ms.assetid: 229fbd46-ef6a-4609-a4cc-d80d52c33cf1
caps.latest.revision: 18
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: d82334ca4c5b5efb1d956c8d3a8afe901fc94f83
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2018
---
# <a name="connect-to-an-access-database"></a>連接至 Access 資料庫
  若要將 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 封裝連接至 Microsoft Office Access 資料來源，您需要使用 OLE DB 連接管理員和資料提供者。 您所使用的資料提供者取決於建立資料來源的 Access 版本：  
  
-   若為 Access 2003 和更舊版本，封裝需要使用 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB 提供者。  
  
-   若為 Access 2007，封裝需要使用 Microsoft Office 12.0 Access 資料庫引擎的 OLE DB 提供者。  
  
 您可以從 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 設計師的 [連接管理員] 區域或 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 匯入和匯出精靈建立 OLE DB 連接管理員並選取對應的資料提供者。  
  
> [!NOTE]  
>  在 64 位元電腦上，您必須執行以 32 位元模式連接至 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Access 資料來源的封裝。 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB 提供者和 Microsoft Office 12.0 Access 資料庫引擎的 OLE DB 提供者都只有提供 32 位元版本。  

## <a name="connectivity-components-for-microsoft-excel-and-access-files"></a>Microsoft Excel 和 Access 檔案的連線元件
  
您可能必須下載 Microsoft Office 檔案的連線元件 (如果尚未安裝)。 在這裡下載 Access 和 Excel 檔案的連線元件最新版本：[Microsoft Access Database Engine 2016 可轉散發套件](https://www.microsoft.com/download/details.aspx?id=54920)。
  
最新版的元件可以開啟舊版 Access 所建立的檔案。

如果電腦有 32 位元版本的 Office，則必須安裝 32 位元版本的元件，而且您也必須確定以 32 位元模式執行套件。

如果您有 Office 365 訂用帳戶，請確定下載 Access Database Engine 2016 可轉散發套件，而非 Microsoft Access 2016 Runtime。 當您執行安裝程式時，可能會看到錯誤訊息，指出您無法使用 Office 隨選即用元件並存安裝下載。 若要略過此錯誤訊息，請開啟 [命令提示字元] 視窗並執行使用 `/quiet` 參數所下載的 .EXE 檔案，以無訊息模式執行安裝。 例如：

`C:\Users\<user name>\Downloads\AccessDatabaseEngine.exe /quiet`
  
## <a name="connecting-to-a-data-source-in-access-2003-or-earlier-format"></a>連接至採用 Access 2003 或舊版格式的資料來源  
  
### <a name="to-create-an-access-connection-manager-from-the-connection-managers-area"></a>從連接管理員區域建立 Access 連接管理員  
  
1.  在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中，開啟封裝。  
  
2.  在 [連線管理員] 區域中，以滑鼠右鍵按一下該區域中的任何位置，然後選取 [新增 OLE DB 連線]。  
  
3.  在 **[設定 OLE DB 連接管理員]** 對話方塊中，按一下 **[新增]**。  
  
     如需詳細資訊，請參閱 [OLE DB 連線管理員](../../integration-services/connection-manager/ole-db-connection-manager.md)。  
  
4.  在 **[連接管理員]** 對話方塊中，針對 **[提供者]** 選取 **[Microsoft Jet 4.0 OLE DB 提供者]**，然後依適當情況設定連接管理員。  
  
### <a name="to-create-an-access-connection-from-the-sql-server-import-and-export-wizard"></a>從 SQL Server 匯入和匯出精靈建立 Access 連接  
  
1.  在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中，啟動 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 匯入和匯出精靈。  
  
2.  在 **[選擇資料來源]** 頁面中，針對 **[資料來源]** 選取 **[Microsoft Access]**，然後設定 Access 連接。  
  
     當您選取 **[Microsoft Access]** 當做 **[資料來源]** 時，精靈就會自動使用正確的資料提供者來建立必要的 OLE DB 連接管理員。 如需詳細資訊，請參閱 [OLE DB 連線管理員](../../integration-services/connection-manager/ole-db-connection-manager.md)。  
  
## <a name="connecting-to-a-data-source-in-access-2007-format"></a>連接至採用 Access 2007 格式的資料來源  
 若要存取 Access 2007 資料來源，OLE DB 連接管理員需要使用 Microsoft Office 12.0 Access 資料庫引擎的 OLE DB 提供者。 2007 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office System 會自動安裝這個提供者。 如果 2007 Office System 沒有安裝在執行 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 的電腦上，您就必須個別安裝該提供者。 若要安裝 Microsoft Office 12.0 Access 資料庫引擎的 OLE DB 提供者，請下載並安裝這個網頁上的元件：＜ [2007 Office System 驅動程式：資料連線元件](http://go.microsoft.com/fwlink/?LinkId=98155)＞。  
  
### <a name="to-create-an-ole-db-connection-manager-from-the-connection-managers-area"></a>從連接管理員區域建立 OLE DB 連接管理員  
  
1.  在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中，開啟封裝。  
  
2.  在 [連線管理員] 區域中，以滑鼠右鍵按一下該區域中的任何位置，然後選取 [新增 OLE DB 連線]。  
  
3.  在 **[設定 OLE DB 連接管理員]** 對話方塊中，按一下 **[新增]**。  
  
     如需詳細資訊，請參閱 [OLE DB 連線管理員](../../integration-services/connection-manager/ole-db-connection-manager.md)。  
  
4.  在 **[連接管理員]** 對話方塊中，針對 **[提供者]** 選取 **[Microsoft Office 12.0 Access 資料庫引擎 OLE DB]**，然後依適當情況設定連接管理員。  
  
    > [!NOTE]  
    >  若要連接至使用 Access 2007 的資料來源，您無法選取 [Microsoft Jet 4.0 OLE DB 提供者] 當作 [資料來源]。  
  
### <a name="to-create-an-ole-db-connection-from-the-sql-server-import-and-export-wizard"></a>從 SQL Server 匯入和匯出精靈建立 OLE DB 連接  
  
1.  在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中，啟動 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 匯入和匯出精靈。  
  
2.  在 **[選擇資料來源]** 頁面中，針對 **[資料來源]** 選取 **[Microsoft Office 12.0 Access 資料庫引擎 OLE DB 提供者]**，然後依適當情況設定連接。  
  
    > [!NOTE]  
    >  若要連接至使用 Access 2007 的資料來源，您無法選取 [Microsoft Jet 4.0 OLE DB 提供者] 當作 [資料來源]。  
  
     當您選取 **[Microsoft Office 12.0 Access 資料庫引擎 OLE DB 提供者]** 當做 **[資料來源]** 時，精靈就會自動使用正確的資料提供者來建立必要的 OLE DB 連接管理員。 如需詳細資訊，請參閱 [OLE DB 連線管理員](../../integration-services/connection-manager/ole-db-connection-manager.md)。  
  
## <a name="see-also"></a>另請參閱  
 [連接至 Excel 活頁簿](../../integration-services/connection-manager/connect-to-an-excel-workbook.md)  
  
  
