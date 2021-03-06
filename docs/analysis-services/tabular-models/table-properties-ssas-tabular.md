---
title: "資料表屬性 |Microsoft 文件"
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.custom: 
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 202902448a31fda27ab2c4d8c0bc894cc50da3db
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2018
---
# <a name="table-properties"></a>Table Properties 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
這篇文章描述表格式模型資料表屬性。 這裡所述的屬性與 [編輯資料表屬性] 對話方塊中的屬性不同，後者會定義從來源匯入的資料行。  
  
 本主題的章節：  
  
-   [資料表屬性](#bkmk_properties)  
  
-   [設定資料表屬性設定](#bkmk_config_prop)  
  
##  <a name="bkmk_properties"></a> 資料表屬性  
 **Basic**  
  
|屬性|預設值|說明|  
|--------------|---------------------|-----------------|  
|**連接名稱**|\<連線名稱 >|資料表之資料來源連接的名稱。<br /><br /> 若要編輯連接，請按一下此按鈕。|  
|**Hidden**|False|指定是否在報表用戶端欄位清單中隱藏資料表。|  
|**資料分割**||資料表的資料分割無法在 **[屬性]** 視窗中顯示。 若要檢視、建立或編輯資料分割，請按一下此按鈕以開啟 [資料分割管理員]。|  
|**來源資料**||資料表的來源資料無法在 **[屬性]** 視窗中顯示。 若要檢視或編輯來源資料，請按一下此按鈕以開啟 [編輯資料表屬性] 對話方塊。|  
|**資料表描述**||資料表的文字描述。<br /><br /> 在 [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)]中，如果使用者將游標置於欄位清單內這個資料表的上方，將以工具提示的形式顯示說明。|  
|**資料表名稱**|\<好記名稱 >|指定資料表的易記名稱。 資料表名稱可在使用 [資料表匯入精靈] 匯入資料表時指定，或在匯入後隨時指定。 模型中的資料表名稱可以不同於在來源的關聯資料表。 資料表易記名稱出現在報表用戶端應用程式欄位清單中以及 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中的模型資料庫。|  
  
 **報表屬性**  
  
 如需詳細的說明與報表屬性的組態資訊，請參閱[Power View 報表屬性](../../analysis-services/tabular-models/power-view-reporting-properties-ssas-tabular.md)。  
  
|屬性|預設值|說明|  
|--------------|---------------------|-----------------|  
|**預設欄位集**|||  
|資料表行為|||  
  
##  <a name="bkmk_config_prop"></a> 設定資料表屬性設定  
  
1.  在模型設計師的 [資料檢視] 中按一下資料表 (索引標籤)，或在 [圖表檢視] 中按一下資料表標頭。  
  
2.  在 **[屬性]** 視窗中按一下屬性，然後輸入值，或按一下按鈕來選取其他組態選項。  
  
  
