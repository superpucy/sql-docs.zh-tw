---
title: SQL Server 的 SQL Errors 物件 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: performance-monitor
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
caps.latest.revision: 14
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a843a34c21cf6567c6f55f233dc56febbb265d6e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sql-server-sql-errors-object"></a>SQL Server 的 SQL Errors 物件
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Microsoft **中的** SQLServer:SQL Errors [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 物件，提供用來監視 **SQL Errors**的計數器。  
  
 下表描述 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQL Errors** 計數器。  
  
|SQL Server SQL Errors 計數器|描述|  
|------------------------------------|-----------------|  
|**Errors/sec**|每秒的錯誤數目。|  
  
 物件中的每個計數器均包含下列執行個體：  
  
|項目|定義|  
|----------|----------------|  
|**_Total**|所有錯誤的相關資訊。|  
|**DB Offline Errors**|追蹤導致 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 讓目前資料庫離線的嚴重錯誤。|  
|**Info Errors**|針對僅提供資訊給使用者而不會導致錯誤的錯誤訊息，提供其相關資訊。|  
|**Kill Connection Errors**|追蹤導致 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 清除目前連接的嚴重錯誤。|  
|**User Errors**|使用者錯誤的相關資訊。|  
  
## <a name="see-also"></a>另請參閱  
 [監視資源使用狀況 &#40;系統監視器&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
