---
title: "Length of Column Data"
description: "Length of Column Data"
author: David-Engel
ms.author: davidengel
ms.date: "01/19/2017"
ms.service: sql
ms.subservice: connectivity
ms.topic: reference
helpviewer_keywords:
  - "column data [ODBC]"
  - "length of column data [ODBC]"
  - "ODBC cursor library [ODBC], cache"
  - "cursor library [ODBC], cache"
  - "cache [ODBC]"
---
# Length of Column Data
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work and plan to modify applications that currently use this feature. Microsoft recommends using the driver's cursor functionality.  
  
 The cursor library creates a buffer in the cache for each length/indicator buffer bound to the result set with **SQLBindCol**. It uses the values in these buffers to construct a **WHERE** clause when it emulates positioned update or delete statements. It updates these buffers from the rowset buffers when it fetches data from the data source and when it executes positioned update statements.  
  
 If the C type of a data buffer is SQL_C_CHAR or SQL_C_BINARY, and the length/indicator value is SQL_NTS, the string length of the data is put into the length/indicator buffer.  
  
> [!NOTE]  
>  The cursor library does not update its cache for a column if **StrLen_or_IndPtr* in the corresponding rowset buffer is SQL_DATA_AT_EXEC or the result of the SQL_LEN_DATA_AT_EXEC macro.
