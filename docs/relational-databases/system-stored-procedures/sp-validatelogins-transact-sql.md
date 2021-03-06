---
title: sp_validatelogins (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_validatelogins
- sp_validatelogins_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_validatelogins
ms.assetid: 6ac52e21-e20d-469b-ad40-5aa091e06b61
caps.latest.revision: 25
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 99463e2d5e22acbdb69458f2119fc7410492621b
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="spvalidatelogins-transact-sql"></a>sp_validatelogins (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  報告有關 Windows 使用者和群組的資訊，這些使用者和群組對應至 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 主體，但不再存在於 Windows 環境中。  
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
  
sp_validatelogins  
```  
  
## <a name="return-code-values"></a>傳回碼值  
 0 (成功) 或 1 (失敗)  
  
## <a name="result-sets"></a>結果集  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**SID**|**varbinary(85)**|Windows 使用者或群組的 Windows 安全性識別碼 (SID)。|  
|**NT 登入**|**sysname**|Windows 使用者或群組的名稱。|  
  
## <a name="remarks"></a>備註  
 如果被遺棄的伺服器層級主體擁有資料庫使用者，必須先移除該資料庫使用者，才可以移除被遺棄的伺服器主體。 若要移除的資料庫使用者，請使用[DROP USER](../../t-sql/statements/drop-user-transact-sql.md)。 如果伺服器層級主體擁有資料庫中的安全性實體，則必須傳送這些安全性實體的擁有權或卸除這些安全性實體。 若要傳送的資料庫安全性實體的擁有權，請使用[ALTER AUTHORIZATION](../../t-sql/statements/alter-authorization-transact-sql.md)。  
  
 若要移除對應至 Windows 使用者和群組不再存在，請使用[DROP LOGIN](../../t-sql/statements/drop-login-transact-sql.md)。  
  
## <a name="permissions"></a>Permissions  
 需要的成員資格**sysadmin**或**securityadmin**固定的伺服器角色。  
  
## <a name="examples"></a>範例  
 下列範例會顯示 Windows 使用者和群組，這些 Windows 使用者和群組不再存在，但仍被授與對 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體的存取權。  
  
```  
EXEC sp_validatelogins;  
GO  
```  
  
## <a name="see-also"></a>另請參閱  
 [系統預存程序 &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [安全性預存程序 &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [卸除使用者 & #40;TRANSACT-SQL & #41;](../../t-sql/statements/drop-user-transact-sql.md)   
 [卸除登入 & #40;TRANSACT-SQL & #41;](../../t-sql/statements/drop-login-transact-sql.md)   
 [ALTER AUTHORIZATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-authorization-transact-sql.md)  
  
  
