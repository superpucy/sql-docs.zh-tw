---
title: 'ConnectionEvents （Visual c + + 語法索引與 #import） |Microsoft 文件'
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
dev_langs:
- C++
helpviewer_keywords:
- 'ConnectionEvents collection [ADO], Visual C++ syntax index with #import'
ms.assetid: dd052d36-7730-4400-822b-0544fb1992b4
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a5d0b5e496fa224e2ab81a9d3aa0e0d78e85495a
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="connectionevents-visual-c-syntax-index-with-import"></a>ConnectionEvents （Visual c + + 語法索引與 #import）
## <a name="events"></a>事件  
  
```  
HRESULT InfoMessage( struct Error * pError, enum  
    EventStatusEnum *     adStatus, struct _Connection * pConnection );  
  
HRESULT BeginTransComplete( long TransactionLevel,  
    struct Error * pError, enum EventStatusEnum * adStatus, struct  
    _Connection * pConnection );  
  
HRESULT CommitTransComplete( struct Error *  
    pError, enum EventStatusEnum     * adStatus, struct _Connection *  
    pConnection );  
  
HRESULT RollbackTransComplete( struct Error *  
    pError, enum     EventStatusEnum * adStatus, struct _Connection *  
    pConnection );  
  
HRESULT WillExecute( BSTR * Source, enum  
    CursorTypeEnum * CursorType,  
    enum LockTypeEnum * LockType, long * Options, enum EventStatusEnum *  
    adStatus, struct _Command * pCommand, struct _Recordset * pRecordset,  
    struct _Connection * pConnection );  
  
HRESULT ExecuteComplete( long RecordsAffected, struct  
    Error * pError,     enum EventStatusEnum * adStatus, struct _Command  
    * pCommand, struct     _Recordset * pRecordset, struct _Connection *  
    pConnection );  
  
HRESULT WillConnect( BSTR * ConnectionString, BSTR *  
    UserID, BSTR *     Password, long * Options, enum EventStatusEnum *  
    adStatus, struct     _Connection * pConnection );  
  
HRESULT ConnectComplete( struct Error *  
    pError, enum EventStatusEnum *     adStatus, struct _Connection *  
    pConnection );  
  
HRESULT Disconnect( enum EventStatusEnum *  
    adStatus, struct _Connection *     pConnection );  
```
