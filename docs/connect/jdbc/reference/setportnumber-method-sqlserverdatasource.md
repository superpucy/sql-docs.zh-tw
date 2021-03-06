---
title: setPortNumber 方法 (SQLServerDataSource) |Microsoft 文件
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
- SQLServerDataSource.setPortNumber
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 59c5fa23-bc1a-4142-af17-70e275f0b833
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 777493f356306fcb2adad1a1066795246e5a71ff
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="setportnumber-method-sqlserverdatasource"></a>setPortNumber 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  設定用來與通訊的連接埠號碼[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]。  
  
## <a name="syntax"></a>語法  
  
```  
  
public void setPortNumber(int portNumber)  
```  
  
#### <a name="parameters"></a>參數  
 *通訊埠編號*  
  
 **Int**包含通訊埠編號的值。  
  
## <a name="remarks"></a>備註  
 連接埠號碼是開啟的通訊端連接時，會使用 TCP/IP 通訊埠編號[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]。 如果未設定 portNumber 屬性， [getPortNumber](../../../connect/jdbc/reference/getportnumber-method-sqlserverdatasource.md)方法會傳回預設值 1433年。  
  
> [!NOTE]  
>  SetPortNumber 方法不會進行任何範圍檢查傳入的連接埠值。 您可以傳遞無效，如 99999，而不觸發錯誤的通訊埠編號。  
  
## <a name="see-also"></a>另請參閱  
 [SQLServerDataSource 成員](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 類別](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
