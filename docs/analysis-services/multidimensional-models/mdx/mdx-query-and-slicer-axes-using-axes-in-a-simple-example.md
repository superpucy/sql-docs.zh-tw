---
title: "在簡單的範例 (MDX) 中使用查詢及 Slicer 軸 |Microsoft 文件"
ms.custom: 
ms.date: 03/04/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 5e3dd069c68623f9f0cc5f4fa90a06ca9a3568e1
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2018
---
# <a name="mdx-query-and-slicer-axes---using-axes-in-a-simple-example"></a>MDX 查詢及 Slicer 軸的簡單範例中使用軸
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
本主題中的簡單範例說明指定和使用查詢及 Slicer 軸的基本知識。  
  
## <a name="the-cube"></a>Cube  
 一個稱為 TestCube 的 Cube，有稱為 Route 與 Time 的兩個簡單維度。 每個維度都只有一個使用者階層，分別稱為 Route 與 Time。 因為 Cube 的量值是 Measures 維度的一部份，這個 Cube 總共有 3 個維度。  
  
## <a name="the-query"></a>查詢  
 查詢是要提供一個矩陣，在此矩陣中，Packages 量值可以在路徑與時間之間交叉比較。  
  
 在下列的 MDX 查詢範例中，Route 與 Time 階層是查詢座標軸，而 Measures 維度則是 Slicer 軸。 [Members](../../../mdx/members-set-mdx.md) 函數指出 MDX 將會使用階層或層級的成員建構集合。 使用 **Members** 函數代表您不需要在 MDX 查詢中，明確地陳述特定階層或層級的每個成員。  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a>結果  
 所得結果會是可識別 Packages 量值一值的方格，此量值位於 COLUMNS 與 ROWS 座標軸維度的每個交集處。 下表顯示此方格內容：  
  
||air|sea|  
|-|---------|---------|  
|1st quarter|60|50|  
|2nd quarter|45|45|  
  
## <a name="see-also"></a>另請參閱  
 [指定查詢座標軸 &#40; 的內容MDX &#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)   
 [指定 Slicer 軸 &#40; 的內容MDX &#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
