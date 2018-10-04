---
title: 什麼是 Azure Data Studio？ | Microsoft Docs
description: Azure Data Studio 是免費、 輕量級工具，可用於管理 SQL Server、 Azure SQL Database 和 Azure SQL 資料倉儲; 在 Windows、 macOS 和 Linux 上執行只要它們正在執行。
ms.custom: tools|sos
ms.date: 09/24/2018
ms.prod: sql
ms.reviewer: alayu; sstein
ms.prod_service: sql-tools
ms.topic: overview
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 93e1eae9c920a06f24d19a3f2757a7afaa7ca968
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2018
ms.locfileid: "48038051"
---
# <a name="what-is-includename-sosincludesname-sosmd"></a>什麼是[!INCLUDE[name-sos](../includes/name-sos.md)]？

Azure Data Studio 是跨平台資料庫工具，供資料專業人員使用 Microsoft 家族的內部部署和雲端資料平台，在 Windows、 MacOS 和 Linux 上的。

先前的預覽名稱 SQL Operations Studio 發行，Azure Data Studio 提供 Intellisense、 程式碼片段、 原始檔控制整合和整合式終端機使用現代的編輯器體驗。 它是設計成可與資料平台使用者記住，與內建的查詢結果集和可自訂的儀表板的圖表。

**[下載並安裝 [!INCLUDE[name-sos](../includes/name-sos-short.md)]](download.md)**


## <a name="transact-sql-t-sql-code-editor-with-intellisense"></a>具有 IntelliSense 的 TRANSACT-SQL (T-SQL) 程式碼編輯器

[!INCLUDE[name-sos](../includes/name-sos-short.md)] 提供現代、 以鍵盤為主 T-SQL 程式碼撰寫體驗，可讓您日常的工作更容易利用內建功能，例如多個索引標籤式視窗、 豐富的 T-SQL 編輯器、 IntelliSense、 關鍵字完成、 程式碼片段、 程式碼巡覽、 和原始檔控制整合 (Git)。 執行隨 T-SQL 查詢、 檢視以及將結果儲存為文字、 JSON 或 Excel。 編輯資料、 組織您最愛的資料庫的連接，並瀏覽熟悉的物件瀏覽體驗中的資料庫物件。 若要了解如何使用 T-SQL 編輯器，請參閱[使用 T-SQL 編輯器來建立資料庫物件](tutorial-sql-editor.md)。

## <a name="smart-t-sql-code-snippets"></a>智慧型的 T-SQL 程式碼片段

T-SQL 程式碼片段會產生適當的 T-SQL 語法來建立資料庫、 資料表、 檢視、 預存程序、 使用者、 登入、 角色等等，並更新現有的資料庫物件。 使用智慧程式碼片段快速建立資料庫副本以進行開發或測試，並生成和執行 CREATE 和 INSERT 指令。

[!INCLUDE[name-sos](../includes/name-sos-short.md)] 也提供建立自訂的 T-SQL 程式碼片段功能。 若要進一步了解，請參閱[建立和使用程式碼片段](code-snippets.md)。


## <a name="customizable-server-and-database-dashboards"></a>可自訂的伺服器和資料庫儀表板

建立豐富可自訂的儀表板來監視，並快速移難排解在您的資料庫中的效能瓶頸。 若要深入了解 insight widget 和資料庫 （和伺服器）的儀表板，請參閱[透過 insight widget 管理伺服器和資料庫](insight-widgets.md)。

## <a name="connection-management-server-groups"></a>連接管理（伺服器群組）

伺服器群組提供一種方式組織的伺服器和您使用的資料庫的連接資訊。 如需詳細資訊，請參閱 <<c0> [ 伺服器群組](server-groups.md)。

## <a name="integrated-terminal"></a>整合式終端機

在 [!INCLUDE[name-sos](../includes/name-sos-short.md)] 使用者介面的整合式終端機視窗中，使用您喜歡的命令列工具 (例如：Bash, PowerShell, sqlcmd, bcp和 ssh)。 若要深入了解整合式終端機，請參閱[整合式驗證終端機] (整合 terminal.md)。

## <a name="extensibility-and-extension-authoring"></a>擴充性和擴充功能撰寫

增強[!INCLUDE[name-sos](../includes/name-sos-short.md)]擴充功能的基底的安裝體驗。 [!INCLUDE[name-sos](../includes/name-sos-short.md)] 資料管理活動，以及支援擴充功能撰寫提供擴充點。

若要了解中的擴充性[!INCLUDE[name-sos](../includes/name-sos-short.md)]，請參閱 <c2> [擴充性](extensibility.md)。
若要深入了解撰寫延伸模組，請參閱[延伸模組製作](extension-authoring.md)。




## <a name="next-steps"></a>後續步驟
- [下載並安裝 [!INCLUDE[name-sos](../includes/name-sos-short.md)]](download.md)
- [連線及查詢 SQL Server](quickstart-sql-server.md)
- [連線及查詢 Azure SQL Database](quickstart-sql-database.md)
