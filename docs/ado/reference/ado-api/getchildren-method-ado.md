---
title: GetChildren 方法 (ADO) |Microsoft 文件
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
f1_keywords:
- _Record::raw_GetChildren
- _Record::GetChildren
helpviewer_keywords:
- GetChildren method [ADO]
ms.assetid: b3f09bac-4f66-49f6-aa5a-6fbb4fb28338
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4605435d6d85ad9ff23df3f1289c7ddf121673ac
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="getchildren-method-ado"></a>GetChildren 方法 (ADO)
傳回[資料錄集](../../../ado/reference/ado-api/recordset-object-ado.md)其資料列代表集合的子系[記錄](../../../ado/reference/ado-api/record-object-ado.md)。  
  
## <a name="syntax"></a>語法  
  
```  
  
Set recordset = record.GetChildren  
```  
  
## <a name="return-value"></a>傳回值  
 A**資料錄集**物件每個資料列代表目前的子系**記錄**物件。 例如的子系**記錄**，代表目錄會是檔案和子目錄的父目錄內。  
  
## <a name="remarks"></a>備註  
 提供者會決定哪些資料行存在於傳回**資料錄集**。 例如，文件的來源提供者一律會傳回資源**資料錄集**。  
  
## <a name="applies-to"></a>適用於  
  
|||  
|-|-|  
|[Record 物件 (ADO)](../../../ado/reference/ado-api/record-object-ado.md)|[Recordset 物件 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)|
