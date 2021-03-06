---
title: 靜態 SQL |Microsoft 文件
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- static SQL [ODBC]
- SQL [ODBC], embedded SQL
- SQL statements [ODBC], embedded SQL
- SQL statements [ODBC], static SQL
- embedded SQL [ODBC]
- SQL [ODBC], static SQL
ms.assetid: 667d92ec-fed9-4028-81d4-bb9ba867356a
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 392cf843734bcc668c88f6408227b20df97d43ae
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="static-sql"></a>靜態 SQL
所示的內嵌的 SQL[內嵌的 SQL 範例](../../odbc/reference/embedded-sql-example.md)稱為靜態 SQL。 在程式中的 SQL 陳述式都是靜態的因為呼叫靜態 SQL也就是說，不會變更每次執行程式。 上一節所述，這些陳述式會編譯編譯程式的其餘部分時。  
  
 靜態 SQL 都適用於許多情況下，並可用於任何應用程式可以在程式的設計階段決定的資料存取。 例如，訂單輸入程式一律使用相同的陳述式來插入新的訂單，而航空保留系統一律使用相同的陳述式來變更一個基座的狀態從可用保留。 每個陳述式會透過主機變數; 使用一般化不同的值，請插入銷售訂單，並可以保留不同基座。 因為這類陳述式可能是硬式編碼程式中，這種程式的陳述式必須剖析、 驗證，並最佳化一次，在編譯時期的優點。 這會導致較快的程式碼。
