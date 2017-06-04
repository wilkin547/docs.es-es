---
title: "Asignar tipos de datos ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Asignar tipos de datos ODBC
La siguiente tabla muestra el tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] deducido de los tipos de datos del proveedor de datos .NET Framework para ODBC \(<xref:System.Data.Odbc>\).  También se incluyen los métodos de los descriptores de acceso con tipo de <xref:System.Data.Odbc.OdbcDataReader>.  
  
|Tipo de ODBC|Tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|Descriptor de acceso con tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|  
|------------------|-------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|  
|SQL\_BIGINT|Int64|GetInt64\(\)|  
|SQL\_BINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_BIT|Boolean|GetBoolean\(\)|  
|SQL\_CHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_DECIMAL|Decimal|GetDecimal\(\)|  
|SQL\_DOUBLE|Double|GetDouble\(\)|  
|SQL\_GUID|Guid|GetGuid\(\)|  
|SQL\_INTEGER|Int32|GetInt32\(\)|  
|SQL\_LONG\_VARCHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_LONGVARBINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_NUMERIC|Decimal|GetDecimal\(\)|  
|SQL\_REAL|Single|GetFloat\(\)|  
|SQL\_SMALLINT|Int16|GetInt16\(\)|  
|SQL\_TINYINT|Byte|GetByte\(\)|  
|SQL\_TYPE\_TIMES|DateTime|GetDateTime\(\)|  
|SQL\_TYPE\_TIMESTAMP|DateTime|GetDateTime\(\)|  
|SQL\_VARBINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_WCHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_WLONGVARCHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_WVARCHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
  
## Vea también  
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)