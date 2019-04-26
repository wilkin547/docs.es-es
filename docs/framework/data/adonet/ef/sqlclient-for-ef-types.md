---
title: SqlClient para tipos de Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: eb12bde1e319fde5adf20ad6cd54f8776aeda31d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879169"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient para tipos de Entity Framework
El archivo del manifiesto del proveedor correspondiente al Proveedor de datos .NET Framework para SQL Server (SqlClient) incluye la lista de tipos primitivos del proveedor, las facetas de cada tipo, las asignaciones entre los tipos primitivos de los modelos conceptual y de almacenamiento, y las reglas de conversión y de promoción entre los tipos primitivos de los modelos conceptual y de almacenamiento.  
  
 En la tabla siguiente describe los tipos de SQL Server 2008, [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], y [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] las bases de datos y cómo estos tipos se asignan a conceptual tipos del modelo. Algunos tipos nuevos introducidos en las últimas versiones de SQL Server no se admiten en las versiones más antiguas. Estos tipos se indican en la tabla siguiente.  
  
|Tipo de proveedor<br /><br /> name|Tipo de proveedor<br /><br /> atributos|`EDMSimpleType`<br /><br /> name|Facets|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|N/D|`Edm.Boolean`|N/D|  
|`tinyint`|N/D|`Edm.Byte`|N/D|  
|`smallint`|N/D|`Edm.Int16`|N/D|  
|`int`|N/D|`Edm.Int32`|N/D|  
|`bigint`|N/D|`Edm.Int64`|N/D|  
|`float`|N/D|`Edm.Double`|N/D|  
|`real`|N/D|`Edm.Double`|N/D|  
|`decimal`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Default: 18<br /><br /> -Constante: False<br /><br /> Escala:<br /><br /> -Como mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Default: 0<br /><br /> -Constante: False|  
|`numeric`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Default: 18<br /><br /> -Constante: False<br /><br /> Escala:<br /><br /> -Como mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Default: 0<br /><br /> -Constante: False|  
|`smallmoney`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Default: 10<br /><br /> -Constante: True<br /><br /> Escala:<br /><br /> -Default: 4<br /><br /> -Constante: True|  
|`money`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Default: 19<br /><br /> -Constante: True<br /><br /> Escala:<br /><br /> -Default: 4<br /><br /> -Constante: True|  
|`binary`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Default: 8000<br /><br /> -Constante: False<br /><br /> FixedLength:<br /><br /> -Default: True<br /><br /> -Constante: True|  
|`varbinary`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Default: 8000<br /><br /> -Constante: False<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`varbinary(max)`<br /><br /> Nota: Este tipo no se admite en [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Default: 214748364780<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`image`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Default: 2147483647<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`timestamp`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Default: 8<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: True<br /><br /> -Constante: True|  
|`rowversion`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Default: 8<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: True<br /><br /> -Constante: True|  
|`smalldatetime`|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Default: 0<br /><br /> -Constante: True|  
|`datetime`|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Default: 3<br /><br /> -Constante: True|  
|`date`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Default: 0<br /><br /> -Constante: False|  
|`time`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.Time`|Precisión:<br /><br /> -Default: 7<br /><br /> -Constante: False|  
|`datetime2`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Default: 7<br /><br /> -Constante: False|  
|`datetimeoffset`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTimeOffset`|Precisión:<br /><br /> -Default: 7<br /><br /> -Constante: False|  
|`nvarchar`<br /><br /> Nota: Este tipo no se admite en [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.String`|MaxLength:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Default: 4000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Default: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`varchar`<br /><br /> Nota: Este tipo no se admite en [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.String`|MaxLength:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Default: 8000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Default: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`char`|N/D|`Edm.String`|MaxLength:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Default: 8000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Default: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: True<br /><br /> -Constante: True|  
|`nchar`|N/D|`Edm.String`|MaxLength:<br /><br /> -Como mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Default: 4000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Default: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: True<br /><br /> -Constante: True|  
|`varchar`(`max`)|N/D|`Edm.String`|MaxLength:<br /><br /> -Default: 2147483647<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Default: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`nvarchar`(`max`)|N/D|`Edm.String`|MaxLength:<br /><br /> -Default: 1073741823<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Default: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`ntext`|Igual comparable: False<br /><br /> Comparable en orden: False|`Edm.String`|MaxLength:<br /><br /> -Default: 1073741823<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Default: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`text`|Igual comparable: False<br /><br /> Comparable en orden: False|`Edm.String`|MaxLength:<br /><br /> -Default: 2147483647<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Default: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
|`Unique`<br /><br /> `identifier`|Igual comparable: True<br /><br /> Comparable en orden: True|`Edm.Guid`|N/D|  
|`xml`|Igual comparable: False<br /><br /> Comparable en orden: False|`Edm.String`|MaxLength:<br /><br /> -Default: 1073741823<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Default: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Default: False<br /><br /> -Constante: True|  
  
## <a name="see-also"></a>Vea también

- [Especificaciones CSDL, SSDL MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
