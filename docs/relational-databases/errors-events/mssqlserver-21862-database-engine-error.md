---
title: MSSQLSERVER_21862 | Microsoft Docs
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
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
caps.latest.revision: 11
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: da8f05258d621f744c5d32f676f59fe24112966d
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver21862"></a>MSSQLSERVER_21862
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>詳細資料  
  
|||  
|-|-|  
|產品名稱|MSSQLSERVER|  
|事件識別碼|21862|  
|事件來源|MSSQLSERVER|  
|元件|SQLEngine|  
|符號名稱|SQLErrorNum21862|  
|訊息文字|在使用 'database snapshot' 或 'database snapshot character' 同步處理方法的發行集內，無法發行檔案資料流資料行。|  
  
## <a name="explanation"></a>說明  
由於無法透過資料庫快照集來存取 FILESTREAM 資料，因此當針對發行集的同步處理方法指定了 *database snapshot* 或 *database_snapshot_character* 參數時，快照集代理程式將無法讀取 FILESTREAM 資料。  
  
## <a name="user-action"></a>使用者動作  
將發行集同步處理方法變更為 *database snapshot* 或 *database_snapshot_character* 以外的項目，或是從發行集中排除 FILESTREAM 資料行。  
  
