---
title: SkipLine 方法 |Microsoft 文件
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
- _Stream::raw_SkipLine
- _Stream::SkipLine
helpviewer_keywords:
- Skipline method [ADO]
ms.assetid: 0abc00fe-ee09-4c8e-b1f2-48ee9c5f3329
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a24691a7579efd5585ccecf413158273354152cd
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="skipline-method"></a>SkipLine 方法
讀取文字時，會略過整個一行[資料流](../../../ado/reference/ado-api/stream-object-ado.md)。  
  
## <a name="syntax"></a>語法  
  
```  
  
Stream.SkipLine  
```  
  
## <a name="remarks"></a>備註  
 會略過所有字元，且包含 下一步線分隔符號。 根據預設， [LineSeparator](../../../ado/reference/ado-api/lineseparator-property-ado.md)是**adCRLF**。 如果您嘗試將跳過[EOS](../../../ado/reference/ado-api/eos-property.md)，目前的位置會一直在**EOS**。  
  
 **SkipLine**方法配合文字資料流 ([類型](../../../ado/reference/ado-api/type-property-ado-stream.md)是**adTypeText**)。  
  
## <a name="applies-to"></a>適用於  
 [Stream 物件 (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
