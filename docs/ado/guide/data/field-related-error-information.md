---
title: 欄位相關錯誤資訊 |Microsoft 文件
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
helpviewer_keywords:
- field-related errors [ADO]
- errors [ADO], field-related
ms.assetid: 5e7b1af4-996b-47c5-9161-c5575ad4fec9
caps.latest.revision: 4
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ec0241e4d57a53776e1d124d697657d464f4e515
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
---
# <a name="field-related-error-information"></a>欄位相關的錯誤資訊
如果錯誤直接相關的欄位 — 比方說，如果資料遺漏，或者它是欄位的錯誤類型 — 您可以擷取問題的原因的詳細資訊，藉由檢查**欄位**物件的**狀態**屬性。 這個屬性已經過增強，以提供特定問題的相關資訊。 所以舉例來說，當呼叫**UpdateBatch**失敗，問題的原因可以檢查來判斷**狀態**屬性**欄位**中每個受影響的功能記錄。 此屬性包含值的其中一個**FieldStatusEnum**常數。 下表包含發生錯誤時，會特別感興趣的那些值。  
  
|常數|Value|Description|  
|--------------|-----------|-----------------|  
|**adFieldCantConvertValue**|2|表示無法擷取的欄位，或儲存而不會遺失資料。|  
|**adFieldDataOverflow**|6|指出提供者所傳回的資料造成溢位欄位的資料類型。|  
|**adFieldDefault**|13|表示欄位的預設值已設定資料時使用。|  
|**adFieldIgnore**|15|表示，在來源中的設定資料值時，已略過此欄位。 提供者已不設定任何值。|  
|**adFieldIntegrityViolation**|10|表示無法修改的欄位，因為它是導出或衍生的實體。|  
|**adFieldIsNull**|3|指出提供者傳回了 null 值。|  
|**adFieldOutOfSpace**|22|表示提供者無法取得足夠的儲存空間可完成移動或複製作業。|
