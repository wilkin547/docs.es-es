---
title: Mappings1 de tipo de datos de Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6ec4bc061ea7a2b7875c9c5521d73dfd2e96954a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="oracle-data-type-mappings"></a>Asignaciones de tipos de datos de Oracle
En la siguiente tabla se enumeran los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Tipo de datos de Oracle|Tipo de datos de .NET Framework devuelto por OracleDataReader.GetValue|Tipo de datos OracleClient devuelto por OracleDataReader.GetOracleValue|Comentarios|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para la **número** tipo de datos y está diseñado para que la <xref:System.Data.OracleClient.OracleDataReader> devuelve un **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor de punto flotante. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**ENTERO**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para la **Number (38)** tipo de datos y está diseñado para que la <xref:System.Data.OracleClient.OracleDataReader> devuelve un **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**AÑO DEL INTERVALO AL MES**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**DÍA DE INTERVALO EN SEGUNDOS**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NÚMERO**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**SIN FORMATO**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** tipo de datos no es compatible con la <xref:System.Data.OracleClient.OracleDataReader> objeto.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**MARCA DE TIEMPO**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**MARCA DE TIEMPO CON LA ZONA HORARIA LOCAL**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**MARCA DE TIEMPO CON LA ZONA HORARIA**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ENTERO SIN SIGNO**|**Número**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para la **Number (38)** tipo de datos y está diseñado para que la <xref:System.Data.OracleClient.OracleDataReader> devuelve un **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero sin signo. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 En la tabla siguiente se enumera los tipos de datos de Oracle y los tipos de datos de .NET Framework (**System.Data.DbType** y <xref:System.Data.OracleClient.OracleType>) para utilizar cuando se enlacen como parámetros.  
  
|Tipo de datos de Oracle|Enumeración DbType para enlazar como un parámetro|Enumeración OracleType para enlazar como un parámetro|Comentarios|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle sólo permite enlazar un **BFILE** como un **BFILE** parámetro. El proveedor de datos de .NET para Oracle no construye uno automáticamente automáticamente si intenta enlazar no**BFILE** valor, como **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**BLOB**|Oracle sólo permite enlazar un **BLOB** como un **BLOB** parámetro. El proveedor de datos de .NET para Oracle no construye uno automáticamente automáticamente si intenta enlazar no**BLOB** valor, como **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle sólo permite enlazar un **CLOB** como un **CLOB** parámetro. El proveedor de datos de .NET para Oracle no construye uno automáticamente automáticamente si intenta enlazar no**CLOB** valor, como **System.String** o <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double o Decimal**|**Float, Double, número**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Determina la **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**ENTERO**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, número**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Determina la **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**AÑO DEL INTERVALO AL MES**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**DÍA DE INTERVALO EN SEGUNDOS**|**Objeto**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle sólo permite enlazar un **NCLOB** como un **NCLOB** parámetro. El proveedor de datos de .NET para Oracle no construye uno automáticamente automáticamente si intenta enlazar no**NCLOB** valor, como **System.String** o <xref:System.Data.OracleClient.OracleString>.|  
|**NÚMERO**|**VarNumeric**|**Número**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**SIN FORMATO**|**Binary**|**Sin formato**||  
|**REF CURSOR**||**Cursor**|Para obtener más información, consulte [cursores REF cursor de Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**MARCA DE TIEMPO**|**DateTime**|**Marca de tiempo**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**MARCA DE TIEMPO CON LA ZONA HORARIA LOCAL**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**MARCA DE TIEMPO CON LA ZONA HORARIA**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**ENTERO SIN SIGNO**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, número**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Determina la **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 El **InputOutput**, **salida**, y **ReturnValue** **ParameterDirection** valores utilizados por la <xref:System.Data.OracleClient.OracleParameter.Value%2A> propiedad de la <xref:System.Data.OracleClient.OracleParameter> objeto son tipos de datos de .NET Framework, a menos que el valor de entrada sea un tipo de datos de Oracle (por ejemplo, <xref:System.Data.OracleClient.OracleNumber> o <xref:System.Data.OracleClient.OracleString>). Esto no se aplica a **REF CURSOR**, **BFILE**, o **LOB** tipos de datos.  
  
## <a name="see-also"></a>Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
