---
title: sp_help (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 10/24/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_help
- sp_help_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help
ms.assetid: 913cd5d4-39a3-4a4b-a926-75ed32878884
caps.latest.revision: 60
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: be83dee5f8f4fa4f9e5893bc71964dd3a8df4e3c
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sphelp-transact-sql"></a>sp_help (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  報告的資料庫物件的相關資訊 (中列出的任何物件**sys.sysobjects**相容性檢視)，為使用者定義資料類型或資料類型。  
  
 
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
  
sp_help [ [ @objname = ] 'name' ]  
```  
  
## <a name="arguments"></a>引數  
 [ **@objname=**] **'***name***'**  
 處於之任何物件名稱**sysobjects**或任何使用者定義資料類型中**systypes**資料表。 *名稱*是**nvarchar (**776**)**，預設值是 NULL。 不接受資料庫名稱。  兩個或三個部分的名稱必須加以分隔，例如 'Person.AddressType' 或 [Person.AddressType]。   
   
  
## <a name="return-code-values"></a>傳回碼值  
 0 (成功) 或 1 (失敗)  
  
## <a name="result-sets"></a>結果集  
 傳回的結果集取決於是否*名稱*已指定，它指定時，而且它是什麼資料庫物件。  
  
1.  如果**sp_help**執行不使用引數，會傳回存在目前資料庫中的所有類型的物件的摘要資訊。  
  
    |資料行名稱|資料類型|Description|  
    |-----------------|---------------|-----------------|  
    |**名稱**|**nvarchar(**128**)**|物件名稱|  
    |**擁有者**|**nvarchar(**128**)**|物件擁有者 (這是擁有物件的資料庫主體， 預設為包含物件之結構描述的擁有者)。|  
    |**object_type**|**nvarchar (**31**)**|物件類型|  
  
2.  如果*名稱*是[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]資料型別或使用者定義資料類型， **sp_help**傳回下列結果集。  
  
    |資料行名稱|資料類型|Description|  
    |-----------------|---------------|-----------------|  
    |**type_name**|**nvarchar(**128**)**|資料類型名稱。|  
    |**Storage_type**|**nvarchar(**128**)**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 類型名稱。|  
    |**長度**|**smallint**|資料類型的實際長度 (以位元組為單位)。|  
    |**Prec**|**int**|有效位數 (總位數)。|  
    |**小數位數**|**int**|小數點右側的位數。|  
    |**可為 Null**|**varchar (**35**)**|指出是否允許 NULL 值：[是] 或 [否]。|  
    |**default_name**|**nvarchar(**128**)**|與這個類型繫結的預設值名稱。<br /><br /> NULL = 未繫結預設值。|  
    |**rule_name**|**nvarchar(**128**)**|與這個類型繫結的規則名稱。<br /><br /> NULL = 未繫結預設值。|  
    |**定序**|**sysname**|資料類型的定序。 非字元資料類型是 NULL。|  
  
3.  如果*名稱*是資料類型以外的任何資料庫物件**sp_help**傳回這個結果設定，也有其他結果集，根據指定的物件類型。  
  
    |資料行名稱|資料類型|Description|  
    |-----------------|---------------|-----------------|  
    |**名稱**|**nvarchar(**128**)**|資料表名稱|  
    |**擁有者**|**nvarchar(**128**)**|資料表擁有者|  
    |**型別**|**nvarchar (**31**)**|資料表類型|  
    |**Created_datetime**|**datetime**|資料表的建立日期|  
  
     根據指定的資料庫物件**sp_help**傳回其他結果集。  
  
     如果*名稱*是系統資料表、 使用者資料表或檢視， **sp_help**傳回下列結果集。 不過，不會傳回描述資料檔在檔案群組中之位置的結果集。  
  
    -   在資料行物件上傳回的其他結果集：  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**column_name**|**nvarchar(**128**)**|資料行名稱。|  
        |**型別**|**nvarchar(**128**)**|資料行資料類型。|  
        |**計算**|**varchar (**35**)**|指出是否計算資料行中的值：[是] 或 [否]。|  
        |**長度**|**int**|資料行長度 (以位元組為單位)。<br /><br /> 注意： 如果資料行資料類型是大數值類型 (**varchar （max)**， **nvarchar （max)**， **varbinary （max)**，或**xml**)，將值顯示為-1。|  
        |**Prec**|**char (**5**)**|資料行有效位數。|  
        |**小數位數**|**char (**5**)**|資料行小數位數。|  
        |**可為 Null**|**varchar (**35**)**|指出資料行是否允許 NULL 值：[是] 或 [否]。|  
        |**TrimTrailingBlanks**|**varchar (**35**)**|修剪尾端空白。 傳回 [是] 或 [否]。|  
        |**FixedLenNullInSource**|**varchar (**35**)**|只是為了與舊版相容。|  
        |**定序**|**sysname**|資料行的定序。 非字元資料類型是 NULL。|  
  
    -   在識別欄位上傳回的其他結果集：  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**識別**|**nvarchar(**128**)**|資料類型宣告為識別的資料行名稱。|  
        |**種子**|**numeric**|識別欄位的起始值。|  
        |**[遞增]**|**numeric**|這個資料行的值所用的遞增。|  
        |**不可複寫**|**int**|識別屬性不會強制執行時複寫登入，例如**sqlrepl**，將資料插入資料表：<br /><br /> 1 = True<br /><br /> 0 = False|  
  
    -   在資料行上傳回的其他結果集：  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**RowGuidCol**|**sysname**|全域唯一識別碼資料行的名稱。|  
  
    -   在檔案群組上傳回的其他結果集：  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**Data_located_on_filegroup**|**nvarchar(**128**)**|資料所在的檔案群組：「主要」、「次要」或「交易記錄」。|  
  
    -   在索引上傳回的其他結果集：  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**index_name**|**sysname**|索引名稱。|  
        |**index_description**|**varchar (**210**)**|索引的描述。|  
        |**index_keys**|**nvarchar (**2078年**)**|建立索引的資料行名稱。 如果是 xVelocity 記憶體最佳化的資料行存放區索引，則傳回 NULL。|  
  
    -   在條件約束上傳回的其他結果集：  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**其中**|**nvarchar (**146**)**|條件約束的類型。|  
        |**constraint_name**|**nvarchar(**128**)**|條件約束的名稱。|  
        |**delete_action**|**nvarchar (**9**)**|指出 DELETE 動作是：NO_ACTION、CASCADE、SET_NULL、SET_DEFAULT 或 N/A。<br /><br /> 只適用於 FOREIGN KEY 條件約束。|  
        |**update_action**|**nvarchar (**9**)**|指出 UPDATE 動作是：NO_ACTION、CASCADE、SET_NULL、SET_DEFAULT 或 N/A。<br /><br /> 只適用於 FOREIGN KEY 條件約束。|  
        |**status_enabled**|**varchar (**8**)**|指出是否啟用條件約束：已啟用、已停用或 N/A。<br /><br /> 只適用於 CHECK 和 FOREIGN KEY 條件約束。|  
        |**status_for_replication**|**varchar (**19**)**|指出條件約束是否針對複寫。<br /><br /> 只適用於 CHECK 和 FOREIGN KEY 條件約束。|  
        |**constraint_keys**|**nvarchar (**2078年**)**|組成條件約束的資料行名稱，如果是預設值和規則，便是定義預設值或規則的文字。|  
  
    -   在進行參考的物件上傳回的其他結果集：  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**資料表的參考者**|**nvarchar (**516**)**|識別參考資料表的其他資料庫物件。|  
  
    -   在預存程序、函數或擴充預存程序上傳回的其他結果集。  
  
        |資料行名稱|資料類型|Description|  
        |-----------------|---------------|-----------------|  
        |**parameter_name**|**nvarchar(**128**)**|預存程序參數名稱。|  
        |**型別**|**nvarchar(**128**)**|預存程序參數的資料類型。|  
        |**長度**|**smallint**|最大的實體儲存體長度 (以位元組為單位)。|  
        |**Prec**|**int**|有效位數或總位數。|  
        |**小數位數**|**int**|小數點右側的位數。|  
        |**Param_order**|**smallint**|參數的順序。|  
  
## <a name="remarks"></a>備註  
 **Sp_help**程序會尋找只會在目前資料庫中的物件。  
  
 當*名稱*未指定， **sp_help**列出的物件名稱、 擁有者，以及針對目前資料庫中的所有物件的物件類型。 **sp_helptrigger**提供觸發程序的相關資訊。  
  
 **sp_help**公開只可排序的索引資料行; 因此，不會公開 XML 索引或空間索引的相關資訊。  
  
## <a name="permissions"></a>Permissions  
 需要 **public** 角色中的成員資格。 使用者必須具有至少一個權限*objname*。 若要檢視資料行條件約束索引鍵、預設值或規則，您必須具有此資料表的 VIEW DEFINITION 權限。  
  
## <a name="examples"></a>範例  
  
### <a name="a-returning-information-about-all-objects"></a>A. 傳回所有物件的相關資訊  
 下列範例會列出 `master` 資料庫中每個物件的相關資訊。  
  
```  
USE master;  
GO  
EXEC sp_help;  
GO  
```  
  
### <a name="b-returning-information-about-a-single-object"></a>B. 傳回單一物件的相關資訊  
 下列範例會顯示 `Person` 資料表的相關資訊。  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sp_help 'Person.Person';  
GO  
```  
  
## <a name="see-also"></a>另請參閱  
 [Database Engine 預存程序&#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [sp_helpindex &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpindex-transact-sql.md)   
 [sp_helprotect &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helprotect-transact-sql.md)   
 [sp_helpserver & #40;TRANSACT-SQL & #41;](../../relational-databases/system-stored-procedures/sp-helpserver-transact-sql.md)   
 [sp_helptrigger &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helptrigger-transact-sql.md)   
 [sp_helpuser &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpuser-transact-sql.md)   
 [系統預存程序 &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [sys.sysobjects &#40;Transact SQL&#41;](../../relational-databases/system-compatibility-views/sys-sysobjects-transact-sql.md)  
  
  
