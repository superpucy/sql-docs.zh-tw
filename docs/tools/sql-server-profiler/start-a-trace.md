---
title: "啟動追蹤 |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
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
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
caps.latest.revision: "24"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ef0d4c1015fa70145f8539a4dd10f4f8f6ffc35b
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2018
---
# <a name="start-a-trace"></a>啟動追蹤
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]在定義新追蹤或建立範本，並使用之後[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]，您可以啟動、 暫停或停止擷取資料，即可使用新的追蹤定義或範本。  
  
## <a name="starting-a-trace"></a>啟動追蹤  
 當您啟動追蹤，而且所定義的來源是 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 或 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]的執行個體時， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 便會建立一個佇列，以提供暫存空間來放置所擷取的伺服器事件。  
  
 當您使用 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 來存取 SQL 追蹤時，啟動追蹤時就會開啟新的追蹤視窗 (如果尚未開啟)，並立即擷取資料。  
  
 當您使用 [!INCLUDE[tsql](../../includes/tsql-md.md)] 系統預存程序來存取 SQL 追蹤時，您必須在每次啟動 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體時啟動追蹤，以便擷取資料。 啟動追蹤後，您只能修改追蹤的名稱。  
  
> [!NOTE]  
>  使用現有的追蹤時，您可以檢視屬性，但是不能修改屬性。 若要修改屬性，請停止或暫停追蹤。  
  
## <a name="see-also"></a>另請參閱  
 [連接到伺服器 &#40; 之後，自動啟動追蹤SQL Server Profiler &#41;](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)   
 [暫停追蹤 &#40;SQL Server Profiler &#41;](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)   
 [停止追蹤 &#40;SQL Server Profiler &#41;](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)   
 [清除追蹤視窗 &#40;SQL Server Profiler &#41;](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)   
 [在追蹤暫停或停止之後執行追蹤 &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
