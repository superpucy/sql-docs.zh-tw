---
title: SQL Server 的 ExecStatistics 物件 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
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
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
caps.latest.revision: 14
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 264706d5009f800809b02a35b53d98d42ef655f4
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sql-server-execstatistics-object"></a>SQL Server 的 ExecStatistics 物件
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Microsoft SQL Server 中的 **SQLServer:ExecStatistics** 物件提供計數器來監視各種執行情形。  
  
 下表描述 SQL Server **Exec Statistics** 計數器。  
  
|SQL Server Exec Statistics 計數器|描述|  
|-----------------------------------------|-----------------|  
|**Distributed Query**|執行分散式查詢的相關統計資料。|  
|**DTC calls**|執行 DTC 呼叫的相關統計資料。|  
|**Extended Procedures**|執行擴充程序的相關統計資料。|  
|**OLEDB calls**|執行 OLEDB 呼叫的相關統計資料。|  
  
 物件中的每個計數器均包含下列執行個體：  
  
|項目|描述|  
|----------|-----------------|  
|**平均執行時間 (ms)**|選取的執行類型之平均執行時間。|  
|**每秒累計執行時間 (ms)**|選取的執行類型之每秒彙總執行時間。|  
|**正在執行數目**|選取的執行類型之進行中執行數目。|  
|**每秒開始執行數目**|選取的執行類型之每秒開始的執行數目。|  
  
## <a name="see-also"></a>另請參閱  
 [監視資源使用狀況 &#40;系統監視器&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
