---
title: compareTo 方法 (DateTimeOffset) |Microsoft 文件
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
ms.assetid: e4cf2ea4-0fe9-40ce-ba79-f2a2b616997e
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b8307787576f520f83ceeffe10c830cd06a16d69
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="compareto-method-datetimeoffset"></a>compareTo 方法 (DateTimeOffset)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  比較這個**DateTimeOffset**物件與其他**DateTimeOffset**物件根據 gmt 的時間。  
  
## <a name="syntax"></a>語法  
  
```  
  
public int compareTo(DateTimeOffset other)  
```  
  
#### <a name="parameters"></a>參數  
 A [DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-class.md)您想要與目前的執行個體比較的值。  
  
## <a name="return-value"></a>傳回值  
 下表描述此方法的傳回值。  
  
|傳回值|Description|  
|------------------|-----------------|  
|0|同時**DateTimeOffset**物件代表相同的點的時間。|  
|負數|這**DateTimeOffset**物件表示之前的時間點*其他*。|  
|正數|這**DateTimeOffset**物件表示某個點的時間之後*其他*。|  
  
## <a name="remarks"></a>備註  
 當兩個**DateTimeOffset**物件在 GMT 具有相同的時間，根據位移的物件沒有其他順序。  
  
## <a name="see-also"></a>另請參閱  
 [DateTimeOffset 類別](../../../connect/jdbc/reference/datetimeoffset-class.md)   
 [DateTimeOffset 成員](../../../connect/jdbc/reference/datetimeoffset-members.md)  
  
  
