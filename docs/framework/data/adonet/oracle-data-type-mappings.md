---
title: "Asignar tipos de datos de Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Asignar tipos de datos de Oracle
En la siguiente tabla se enumeran los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Tipo de datos de Oracle|Tipo de datos de .NET Framework devuelto por OracleDataReader.GetValue|Tipo de datos OracleClient devuelto por OracleDataReader.GetOracleValue|Comentarios|  
|-----------------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------|-----------------|  
|**BFILE**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias del tipo de datos **NUMBER**, y se ha diseñado para que <xref:System.Data.OracleClient.OracleDataReader> devuelva **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor de punto flotante.  El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias del tipo de datos **NUMBER \(38\)**, y se ha diseñado para que <xref:System.Data.OracleClient.OracleDataReader> devuelva **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero.  El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||El objeto <xref:System.Data.OracleClient.OracleDataReader> no admite el tipo de datos **REF CURSOR** de Oracle.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**UNSIGNED INTEGER**|**Número**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias del tipo de datos **NUMBER \(38\)**, y se ha diseñado para que <xref:System.Data.OracleClient.OracleDataReader> devuelva **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero sin signo.  El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 En la siguiente tabla se enumeran los tipos de datos de Oracle y los tipos de datos de .NET Framework \(**System.Data.DbType** y <xref:System.Data.OracleClient.OracleType>\) que se deben utilizar cuando se enlacen como parámetros.  
  
|Tipo de datos de Oracle|Enumeración DbType para enlazar como un parámetro|Enumeración OracleType para enlazar como un parámetro|Comentarios|  
|-----------------------------|-------------------------------------------------------|-----------------------------------------------------------|-----------------|  
|**BFILE**||**BFile**|Oracle sólo permite enlazar un **BFILE** como un parámetro **BFILE**.  El proveedor de datos de .NET para Oracle no construye uno automáticamente si intenta enlazar un valor que no es **BFILE**, como **byte\[\]** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**Blob**|Oracle solo permite enlazar un **BLOB** como un parámetro **BLOB**.  El proveedor de datos .NET para Oracle no construye uno automáticamente si intenta enlazar un valor que no es **BLOB**, como **byte\[\]** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle solo permite enlazar un **CLOB** como un parámetro **CLOB**.  El proveedor de datos .NET para Oracle no construye uno automáticamente si intenta enlazar un valor que no es **CLOB**, como **System.String** o <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> determina **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> determina **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**INTERVAL DAY TO SECOND**|**Objeto**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle solo permite enlazar un **NCLOB** como un parámetro **NCLOB**.  El proveedor de datos .NET para Oracle con construye uno automáticamente si intenta enlazar un valor que no es **NCLOB**, como **System.String** o <xref:System.Data.OracleClient.OracleString>.|  
|**NUMBER**|**VarNumeric**|**Número**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Binary**|**Raw**||  
|**REF CURSOR**||**Cursor**|Para obtener más información, consulta [Cursores REF CURSOR de Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**Marca de tiempo**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**UNSIGNED INTEGER**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> determina **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Los valores **InputOutput**, **Output** y **ReturnValue** **ParameterDirection** utilizados por la propiedad <xref:System.Data.OracleClient.OracleParameter.Value%2A> del objeto <xref:System.Data.OracleClient.OracleParameter> son tipos de datos de .NET Framework, a menos que el valor de entrada sea un tipo de dato de Oracle \(por ejemplo, <xref:System.Data.OracleClient.OracleNumber> o <xref:System.Data.OracleClient.OracleString>\).  Esto no se aplica a los tipos de datos **REF CURSOR**, **BFILE** o **LOB**.  
  
## Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)