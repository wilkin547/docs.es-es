---
description: Más información acerca de las asignaciones de tipos de datos de Oracle
title: Asignaciones de tipos de datos de Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: 1b5a130916a54049518b8b335fbf384d99035090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754373"
---
# <a name="oracle-data-type-mappings"></a>Asignaciones de tipos de datos de Oracle

En la siguiente tabla se enumeran los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Tipo de datos de Oracle|Tipo de datos de .NET Framework devuelto por OracleDataReader.GetValue|Tipo de datos OracleClient devuelto por OracleDataReader.GetOracleValue|Observaciones|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para el tipo de datos **Number** y está diseñado para que <xref:System.Data.OracleClient.OracleDataReader> devuelva un valor **System. decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor de punto flotante. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para el tipo de datos **Number (38)** y está diseñado para que <xref:System.Data.OracleClient.OracleDataReader> devuelva un valor **System. decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**INTERVALO AÑO A MES**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVALO DE DÍA A SEGUNDO**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NÚMEROS**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**Socket**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||El tipo de datos **ref cursor** de Oracle no es compatible con el <xref:System.Data.OracleClient.OracleDataReader> objeto.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**MARCA DE TIEMPO CON ZONA HORARIA**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ENTERO SIN SIGNO**|**Number**|<xref:System.Data.OracleClient.OracleNumber>|Este tipo de datos es un alias para el tipo de datos **Number (38)** y está diseñado para que <xref:System.Data.OracleClient.OracleDataReader> devuelva un valor **System. decimal** o <xref:System.Data.OracleClient.OracleNumber> en lugar de un valor entero sin signo. El uso del tipo de datos de .NET Framework puede ocasionar un desbordamiento.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 En la tabla siguiente se enumeran los tipos de datos de Oracle y los tipos de datos .NET Framework (**System. Data. DbType** y <xref:System.Data.OracleClient.OracleType> ) que se van a usar al enlazarlos como parámetros.  
  
|Tipo de datos de Oracle|Enumeración DbType para enlazar como un parámetro|Enumeración OracleType para enlazar como un parámetro|Observaciones|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**Sobre**|Oracle solo permite enlazar un **BFILE** como parámetro **BFILE** . El proveedor de datos .NET para Oracle no construye uno automáticamente si intenta enlazar un valor no **BFILE** , como **Byte []** o <xref:System.Data.OracleClient.OracleBinary> .|  
|**BLOB**||**Blob**|Oracle solo permite enlazar un **BLOB** como parámetro de **BLOB** . El proveedor de datos .NET para Oracle no construye uno automáticamente si intenta enlazar un valor que no es **BLOB** , como **Byte []** o <xref:System.Data.OracleClient.OracleBinary> .|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle solo permite enlazar un **CLOB** como parámetro **CLOB** . El proveedor de datos .NET para Oracle no construye uno automáticamente si intenta enlazar un valor que no es **CLOB** , como **System. String** o <xref:System.Data.OracleClient.OracleString> .|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> determina los **datos System. Data. DBType** y <xref:System.Data.OracleClient.OracleType> .|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> determina los **datos System. Data. DBType** y <xref:System.Data.OracleClient.OracleType> .|  
|**INTERVALO AÑO A MES**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**INTERVALO DE DÍA A SEGUNDO**|**Object**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binario**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle solo permite enlazar un **NCLOB** como parámetro **NCLOB** . El proveedor de datos .NET para Oracle no construye uno automáticamente si intenta enlazar un valor que no sea **NCLOB** , como **System. String** o <xref:System.Data.OracleClient.OracleString> .|  
|**NÚMEROS**|**VarNumeric**|**Number**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**Socket**|**Binario**|**Sin formato**||  
|**REF CURSOR**||**Cursor**|Para obtener más información, vea [cursores REF cursor de Oracle](oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**Pseudocolumna**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**MARCA DE TIEMPO CON ZONA HORARIA**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> solo está disponible cuando se usa el software de cliente y servidor de Oracle 9i.|  
|**ENTERO SIN SIGNO**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> determina los **datos System. Data. DBType** y <xref:System.Data.OracleClient.OracleType> .|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Los valores de **ParameterDirection** , **Output** y **ReturnValue** **que usa** la <xref:System.Data.OracleClient.OracleParameter.Value%2A> propiedad del <xref:System.Data.OracleClient.OracleParameter> objeto son .NET Framework tipos de datos, a menos que el valor de entrada sea un tipo de datos de Oracle (por ejemplo, <xref:System.Data.OracleClient.OracleNumber> o <xref:System.Data.OracleClient.OracleString> ). Esto no se aplica a los tipos de datos **ref cursor**, **BFILE** o **LOB** .  
  
## <a name="see-also"></a>Vea también

- [Oracle y ADO.NET](oracle-and-adonet.md)
- [Información general de ADO.NET](ado-net-overview.md)
