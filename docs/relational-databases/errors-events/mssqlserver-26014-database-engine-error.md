---
title: MSSQLSERVER_26014 | Microsoft Docs
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
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
caps.latest.revision: 10
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 001529a5c7202d93f0559c9eb53af31b8fcdca71
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver26014"></a>MSSQLSERVER_26014
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>詳細資料  
  
|||  
|-|-|  
|產品名稱|[SQL Server]|  
|事件識別碼|26014|  
|事件來源|MSSQLSERVER|  
|元件|SQLEngine|  
|符號名稱|SNI_SSL_USER_CERT_FAILURE|  
|訊息文字|無法載入使用者指定的憑證 [Cert Hash(sha1) "%hs"]。 伺服器將不會接受連接。 您應該確認已正確安裝憑證。 請參閱線上叢書中的＜設定憑證給 SSL 使用＞(Configuring Certificate for Use by SSL)。|  
  
## <a name="explanation"></a>說明  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 已嘗試載入在訊息中指定的憑證，但是作業失敗。 您必須先解決此問題，然後 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 才能使用這個憑證。  
  
造成此錯誤的可能原因包括：  
  
-   憑證可能已經移動或刪除。  
  
-   如果 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 所使用的登入已經變更，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 可能就沒有存取此憑證的權限。  
  
-   憑證可能已經過期。  
  
## <a name="user-action"></a>使用者動作  
請確定在訊息中指定的憑證存在系統上、可以存取，而且可供使用。  
  
