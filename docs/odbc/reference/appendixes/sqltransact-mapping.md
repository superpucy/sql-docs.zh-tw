---
title: SQLTransact 對應 |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLTransact
- SQLTransact function [ODBC], mapping
ms.assetid: 8a01041f-3572-46f9-8213-b817f3cf929c
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e4742829b5df9d99007181109f68d020a2f4af98
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sqltransact-mapping"></a>SQLTransact 對應
**SQLTransact**現在取代**SQLEndTran**。 兩個函式之間的主要差異在於**SQLEndTran**包含引數*HandleType*，以指定要完成工作的範圍。 *HandleType*引數可以指定的環境或連接控制代碼。 下列呼叫**SQLTransact**:  
  
```  
SQLTransact(henv, hdbc, fType)  
```  
  
 對應到  
  
```  
SQLEndTran(SQL_HANDLE_DBC, ConnectionHandle, CompletionType);  
```  
  
 如果*ConnectionHandle*不等於 SQL_NULL_HDBC。 *ConnectionHandle*引數設定的值為*hdbc*。  
  
 **SQL_Transact**對應到  
  
```  
SQLEndTran (SQL_HANDLE_ENV, EnvironmentHandle, CompletionType);  
```  
  
 如果*ConnectionHandle*等於 SQL_NULL_HDBC。 *EnvironmentHandle*引數設定的值為*henv*。  
  
 在上述的情況下，這兩*CompletionType*引數設定為相同的值做為*fType*。
