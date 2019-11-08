---
title: SqlClient para tipos de Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: d132583bba2520d37693be6c4b085cfa514003e0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737846"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient para tipos de Entity Framework
El archivo del manifiesto del proveedor correspondiente al Proveedor de datos .NET Framework para SQL Server (SqlClient) incluye la lista de tipos primitivos del proveedor, las facetas de cada tipo, las asignaciones entre los tipos primitivos de los modelos conceptual y de almacenamiento, y las reglas de conversión y de promoción entre los tipos primitivos de los modelos conceptual y de almacenamiento.  
  
 En la tabla siguiente se describen los tipos para las bases de datos SQL Server 2008, SQL Server 2005 y SQL Server 2000 y cómo se asignan estos tipos a los tipos de modelos conceptuales. Algunos tipos nuevos introducidos en las últimas versiones de SQL Server no se admiten en las versiones más antiguas. Estos tipos se indican en la tabla siguiente.  
  
|Tipo de proveedor<br /><br /> name|Tipo de proveedor<br /><br /> atributos|`EDMSimpleType`<br /><br /> name|Facets|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|no disponible|`Edm.Boolean`|no disponible|  
|`tinyint`|no disponible|`Edm.Byte`|no disponible|  
|`smallint`|no disponible|`Edm.Int16`|no disponible|  
|`int`|no disponible|`Edm.Int32`|no disponible|  
|`bigint`|no disponible|`Edm.Int64`|no disponible|  
|`float`|no disponible|`Edm.Double`|no disponible|  
|`real`|no disponible|`Edm.Double`|no disponible|  
|`decimal`|no disponible|`Edm.Decimal`|Precisión<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 18<br /><br /> -Constante: false<br /><br /> Escala<br /><br /> -Mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: false|  
|`numeric`|no disponible|`Edm.Decimal`|Precisión<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 18<br /><br /> -Constante: false<br /><br /> Escala<br /><br /> -Mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: false|  
|`smallmoney`|no disponible|`Edm.Decimal`|Precisión<br /><br /> -Valor predeterminado: 10<br /><br /> -Constant: true<br /><br /> Escala<br /><br /> -Valor predeterminado: 4<br /><br /> -Constant: true|  
|`money`|no disponible|`Edm.Decimal`|Precisión<br /><br /> -Valor predeterminado: 19<br /><br /> -Constant: true<br /><br /> Escala<br /><br /> -Valor predeterminado: 4<br /><br /> -Constant: true|  
|`binary`|no disponible|`Edm.Binary`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`varbinary`|no disponible|`Edm.Binary`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`varbinary(max)`<br /><br /> Nota: este tipo no se admite en SQL Server 2000.|no disponible|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 214748364780<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`image`|no disponible|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`timestamp`|no disponible|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`rowversion`|no disponible|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`smalldatetime`|no disponible|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 0<br /><br /> -Constant: true|  
|`datetime`|no disponible|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 3<br /><br /> -Constant: true|  
|`date`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|no disponible|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: false|  
|`time`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|no disponible|`Edm.Time`|Precisión<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: false|  
|`datetime2`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|no disponible|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: false|  
|`datetimeoffset`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|no disponible|`Edm.DateTimeOffset`|Precisión<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: false|  
|`nvarchar`<br /><br /> Nota: este tipo no se admite en SQL Server 2000.|no disponible|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Valor predeterminado: 4000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`varchar`<br /><br /> Nota: este tipo no se admite en SQL Server 2000.|no disponible|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`char`|no disponible|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`nchar`|no disponible|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Valor predeterminado: 4000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`varchar`(`max`)|no disponible|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`nvarchar`(`max`)|no disponible|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`ntext`|Igual comparable: false<br /><br /> Orden comparable: false|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`text`|Igual comparable: false<br /><br /> Orden comparable: false|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`Unique`<br /><br /> `identifier`|Igual comparable: true<br /><br /> Orden comparable: true|`Edm.Guid`|no disponible|  
|`xml`|Igual comparable: false<br /><br /> Orden comparable: false|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
  
## <a name="see-also"></a>Vea también

- [Especificaciones CSDL, SSDL MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
