---
title: "暫停追蹤 (SQL Server Profiler) |Microsoft 文件"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: sql-server-profiler
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
caps.latest.revision: "24"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: cbf301c5d846a42e1aed2571b60c0b88f638631b
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2018
---
# <a name="pause-a-trace-sql-server-profiler"></a>暫停追蹤 (SQL Server Profiler)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]暫停追蹤可避免進一步事件資料被擷取，直到追蹤重新啟動。  
  
 暫停追蹤可防止事件資料被擷取，直到重新啟動追蹤為止。 重新啟動追蹤可讓追蹤作業繼續進行。 重新啟動之後，先前擷取的資料並不會遺失。 當追蹤重新啟動時，資料的擷取動作會從該暫停點繼續進行。 當追蹤暫停時，您可以變更名稱、事件、資料行及篩選條件。 但是，您無法變更傳送追蹤資料的目的地，也不能變更伺服器連接。  
  
### <a name="to-pause-a-trace"></a>若要暫停追蹤  
  
1.  選取包含執行中追蹤的視窗。  
  
2.  在 **[檔案]** 功能表上，按一下 **[暫停追蹤]**。  
  
## <a name="see-also"></a>另請參閱  
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
