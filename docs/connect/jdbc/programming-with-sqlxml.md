---
title: 使用 SQLXML 進行程式設計 |Microsoft 文件
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
ms.assetid: 4d2cc57c-7293-4d92-b8b1-525e2b35f591
caps.latest.revision: 23
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 91d2b0b1048b6385bcae2b3c9aa523962a4c1d22
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="programming-with-sqlxml"></a>使用 SQLXML 進行程式設計
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  本章節描述如何使用[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]API 方法來儲存及擷取 XML 文件，並從關聯式資料庫使用**SQLXML**物件。  
  
 本節同時包含有關 SQLXML 物件類型的資訊，並提供使用 SQLXML 物件時重要指導方針和限制的清單。  
  
## <a name="reading-and-writing-xml-data-with-sqlxml-objects"></a>讀取和寫入具有 SQLXML 物件的 XML 資料  
 下列清單說明如何使用[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]API 方法來讀取和寫入具有 SQLXML 物件的 XML 資料：  
  
-   若要建立的 SQLXML 物件，使用[createSQLXML](../../connect/jdbc/reference/createsqlxml-method-sqlserverconnection.md)方法[SQLServerConnection](../../connect/jdbc/reference/sqlserverconnection-class.md)類別。 請注意，這種方法會建立不含任何資料的 SQLXML 物件。 若要加入**xml** SQLXML 物件的資料呼叫 SQLXML 介面中指定下列方法之一： setResult setCharacterStream、 setBinaryStream、 或 setString。  
  
-   若要擷取 SQLXML 物件本身，請使用 getSQLXML 方法[SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md)類別或[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別。  
  
-   若要擷取**xml**的 SQLXML 物件的資料使用 SQLXML 介面中指定下列方法之一： Ierrorinfo getCharacterStream，getBinaryStream，或 getString。  
  
-   若要更新**xml**的 SQLXML 物件中的資料使用[updateSQLXML](../../connect/jdbc/reference/updatesqlxml-method-sqlserverresultset.md)方法[SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md)類別。  
  
-   類型的資料庫資料表資料行中儲存 SQLXML 物件**xml**，使用的 setSQLXML 方法[SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)類別或[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別。  
  
 中的範例程式碼[SQLXML 資料類型範例](../../connect/jdbc/sqlxml-data-type-sample.md)示範如何執行這些常見的 API 工作。  
  
## <a name="readable-and-writable-sqlxml-objects"></a>可讀取和可寫入的 SQLXML 物件  
 下表將列出 JDBC API 提供之 setter、getter 和 updater 方法所支援的 SQLXML 物件類型。 此表格中的欄位代表下列項目：  
  
-   **方法名稱**欄會列出 JDBC API 中支援的 getter、 setter 和 updater 方法。  
  
-   **Getter SQLXML 物件**欄位代表 SQLXML 物件，它由  [getSQLXML](../../connect/jdbc/reference/getsqlxml-method-sqlservercallablestatement.md)方法[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別或[getSQLXML](../../connect/jdbc/reference/getsqlxml-method-sqlserverresultset.md)方法[SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md)類別。  
  
-   **Setter SQLXML 物件**欄位代表的 SQLXML 物件，它由[createSQLXML](../../connect/jdbc/reference/createsqlxml-method-sqlserverconnection.md)方法[SQLServerConnection](../../connect/jdbc/reference/sqlserverconnection-class.md)類別。 請注意，下列 setter 方法接受只所建立的 SQLXML 物件[createSQLXML](../../connect/jdbc/reference/createsqlxml-method-sqlserverconnection.md)方法。  
  
|方法名稱|Getter SQLXML 物件<br /><br /> (可讀取)|Setter SQLXML 物件<br /><br /> (可寫入)|  
|-----------------|-------------------------------------------|-------------------------------------------|  
|CallableStatement.setSQLXML()|不支援|Supported|  
|CallableStatement.setObject()|不支援|Supported|  
|PreparedStatement.setSQLXML()|不支援|Supported|  
|Preparedstatement.setobject （)|不支援|Supported|  
|ResultSet.updateSQLXML()|不支援|Supported|  
|ResultSet.updateObject()|不支援|Supported|  
|ResultSet.getSQLXML()|Supported|不支援|  
|CallableStatement.getSQLXML()|Supported|不支援|  
  
 如上表所示，setter SQLXML 方法無法使用可讀取的 SQLXML 物件。同樣地，getter 方法無法使用可寫入的 SQLXML 物件。  
  
 如果應用程式叫用的 setObject 方法所使用的 SQLXML 物件中指定的小數位數或長度參數，則會忽略小數位數或長度參數。  
  
## <a name="guidelines-and-limitations-when-using-sqlxml-objects"></a>使用 SQLXML 物件時的指導方針和限制  
 應用程式可以使用 SQLXML 物件，在資料庫中讀取和寫入 XML 資料。 下列清單將提供有關使用 SQLXML 物件時特定限制和指引的資訊：  
  
-   SQLXML 物件只有在建立此物件的交易持續期間有效。  
  
-   從 getter 方法擷取的 SQLXML 物件只能用來讀取資料。  
  
-   連接物件所建立的 SQLXML 物件只能用來寫入資料。  
  
-   應用程式只能針對可讀取的 SQLXML 物件叫用單一 getter 方法來讀取資料。 叫用 getter 方法之後，相同 SQLXML 物件上的所有其他 getter 或 setter 方法都會失敗。  
  
-   應用程式在讀取或寫入之後，可以叫用只有 SQLXML 物件上的可用方法。 不過，只要基礎資料行或參數使用中，它仍然能夠處理傳回的資料流或來源。 如果基礎資料行或參數變成非使用中，與 SQLXML 物件相關聯的資料流或來源將會關閉。 如果基礎資料行或參數不再有效，基礎資料將不適用於 Stream、Simple API for XML (SAX) 和 Streaming API for XML (StAX) getter。  
  
-   應用程式只能針對可寫入的 SQLXML 物件叫用單一 setter 方法。 叫用 setter 方法之後，相同 SQLXML 物件上的所有其他 setter 或 getter 方法都會失敗。  
  
-   若要設定 SQLXML 物件的資料，應用程式必須在傳回的物件中使用適當的 setter 方法與函數。  
  
-   GetSQLXML 方法[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別和[SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md)類別會傳回**null**資料為基礎的資料行是否**null**。  
  
-   setter 物件可以透過在其中建立這些物件的連接生效。  
  
-   不允許應用程式設定**null**使用 SQLXML 介面所提供的 setter 方法的值。 應用程式可以使用 SQLXML 介面中提供的 setter 方法來設定空字串 ("")。 若要設定**null**值，應用程式應該呼叫下列其中之一：  
  
    -   SetNull 方法[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別和[SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)類別。  
  
    -   SetObject 方法[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別和[SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)類別。  
  
    -   SetSQLXML 方法[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)類別和[SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)類別**null**參數值。  
  
-   基於效能考量，使用 XML 文件時，我們建議您使用 Simple API for XML (SAX) 和 Streaming API for XML (StAX) 剖析器，而非文件物件模型 (DOM) 剖析器。  
  
 XML 剖析器無法處理空值。 不過，SQL Server 允許應用程式在 XML 資料類型的資料庫資料行中擷取和儲存空值。 這表示，剖析 XML 資料時，如果基礎值是空的，剖析器就會擲回例外狀況。 若為 DOM 輸出，JDBC Driver 會捕捉例外狀況並擲回錯誤。 若為 SAX 和 Stax 輸出，錯誤則直接來自剖析器。  
  
## <a name="adaptive-buffering-and-sqlxml-support"></a>適應性緩衝和 SQLXML 支援  
 SQLXML 物件所傳回的二進位和字元資料流會遵循適應性或完整緩衝模式。 反之，如果 XML 剖析器不是資料流，它們就不會遵循適應性或完整設定。 如需有關適應性緩衝的詳細資訊，請參閱[使用適應性緩衝](../../connect/jdbc/using-adaptive-buffering.md)。  
  
## <a name="see-also"></a>另請參閱  
 [支援 XML 資料](../../connect/jdbc/supporting-xml-data.md)  
  
  
