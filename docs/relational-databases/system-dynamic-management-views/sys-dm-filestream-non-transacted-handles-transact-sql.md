---
title: sys.dm_filestream_non_transacted_handles (TRANSACT-SQL) |Microsoft 文件
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: dmv's
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_filestream_non_transacted_handles_TSQL
- dm_filestream_non_transacted_handles
- dm_filestream_non_transacted_handles_TSQL
- sys.dm_filestream_non_transacted_handles
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_filestream_non_transacted_handles dynamic management view
ms.assetid: 507ec125-67dc-450a-9081-94cde5444a92
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: bb27d263081cac5975e8a68a1cf13004fb1d2759
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sysdmfilestreamnontransactedhandles-transact-sql"></a>sys.dm_filestream_non_transacted_handles (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  顯示與 FileTable 資料相關聯、目前開啟的非交易式檔案控制代碼。  
  
 此檢視中針對每個開啟的檔案控制代碼包含一個資料列。 由於此檢視的資料對應到伺服器的即時內部狀態，因此隨著控制代碼開啟和關閉，資料會時常更新。 此檢視不包含歷程記錄資訊。  
  
 如需詳細資訊，請參閱 [管理作業步驟](../../relational-databases/blob/manage-filetables.md)。  
  
|**[資料行]**|**型別**|**說明**|  
|----------------|--------------|---------------------|  
|database_id|int|與控制代碼相關聯的資料庫識別碼。|  
|object_id|int|控制代碼之相關 FileTable 的物件識別碼。|  
|handle_id|int|唯一的控制代碼內容識別碼。 使用[sp_kill_filestream_non_transacted_handles &#40;TRANSACT-SQL&#41; ](../../relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles.md)預存程序來終止特定控制代碼。|  
|file_object_type|int|控制代碼的類型。 這表示控制代碼開啟時所針對的階層層級，即資料庫或項目。|  
|file_object_type_desc|nvarchar(120)|"UNDEFINED"、<br />"SERVER_ROOT"、<br />"DATABASE_ROOT"、<br />"TABLE_ROOT"、<br />"TABLE_ITEM"|  
|correlation_process_id|varbinary(8)|包含引發要求之處理序的唯一識別碼。|  
|correlation_thread_id|varbinary(8)|包含引發要求之執行緒的唯一識別碼。|  
|file_context|varbinary(8)|這個控制代碼所用之檔案物件的指標。|  
|state|int|控制代碼的目前狀態。 可能是作用中、已關閉或已終止。|  
|state_desc|nvarchar(120)|"ACTIVE"、<br />"CLOSED"、<br />"KILLED"|  
|current_workitem_type|int|目前所處理之控制代碼的狀態。|  
|current_workitem_type_desc|nvarchar(120)|"NoSetWorkItemType"、<br />"FFtPreCreateWorkitem"、<br />"FFtGetPhysicalFileNameWorkitem"、<br />"FFtPostCreateWorkitem"、<br />"FFtPreCleanupWorkitem"、<br />"FFtPostCleanupWorkitem"、<br />"FFtPreCloseWorkitem"、<br />"FFtQueryDirectoryWorkItem"、<br />"FFtQueryInfoWorkItem"、<br />"FFtQueryVolumeInfoWorkItem"、<br />"FFtSetInfoWorkitem"、<br />"FFtWriteCompletionWorkitem"|  
|fcb_id|bigint|FileTable 檔案控制區塊識別碼。|  
|item_id|varbinary(892)|檔案或目錄的項目識別碼。 如果是伺服器根控制代碼，可能是 null。|  
|is_directory|bit|這是目錄。|  
|item_name|nvarchar(512)|項目的名稱。|  
|opened_file_name|nvarchar(512)|原始要求開啟的路徑。|  
|database_directory_name|nvarchar(512)|代表資料庫目錄名稱的 opened_file_name 部分。|  
|table_directory_name|nvarchar(512)|代表資料表目錄名稱的 opened_file_name 部分。|  
|remaining_file_name|nvarchar(512)|代表剩餘目錄名稱的 opened_file_name 部分。|  
|open_time|datetime|開啟控制代碼的時間。|  
|flags|int|ShareFlagsUpdatedToFcb = 0x1、<br />DeleteOnClose = 0x2、<br />NewFile = 0x4、<br />PostCreateDoneForNewFile = 0x8、<br />StreamFileOverwritten = 0x10、<br />RequestCancelled = 0x20、<br />NewFileCreationRolledBack = 0x40|  
|login_id|int|開啟控制代碼的主體識別碼。|  
|login_name|nvarchar(512)|開啟控制代碼的主體名稱。|  
|login_sid|varbinary(85)|開啟控制代碼的主體 SID。|  
|read_access|bit|開啟以便讀取。|  
|write_access|bit|開啟以便寫入。|  
|delete_access|bit|開啟以便刪除。|  
|share_read|bit|在允許 share_read 的情況下開啟。|  
|share_write|bit|在允許 share_write 的情況下開啟。|  
|share_delete|bit|在允許 share_delete 的情況下開啟。|  
  
## <a name="see-also"></a>另請參閱  
 [管理 FileTable](../../relational-databases/blob/manage-filetables.md)  
  
  
