---
title: 顯示並儲存執行計畫 | Microsoft Docs
ms.custom: ''
ms.date: 08/21/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: performance
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
caps.latest.revision: 24
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 41975afdb44da50c2c2513a760b2f1879f816ba4
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="display-and-save-execution-plans"></a>顯示並儲存執行計畫
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  本節將說明如何顯示執行計畫，以及如何使用 Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]將執行計畫儲存到 XML 格式的檔案中。  
  
 執行計畫會以圖形化的方式，顯示 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 查詢最佳化工具所選擇的資料擷取方法。 執行計畫會使用圖示來呈現 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中特定陳述式與查詢的執行成本，而不是使用 [SET SHOWPLAN_ALL](../../t-sql/statements/set-showplan-all-transact-sql.md) 或 [SET SHOWPLAN_TEXT](../../t-sql/statements/set-showplan-text-transact-sql.md) 陳述式所產生的表格呈現方式。 這種圖形式的方法，對於了解查詢的效能特性非常有幫助。  

 雖然 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 查詢最佳化工具只會產生一個執行計畫，但仍有**估計**執行計畫和**實際**執行計畫的概念。
 -  [估計執行計畫](../../relational-databases/performance/display-the-estimated-execution-plan.md)傳回的執行計畫如同查詢最佳化工具在編譯時期產生的執行計畫。 產生估計執行計畫不會實際執行查詢或 Batch，因此不包含任何執行階段資訊，例如實際的資源使用計量或執行階段警告。 
 -  [實際執行計畫](../../relational-databases/performance/display-an-actual-execution-plan.md)傳回的執行計畫，如同查詢最佳化工具所產生、完成查詢或 Batch 執行之後的執行計畫。 這包括資源使用計量和任何執行階段警告的執行階段資訊。  

 如需詳細資訊，請參閱[查詢處理架構指南](../../relational-databases/query-processing-architecture-guide.md)。
  
## <a name="in-this-section"></a>本節內容  
  
-   [顯示估計的執行計畫](../../relational-databases/performance/display-the-estimated-execution-plan.md)  
  
-   [顯示實際執行計畫](../../relational-databases/performance/display-an-actual-execution-plan.md)  
  
-   [以 XML 格式儲存執行計畫](../../relational-databases/performance/save-an-execution-plan-in-xml-format.md)  
  
  
