---
title: MSSQLSERVER_5242 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: errors-events
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 5242 (Database Engine error)
ms.assetid: 712b1a10-2f87-41df-a111-1ed9f14102d4
caps.latest.revision: 15
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 33f827d0ded196005a8446be07caefa273141428
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver5242"></a>MSSQLSERVER_5242
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>詳細資料  
  
|||  
|-|-|  
|產品名稱|[SQL Server]|  
|事件識別碼|5242|  
|事件來源|MSSQLSERVER|  
|元件|SQLEngine|  
|符號名稱||  
|訊息文字|於資料庫 '%.*ls'(識別碼:%d) 的頁面 %S_PGID 上執行內部作業期間，偵測到不一致性。 請連絡技術支援部門。 參考編號 %ld。|  
  
## <a name="explanation"></a>說明  
錯誤訊息中參照的資料庫頁面上發生結構不一致的問題。  
  
## <a name="see-also"></a>另請參閱  
[DBCC CHECKDB &#40;Transact-SQL&#41;](~/t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)  
[資料庫檔案與檔案群組](~/relational-databases/databases/database-files-and-filegroups.md)  
  
