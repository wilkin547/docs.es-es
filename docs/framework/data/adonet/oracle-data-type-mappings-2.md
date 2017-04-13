---
title: "Asignaciones de tipos de datos de Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d2521bcc-0051-4f35-8be3-e8723edeaf6f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# Asignaciones de tipos de datos de Oracle
En la siguiente tabla se muestra el tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] deducido de los tipos de datos del proveedor de datos .NET Framework para Oracle \(<xref:System.Data.OracleClient>\). También se incluyen los métodos de los descriptores de acceso con tipo de <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Tipo de Oracle|Tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|Descriptor de acceso con tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|Descriptor de acceso con tipo de OracleType|  
|--------------------|-------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|-------------------------------------------------|  
|BFILE|Byte\[\]|GetBytes\(\)|GetOracleBFile\(\)|  
|BLOB|Byte\[\]|GetBytes\(\)|GetOracleLob\(\)|  
|CHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|CLOB|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|DATE|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|FLOAT|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTERVAL YEAR TO MONTH \*|Int32|GetInt32\(\)|GetOracleMonthSpan\(\)|  
|INTERVAL DAY TO SECOND \*|TimeSpan|GetTimeSpan\(\)|GetOracleTimeSpan\(\)|  
|LONG|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|LONG RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|NCHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|NCLOB|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|NUMBER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|NVARCHAR2|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|REF CURSOR||||  
|ROWID|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|TIMESTAMP \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH LOCAL TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|UNSIGNED INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|VARCHAR2|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
  
 \* El tipo de Oracle especificado sólo está disponible cuando se utiliza el software de Oracle 9i tanto para el cliente como para el servidor.  
  
 \*\* Un tipo NUMBER de Oracle puede tener un máximo de 38 dígitos significativos. El tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de `decimal` está limitado a 28 dígitos. La lectura de un valor NUMBER de Oracle en un tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de `decimal` produce una excepción `OverflowException` para los valores NUMBER con un tamaño superior a 28 dígitos. Si se lee un valor NUMBER de Oracle desde un objeto `OracleDataReader`, se recomienda llamar al método de descriptor de acceso con tipo `GetOracleNumber` para devolver los valores NUMBER de Oracle como `OracleNumber`. Si rellena un objeto `DataSet`, puede usar el evento `FillError` para determinar si se ha producido una excepción `OverflowException` y emprender la acción adecuada en ese caso. Para obtener información sobre el evento `FillError`, consulte [Control de eventos DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)