---
title: "新增資料集篩選、資料區篩選和群組篩選 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.service: 
ms.component: report-design
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fcca7243-a702-4725-8e6f-cf118e988acf
caps.latest.revision: "8"
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 3b3d4f355e52f27689dad4f157ca65edad99fa99
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2018
---
# <a name="add-dataset-filters-data-region-filters-and-group-filters"></a>新增資料集篩選、資料區篩選和群組篩選
  在報表中，篩選屬於資料集、資料區域或資料區域群組的一部分，您可以篩選來限制報表中所要使用的資料。 如果您無法變更資料集查詢，那麼篩選便是協助您控制報表資料的好辦法，例如，如果您正在使用共用的資料集。  
  
 篩選可協助您控制要在報表中顯示和處理哪些資料。 您可以為資料集、資料區或群組的任意組合指定篩選。  
  
 如需詳細資訊，請參閱[將篩選加入資料集中 &#40;報表產生器及 SSRS&#41;](../../reporting-services/report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md) 和[篩選方程式範例 &#40;報表產生器及 SSRS&#41;](../../reporting-services/report-design/filter-equation-examples-report-builder-and-ssrs.md)。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="When"></a> 選擇要設定篩選的時機  
 當您無法篩選來源的資料時，請指定報表項目的篩選。 例如，當資料來源不支援查詢參數、您必須執行預存程序但無法修改查詢，或者參數化報表快照集會針對不同的使用者顯示自訂資料時，請使用報表篩選。  
  
 您可以在擷取報表資料集之前或之後來篩選報表資料。 若要在擷取資料之前進行篩選，請針對每個資料集變更查詢。 當您篩選查詢中的資料時，您會篩選資料來源中的資料，這樣會減少在報表中擷取及處理所需的資料量。 若要在擷取資料之後進行篩選，請在報表中建立篩選運算式。 您可以為資料集、資料區或群組 (包括詳細資料群組) 設定篩選運算式。 您也可以在篩選運算式中包含參數，提供一個方式來為特定值或特定使用者篩選資料，例如，篩選可識別檢視報表之使用者的值。  
  
##  <a name="Where"></a> 選擇要設定篩選的位置  
 依據您想要在報表中達成的效果，判斷要設定篩選的位置。 在執行階段，報表處理器會按照下列順序套用篩選：套用至資料集、套用至資料區，然後由上而下套用至每個群組階層中的群組。 在資料表、矩陣和清單上，系統會針對資料列群組、資料行群組和相鄰群組獨立套用篩選。 在圖表上，系統會針對類別目錄群組和數列群組獨立套用篩選。 當報表處理器套用篩選時，系統就會按照在每個報表項目之 [屬性] 對話方塊的 [篩選] 頁面上定義的順序套用所有篩選方程式，而這就相當於使用布林值 AND 作業來結合這些篩選方程式。  
  
 下列清單會比較針對不同報表項目設定篩選的效果：  
  
-   **資料集** ：當您想讓繫結至單一資料集的一個或多個資料區以相同的方式篩選時，請設定資料集的篩選。 例如，您可以針對同時繫結至顯示銷售資料之資料表和顯示相同資料之圖表的資料集設定篩選。  
  
-   **資料區** ：當您想讓繫結至單一資料集的一個或多個資料區提供不同的資料集檢視時，請設定資料區的篩選。 例如，您可以在同一份報表中，設定某個資料表資料區域的篩選來顯示銷售量前十名的商店，並且設定不同資料表資料區域的篩選來顯示銷售量後十名的商店。  
  
-   **Tablix 資料區中的資料列或資料行群組** ：當您想要針對群組運算式包含或排除特定值來控制要在資料表、矩陣或清單中顯示哪些群組值時，請設定群組的篩選。  
  
-   **Tablix 資料區中的詳細資料群組** ：當您針對某個資料區設有多個詳細資料群組，而且想讓每個詳細資料群組顯示資料集中的不同資料組時，請設定詳細資料群組的篩選。  
  
-   **圖表資料區中的數列或類別目錄群組：** 當您想要針對群組運算式包含或排除特定值來控制要在圖表中顯示哪些值時，請設定數列或類別目錄群組的篩選。  
  
 回到頁首  
  
##  <a name="FilterEquations"></a> 了解篩選方程式  
 在執行階段，報表處理器會將值轉換成指定的資料類型，然後使用指定的運算子來比較運算式和值。 下列清單將描述篩選方程式的每個部分：  
  
-   **運算式** ：定義您要篩選的項目。 一般而言，這是資料集欄位。  
  
-   **資料類型** ：指定報表處理器在執行階段評估篩選方程式時要使用的資料類型。 您所選取的資料類型必須是報表定義結構描述所支援的其中一種資料類型。  
  
-   **運算子** ：定義如何比較篩選方程式的兩個部分。  
  
-   **值** ：定義要在比較中使用的運算式。  
  
 下列各節將描述篩選方程式的每個部分。  
  
### <a name="expression"></a>運算式  
 當報表處理器在執行階段評估篩選方程式時，運算式和值的資料類型必須相同。 您針對 [運算式] 選取的欄位資料類型是由用來從資料來源中擷取資料的資料處理延伸模組或資料提供者所決定。 您針對 [值] 輸入的運算式資料類型是由 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 預設值所決定。 資料類型的選擇是由支援報表定義的資料類型所決定。 資料提供者可能會將資料庫的值轉換成 CLR 類型。  
  
### <a name="data-type"></a>資料類型  
 若要讓報表處理器比較兩個值，其資料類型必須相同。 下表將列出 CLR 資料類型與報表定義資料類型之間的對應。 您從資料來源中擷取的資料可能會在它是報表資料時轉換成不同的資料類型。  
  
|**報表定義結構描述資料類型**|**CLR 類型**|  
|--------------------------------------------|-----------------------|  
|**布林**|**布林**|  
|**DateTime**|**DateTime**、 **DateTimeOffset**|  
|**Integer**|**Int16**、 **Int32**、 **UInt16**、 **Byte**、 **SByte**|  
|**Float**|**Single**、 **Double**、 **Decimal**|  
|**Text**|**String**、 **Char**、 **GUID**、 **Timespan**|  
  
 如果您必須指定資料類型，就可以在運算式的 Value 部分中指定自己的轉換。  
  
### <a name="operator"></a>運算子  
 下表將列出您可以在篩選方程式中使用的運算子，以及報表處理器用來評估篩選方程式的項目。  
  
|運算子|動作|  
|--------------|------------|  
|**Equal、Like、NotEqual、GreaterThan、GreaterThanOrEqual、LessThan、LessThanOrEqual**|比較運算式與單一值。|  
|**TopN、BottomN**|比較運算式與單一 **整數** 值。|  
|**TopPercent、BottomPercent**|比較運算式與單一 **整數** 或 **浮點數** 值。|  
|**介於**|測試運算式是否位於 (包含) 兩個值之間。|  
|**In**|測試運算式是否包含在一組值之中。|  
  
### <a name="value"></a>ReplTest1  
 Value 運算式會指定篩選方程式的最終部分。 報表處理器會將評估的運算式轉換成您所指定的資料類型，然後評估整個篩選方程式，以便判斷在 [運算式] 中指定的資料是否通過篩選。  
  
 若要轉換成不是標準 CLR 資料類型的資料類型，您必須修改運算式，以便明確轉換成資料類型。 在 [運算式] 對話方塊中，您可以使用列於 [一般函數] 之 [轉換] 底下的轉換函數。 例如，若為代表在 `ListPrice` 資料來源上儲存成 **money** 資料類型之資料的欄位 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ，資料處理延伸模組就會將欄位值傳回成 <xref:System.Decimal> 資料類型。 若要將篩選設定成僅使用報表貨幣中大於 **$50000.00** 的值，請使用運算式 `=CDec(50000.00)`，將此值轉換成十進位。  
  
 這個值也可以包含參數參考，以便允許使用者以互動方式選取要篩選的值。  
  
 回到頁首  
  
## <a name="see-also"></a>另請參閱  
 [報表中的運算式用法 &#40;報表產生器及 SSRS&#41;](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)   
 [報表參數 &#40;報表產生器和報表設計師&#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)  
  
  
