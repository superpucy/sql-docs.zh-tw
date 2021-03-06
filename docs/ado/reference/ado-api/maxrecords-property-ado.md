---
title: MaxRecords 屬性 (ADO) |Microsoft 文件
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
- Recordset15::MaxRecords
helpviewer_keywords:
- MaxRecords property [ADO]
ms.assetid: 20c76571-8c9a-482c-a99e-726ab1d93f8b
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1eb073548d3f2b7b9422b416cdcc5c20a7984a56
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="maxrecords-property-ado"></a>MaxRecords 屬性 (ADO)
表示要傳回的記錄數目上限[資料錄集](../../../ado/reference/ado-api/recordset-object-ado.md)從查詢。  
  
## <a name="settings-and-return-values"></a>設定和傳回值  
 設定或傳回**長**值，指出要傳回的記錄數目上限。 預設值是零 (**0**)，這表示沒有限制。  
  
## <a name="remarks"></a>備註  
 使用**MaxRecords**屬性來限制從資料來源提供者所傳回的記錄數目。 這個屬性的預設設定是零，表示提供者會傳回所有要求的記錄。  
  
 **MaxRecords**屬性是讀取/寫入時**資料錄集**開啟時，已關閉，且為唯讀。  
  
## <a name="applies-to"></a>適用於  
 [Recordset 物件 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>另請參閱  
 [MaxRecords 屬性範例 (VB)](../../../ado/reference/ado-api/maxrecords-property-example-vb.md)   
 [MaxRecords 屬性範例 (VC++)](../../../ado/reference/ado-api/maxrecords-property-example-vc.md)   
