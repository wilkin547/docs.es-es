---
title: SqlClient para tipos de Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: af3a4eea08dd3f4e1a134fcb66d92bc4a3b077c7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248378"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient para tipos de Entity Framework
El archivo del manifiesto del proveedor correspondiente al Proveedor de datos .NET Framework para SQL Server (SqlClient) incluye la lista de tipos primitivos del proveedor, las facetas de cada tipo, las asignaciones entre los tipos primitivos de los modelos conceptual y de almacenamiento, y las reglas de conversión y de promoción entre los tipos primitivos de los modelos conceptual y de almacenamiento.  
  
 En la tabla siguiente se describen los tipos para las bases de datos SQL Server 2008, SQL Server 2005 y SQL Server 2000 y cómo se asignan estos tipos a los tipos de modelos conceptuales. Algunos tipos nuevos introducidos en las últimas versiones de SQL Server no se admiten en las versiones más antiguas. Estos tipos se indican en la tabla siguiente.  
  
|Tipo de proveedor<br /><br /> name|Tipo de proveedor<br /><br /> atributos|`EDMSimpleType`<br /><br /> Nombre|Facets|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|N/D|`Edm.Boolean`|N/D|  
|`tinyint`|N/D|`Edm.Byte`|N/D|  
|`smallint`|N/D|`Edm.Int16`|N/D|  
|`int`|N/D|`Edm.Int32`|N/D|  
|`bigint`|N/D|`Edm.Int64`|N/D|  
|`float`|N/D|`Edm.Double`|N/D|  
|`real`|N/D|`Edm.Double`|N/D|  
|`decimal`|N/D|`Edm.Decimal`|Precisión<br /><br /> Cantidad 1<br /><br /> Máximo 38<br /><br /> Predeterminada 18<br /><br /> Constante False<br /><br /> Escala<br /><br /> Cantidad 0<br /><br /> Máximo 38<br /><br /> Predeterminada 0<br /><br /> Constante False|  
|`numeric`|N/D|`Edm.Decimal`|Precisión<br /><br /> Cantidad 1<br /><br /> Máximo 38<br /><br /> Predeterminada 18<br /><br /> Constante False<br /><br /> Escala<br /><br /> Cantidad 0<br /><br /> Máximo 38<br /><br /> Predeterminada 0<br /><br /> Constante False|  
|`smallmoney`|N/D|`Edm.Decimal`|Precisión<br /><br /> Predeterminada 10<br /><br /> Constante True<br /><br /> Escala<br /><br /> Predeterminada 4<br /><br /> Constante True|  
|`money`|N/D|`Edm.Decimal`|Precisión<br /><br /> Predeterminada 19<br /><br /> Constante True<br /><br /> Escala<br /><br /> Predeterminada 4<br /><br /> Constante True|  
|`binary`|N/D|`Edm.Binary`|Longitud<br /><br /> Cantidad 1<br /><br /> Máximo 8000<br /><br /> Predeterminada 8000<br /><br /> Constante False<br /><br /> FixedLength<br /><br /> Predeterminada True<br /><br /> Constante True|  
|`varbinary`|N/D|`Edm.Binary`|Longitud<br /><br /> Cantidad 1<br /><br /> Máximo 8000<br /><br /> Predeterminada 8000<br /><br /> Constante False<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`varbinary(max)`<br /><br /> Nota: Este tipo no se admite en SQL Server 2000.|N/D|`Edm.Binary`|Longitud<br /><br /> Predeterminada 214748364780<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`image`|N/D|`Edm.Binary`|Longitud<br /><br /> Predeterminada 2147483647<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`timestamp`|N/D|`Edm.Binary`|Longitud<br /><br /> Predeterminada 8<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada True<br /><br /> Constante True|  
|`rowversion`|N/D|`Edm.Binary`|Longitud<br /><br /> Predeterminada 8<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada True<br /><br /> Constante True|  
|`smalldatetime`|N/D|`Edm.DateTime`|Precisión<br /><br /> Predeterminada 0<br /><br /> Constante True|  
|`datetime`|N/D|`Edm.DateTime`|Precisión<br /><br /> Predeterminada 3<br /><br /> Constante True|  
|`date`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión<br /><br /> Predeterminada 0<br /><br /> Constante False|  
|`time`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.Time`|Precisión<br /><br /> Predeterminada 7<br /><br /> Constante False|  
|`datetime2`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión<br /><br /> Predeterminada 7<br /><br /> Constante False|  
|`datetimeoffset`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTimeOffset`|Precisión<br /><br /> Predeterminada 7<br /><br /> Constante False|  
|`nvarchar`<br /><br /> Nota: Este tipo no se admite en SQL Server 2000.|N/D|`Edm.String`|Longitud<br /><br /> Cantidad 1<br /><br /> Máximo 4000<br /><br /> Predeterminada 4000<br /><br /> Constante False<br /><br /> Unicode:<br /><br /> Predeterminada True<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`varchar`<br /><br /> Nota: Este tipo no se admite en SQL Server 2000.|N/D|`Edm.String`|Longitud<br /><br /> Cantidad 1<br /><br /> Máximo 8000<br /><br /> Predeterminada 8000<br /><br /> Constante False<br /><br /> Unicode:<br /><br /> Predeterminada False<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`char`|N/D|`Edm.String`|Longitud<br /><br /> Cantidad 1<br /><br /> Máximo 8000<br /><br /> Predeterminada 8000<br /><br /> Constante False<br /><br /> Unicode:<br /><br /> Predeterminada False<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada True<br /><br /> Constante True|  
|`nchar`|N/D|`Edm.String`|Longitud<br /><br /> Cantidad 1<br /><br /> Máximo 4000<br /><br /> Predeterminada 4000<br /><br /> Constante False<br /><br /> Unicode:<br /><br /> Predeterminada True<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada True<br /><br /> Constante True|  
|`varchar`(`max`)|N/D|`Edm.String`|Longitud<br /><br /> Predeterminada 2147483647<br /><br /> Constante True<br /><br /> Unicode:<br /><br /> Predeterminada False<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`nvarchar`(`max`)|N/D|`Edm.String`|Longitud<br /><br /> Predeterminada 1073741823<br /><br /> Constante True<br /><br /> Unicode:<br /><br /> Predeterminada True<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`ntext`|Igual comparable: False<br /><br /> Orden comparable: False|`Edm.String`|Longitud<br /><br /> Predeterminada 1073741823<br /><br /> Constante True<br /><br /> Unicode:<br /><br /> Predeterminada False<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`text`|Igual comparable: False<br /><br /> Orden comparable: False|`Edm.String`|Longitud<br /><br /> Predeterminada 2147483647<br /><br /> Constante True<br /><br /> Unicode:<br /><br /> Predeterminada False<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
|`Unique`<br /><br /> `identifier`|Igual comparable: True<br /><br /> Orden comparable: True|`Edm.Guid`|N/D|  
|`xml`|Igual comparable: False<br /><br /> Orden comparable: False|`Edm.String`|Longitud<br /><br /> Predeterminada 1073741823<br /><br /> Constante True<br /><br /> Unicode:<br /><br /> Predeterminada True<br /><br /> Constante True<br /><br /> FixedLength<br /><br /> Predeterminada False<br /><br /> Constante True|  
  
## <a name="see-also"></a>Vea también

- [Especificaciones CSDL, SSDL MSL](./language-reference/csdl-ssdl-and-msl-specifications.md)
