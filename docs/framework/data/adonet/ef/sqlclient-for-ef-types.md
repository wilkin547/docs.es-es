---
description: 'Más información acerca de: SqlClient para Entity Framework'
title: SqlClient para tipos de Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: 92bd557198d203229394fb3a4c2fe286e217edca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673185"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient para tipos de Entity Framework

El archivo del manifiesto del proveedor correspondiente al Proveedor de datos .NET Framework para SQL Server (SqlClient) incluye la lista de tipos primitivos del proveedor, las facetas de cada tipo, las asignaciones entre los tipos primitivos de los modelos conceptual y de almacenamiento, y las reglas de conversión y de promoción entre los tipos primitivos de los modelos conceptual y de almacenamiento.  
  
 En la tabla siguiente se describen los tipos para las bases de datos SQL Server 2008, SQL Server 2005 y SQL Server 2000 y cómo se asignan estos tipos a los tipos de modelos conceptuales. Algunos tipos nuevos introducidos en las últimas versiones de SQL Server no se admiten en las versiones más antiguas. Estos tipos se indican en la tabla siguiente.  
  
|Tipo de proveedor<br /><br /> name|Tipo de proveedor<br /><br /> attributes|`EDMSimpleType`<br /><br /> name|Facetas|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|N/D|`Edm.Boolean`|N/D|  
|`tinyint`|N/D|`Edm.Byte`|N/D|  
|`smallint`|N/D|`Edm.Int16`|N/D|  
|`int`|N/D|`Edm.Int32`|N/D|  
|`bigint`|N/D|`Edm.Int64`|N/D|  
|`float`|N/D|`Edm.Double`|N/D|  
|`real`|N/D|`Edm.Double`|N/D|  
|`decimal`|N/D|`Edm.Decimal`|Precisión<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 18<br /><br /> -Constante: false<br /><br /> Escala:<br /><br /> -Mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: false|  
|`numeric`|N/D|`Edm.Decimal`|Precisión<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 18<br /><br /> -Constante: false<br /><br /> Escala:<br /><br /> -Mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: false|  
|`smallmoney`|N/D|`Edm.Decimal`|Precisión<br /><br /> -Valor predeterminado: 10<br /><br /> -Constant: true<br /><br /> Escala:<br /><br /> -Valor predeterminado: 4<br /><br /> -Constant: true|  
|`money`|N/D|`Edm.Decimal`|Precisión<br /><br /> -Valor predeterminado: 19<br /><br /> -Constant: true<br /><br /> Escala:<br /><br /> -Valor predeterminado: 4<br /><br /> -Constant: true|  
|`binary`|N/D|`Edm.Binary`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`varbinary`|N/D|`Edm.Binary`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`varbinary(max)`<br /><br /> Nota: este tipo no se admite en SQL Server 2000.|N/D|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 214748364780<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`image`|N/D|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`timestamp`|N/D|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`rowversion`|N/D|`Edm.Binary`|Longitud<br /><br /> -Valor predeterminado: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`smalldatetime`|N/D|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 0<br /><br /> -Constant: true|  
|`datetime`|N/D|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 3<br /><br /> -Constant: true|  
|`date`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: false|  
|`time`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.Time`|Precisión<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: false|  
|`datetime2`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: false|  
|`datetimeoffset`<br /><br /> Nota: este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTimeOffset`|Precisión<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: false|  
|`nvarchar`<br /><br /> Nota: este tipo no se admite en SQL Server 2000.|N/D|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Valor predeterminado: 4000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`varchar`<br /><br /> Nota: este tipo no se admite en SQL Server 2000.|N/D|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`char`|N/D|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`nchar`|N/D|`Edm.String`|Longitud<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Valor predeterminado: 4000<br /><br /> -Constante: false<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Default: true<br /><br /> -Constant: true|  
|`varchar`(`max`)|N/D|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`nvarchar`(`max`)|N/D|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`ntext`|Igual comparable: false<br /><br /> Orden comparable: false|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`text`|Igual comparable: false<br /><br /> Orden comparable: false|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
|`Unique`<br /><br /> `identifier`|Igual comparable: true<br /><br /> Orden comparable: true|`Edm.Guid`|N/D|  
|`xml`|Igual comparable: false<br /><br /> Orden comparable: false|`Edm.String`|Longitud<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constant: true<br /><br /> Unicode:<br /><br /> -Default: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -Valor predeterminado: false<br /><br /> -Constant: true|  
  
## <a name="see-also"></a>Vea también

- [Especificaciones CSDL, SSDL MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
