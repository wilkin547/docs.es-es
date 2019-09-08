---
title: Asignaciones de tipos de datos de OLE DB
ms.date: 03/30/2017
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
ms.openlocfilehash: 969433b2582771a0ed57217180c2795f9359956f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783485"
---
# <a name="ole-db-data-type-mappings"></a>Asignaciones de tipos de datos de OLE DB
En la tabla siguiente se muestra el tipo de .NET Framework deducido para los tipos de datos del proveedor de datos .NET Framework para<xref:System.Data.OleDb>ADO y OLE DB (). También <xref:System.Data.OleDb.OleDbDataReader> se enumeran los métodos de descriptor de acceso con tipo para.  
  
|Tipo de ADO|Tipo de OLE DB|Tipo .NET Framework|.NET Framework descriptor de acceso con tipo|  
|--------------|-----------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|adBigInt|DBTYPE_I8|Int64|GetInt64()|  
|adBinary|DBTYPE_BYTES|Byte[]|GetBytes()|  
|adBoolean|DBTYPE_BOOL|Boolean|GetBoolean()|  
|adBSTR|DBTYPE_BSTR|string|GetString()|  
|adChapter|DBTYPE_HCHAPTER|Compatible con `DataReader`. Consulte [recuperación de datos mediante DataReader](retrieving-data-using-a-datareader.md).|GetValue()|  
|adChar|DBTYPE_STR|string|GetString()|  
|adCurrency|DBTYPE_CY|Decimal|GetDecimal()|  
|adDate|DBTYPE_DATE|DateTime|GetDateTime()|  
|adDBDate|DBTYPE_DBDATE|DateTime|GetDateTime()|  
|adDBTime|DBTYPE_DBTIME|DateTime|GetDateTime()|  
|adDBTimeStamp|DBTYPE_DBTIMESTAMP|DateTime|GetDateTime()|  
|adDecimal|DBTYPE_DECIMAL|Decimal|GetDecimal()|  
|adDouble|DBTYPE_R8|Double|GetDouble()|  
|adError|DBTYPE_ERROR|ExternalException|GetValue()|  
|adFileTime|DBTYPE_FILETIME|DateTime|GetDateTime()|  
|adGUID|DBTYPE_GUID|Guid|GetGuid()|  
|adIDispatch|DBTYPE_IDISPATCH *|Object|GetValue()|  
|adInteger|DBTYPE_I4|Int32|GetInt32()|  
|adIUnknown|DBTYPE_IUNKNOWN *|Object|GetValue()|  
|adNumeric|DBTYPE_NUMERIC|Decimal|GetDecimal()|  
|adPropVariant|DBTYPE_PROPVARIANT|Object|GetValue()|  
|adSingle|DBTYPE_R4|Single|GetFloat()|  
|adSmallInt|DBTYPE_I2|Int16|GetInt16()|  
|adTinyInt|DBTYPE_I1|Byte|GetByte()|  
|adUnsignedBigInt|DBTYPE_UI8|UInt64|GetValue()|  
|adUnsignedInt|DBTYPE_UI4|UInt32|GetValue()|  
|adUnsignedSmallInt|DBTYPE_UI2|UInt16|GetValue()|  
|adUnsignedTinyInt|DBTYPE_UI1|Byte|GetByte()|  
|adVariant|DBTYPE_VARIANT|Object|GetValue()|  
|adWChar|DBTYPE_WSTR|string|GetString()|  
|adUserDefined|DBTYPE_UDT|no admitido||  
|adVarNumeric|DBTYPE_VARNUMERIC|no admitido||  
  
 \*En el caso de `DBTYPE_IUNKNOWN` los `DBTYPE_IDISPATCH`tipos de OLE DB y, la referencia de objeto es una representación de cálculo de referencias del puntero.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
