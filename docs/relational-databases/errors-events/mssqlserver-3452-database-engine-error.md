---
title: MSSQLSERVER_3452 | Microsoft Docs
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
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
caps.latest.revision: 17
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: df4e5faa901c840ebc1f03c828cb377edfad79ee
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver3452"></a>MSSQLSERVER_3452
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>詳細資料  
  
|||  
|-|-|  
|產品名稱|[SQL Server]|  
|事件識別碼|3452|  
|事件來源|MSSQLSERVER|  
|元件|SQLEngine|  
|符號名稱|REC_CHECKIDENTITY|  
|訊息文字|資料庫 '%.*ls' (%d) 的復原偵測到資料表識別碼 %d 中的識別值可能不一致。 請執行 DBCC CHECKIDENT ('%.\*ls')。|  
  
## <a name="explanation"></a>說明  
升級至 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 時，復原資料庫中識別值的處理序在中繼資料中發現不一致的問題。  
  
## <a name="user-action"></a>使用者動作  
執行 DBCC CHECKIDENT。  
  
