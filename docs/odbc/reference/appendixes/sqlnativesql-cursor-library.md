---
title: SQLNativeSql （資料指標程式庫） |Microsoft 文件
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
- SQLNativeSql function [ODBC], Cursor Library
ms.assetid: c4459092-1177-4b2a-b7f5-e0083d3bf2b2
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f9ce0357981dbc7a499bf0dc0cefc52313a2596a
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="sqlnativesql-cursor-library"></a>SQLNativeSql （資料指標程式庫）
> [!IMPORTANT]  
>  將移除這項功能，在未來的版本的 Windows。 避免在新的開發工作中使用這項功能，並規劃修改目前使用這項功能的應用程式。 Microsoft 建議使用驅動程式的資料指標功能。  
  
 本主題討論使用**SQLNativeSql**資料指標程式庫中的函式。 如需一般資訊**SQLNativeSql**，請參閱[SQLNativeSql 函數](../../../odbc/reference/syntax/sqlnativesql-function.md)。  
  
 如果驅動程式支援此函式，資料指標程式庫呼叫**SQLNativeSql**驅動程式中，並將它的 SQL 陳述式。 定位更新，定位 delete 和**選取更新**陳述式，資料指標程式庫修改陳述式，再將它傳遞至驅動程式。  
  
> [!NOTE]  
>  資料指標程式庫不正確地傳回 SQLSTATE 34000 （無效的資料指標名稱），如果資料指標名稱中無效的定位的更新或刪除陳述式中傳遞*InStatementText*引數的**SQLNativeSql**. **SQLNativeSql**不是傳回語法錯誤，但只有在陳述式準備或執行時才會傳回錯誤。
