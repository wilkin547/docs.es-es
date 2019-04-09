---
title: Asignaciones de tipos de datos de Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: c1fb3a6838e6a1b242255d4035c10ab0ec07d536
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104577"
---
# <a name="oracle-data-type-mappings"></a>Asignaciones de tipos de datos de Oracle
En la siguiente tabla se enumeran los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Tipo de datos de Oracle|Tipo de datos de .NET Framework devuelto por OracleDataReader.GetValue|Tipo de datos OracleClient devuelto por OracleDataReader.GetOracleValue|Comentarios|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para el **número** tipo de datos y está diseñado para que la <xref:System.Data.OracleClient.OracleDataReader> devuelve un **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor de punto flotante. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para el **Number (38)** tipo de datos y está diseñado para que la <xref:System.Data.OracleClient.OracleDataReader> devuelve un **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** tipo de datos no es compatible con la <xref:System.Data.OracleClient.OracleDataReader> objeto.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**UNSIGNED INTEGER**|**número**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para el **Number (38)** tipo de datos y está diseñado para que la <xref:System.Data.OracleClient.OracleDataReader> devuelve un **System.Decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero sin signo. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 En la tabla siguiente se enumera los tipos de datos de Oracle y los tipos de datos de .NET Framework (**System.Data.DbType** y <xref:System.Data.OracleClient.OracleType>) que se usará cuando se enlacen como parámetros.  
  
|Tipo de datos de Oracle|Enumeración DbType para enlazar como un parámetro|Enumeración OracleType para enlazar como un parámetro|Comentarios|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle solo permite enlazar un **BFILE** como un **BFILE** parámetro. El proveedor de datos .NET para Oracle no construye uno automáticamente para usted si intenta enlazar que no es**BFILE** valor, como **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**Blob**|Oracle solo permite enlazar un **BLOB** como un **BLOB** parámetro. El proveedor de datos .NET para Oracle no construye uno automáticamente para usted si intenta enlazar que no es**BLOB** valor, como **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle solo permite enlazar un **CLOB** como un **CLOB** parámetro. El proveedor de datos .NET para Oracle no construye uno automáticamente para usted si intenta enlazar que no es**CLOB** valor, como **System.String** o <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Determina el **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Determina el **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> solo disponible cuando usa software de cliente y servidor de Oracle 9i.|  
|**INTERVAL DAY TO SECOND**|**Object**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> solo disponible cuando usa software de cliente y servidor de Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle solo permite enlazar un **NCLOB** como un **NCLOB** parámetro. El proveedor de datos .NET para Oracle no construye uno automáticamente para usted si intenta enlazar que no es**NCLOB** valor, como **System.String** o <xref:System.Data.OracleClient.OracleString>.|  
|**NUMBER**|**VarNumeric**|**número**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Binary**|**Raw**||  
|**REF CURSOR**||**Cursor**|Para obtener más información, consulte [cursores REF cursor de Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**Marca de tiempo**|<xref:System.Data.OracleClient.OracleType> solo disponible cuando usa software de cliente y servidor de Oracle 9i.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> solo disponible cuando usa software de cliente y servidor de Oracle 9i.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> solo disponible cuando usa software de cliente y servidor de Oracle 9i.|  
|**UNSIGNED INTEGER**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Determina el **System.Data.DBType** y <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 El **InputOutput**, **salida**, y **ReturnValue** **ParameterDirection** valores utilizados por el <xref:System.Data.OracleClient.OracleParameter.Value%2A> propiedad de la <xref:System.Data.OracleClient.OracleParameter> objeto son tipos de datos de .NET Framework, a menos que el valor de entrada es un tipo de datos de Oracle (por ejemplo, <xref:System.Data.OracleClient.OracleNumber> o <xref:System.Data.OracleClient.OracleString>). Esto no es aplicable a **REF CURSOR**, **BFILE**, o **LOB** tipos de datos.  
  
## <a name="see-also"></a>Vea también

- [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
