---
title: wasNull 方法 (SQLServerResultSet) |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: jdbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
apiname:
- SQLServerResultSet.wasNull
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: d37f80ef-d72c-4429-ada3-1d685bdab6d7
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 944a5bedd9d77432e042bec257810dd627fb5db0
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="wasnull-method-sqlserverresultset"></a>wasNull 方法 (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  確認上一個讀取的值是否為 null 值。  
  
## <a name="syntax"></a>語法  
  
```  
  
public boolean wasNull()  
```  
  
## <a name="return-value"></a>傳回值  
 **true**如果最後一個值讀取為 null。 否則為 **false**。  
  
## <a name="exceptions"></a>例外狀況  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>備註  
 WasNull 方法 java.sql.ResultSet 介面中所指定此 wasNull 方法。  
  
## <a name="see-also"></a>另請參閱  
 [SQLServerResultSet 成員](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 類別](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
