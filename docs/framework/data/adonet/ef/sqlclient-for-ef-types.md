---
title: SqlClient para tipos de Entity Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
caps.latest.revision: "9"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 50898395dcba9e33544cae63208b352c7a6fb6f4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="sqlclient-for-entity-frameworktypes"></a>SqlClient para tipos de Entity Framework
El archivo del manifiesto del proveedor correspondiente al Proveedor de datos .NET Framework para SQL Server (SqlClient) incluye la lista de tipos primitivos del proveedor, las facetas de cada tipo, las asignaciones entre los tipos primitivos de los modelos conceptual y de almacenamiento, y las reglas de conversión y de promoción entre los tipos primitivos de los modelos conceptual y de almacenamiento.  
  
 La tabla siguiente describe los tipos de SQL Server 2008, [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], y [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] tipos de modelo de bases de datos y cómo se asignan a conceptual estos tipos. Algunos tipos nuevos introducidos en las últimas versiones de SQL Server no se admiten en las versiones más antiguas. Estos tipos se indican en la tabla siguiente.  
  
|Tipo de proveedor<br /><br /> name|Tipo de proveedor<br /><br /> atributos|`EDMSimpleType`<br /><br /> name|Facets|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|no disponible|`Edm.Boolean`|no disponible|  
|`tinyint`|no disponible|`Edm.Byte`|no disponible|  
|`smallint`|no disponible|`Edm.Int16`|no disponible|  
|`int`|no disponible|`Edm.Int32`|no disponible|  
|`bigint`|no disponible|`Edm.Int64`|no disponible|  
|`float`|no disponible|`Edm.Double`|no disponible|  
|`real`|no disponible|`Edm.Double`|no disponible|  
|`decimal`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 18<br /><br /> -Constante: False<br /><br /> Escala:<br /><br /> -Mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: False|  
|`numeric`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 18<br /><br /> -Constante: False<br /><br /> Escala:<br /><br /> -Mínimo: 0<br /><br /> -Máximo: 38<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: False|  
|`smallmoney`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Valor predeterminado: 10<br /><br /> -Constante: True<br /><br /> Escala:<br /><br /> -Valor predeterminado: 4<br /><br /> -Constante: True|  
|`money`|N/D|`Edm.Decimal`|Precisión:<br /><br /> -Valor predeterminado: 19<br /><br /> -Constante: True<br /><br /> Escala:<br /><br /> -Valor predeterminado: 4<br /><br /> -Constante: True|  
|`binary`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: False<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True|  
|`varbinary`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: False<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`varbinary(max)`<br /><br /> Nota: Este tipo no se admite en [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.Binary`|MaxLength:<br /><br /> - Default: 214748364780<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`image`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`timestamp`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Valor predeterminado: 8<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True|  
|`rowversion`|N/D|`Edm.Binary`|MaxLength:<br /><br /> -Valor predeterminado: 8<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True|  
|`smalldatetime`|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: True|  
|`datetime`|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Valor predeterminado: 3<br /><br /> -Constante: True|  
|`date`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Valor predeterminado: 0<br /><br /> -Constante: False|  
|`time`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.Time`|Precisión:<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: False|  
|`datetime2`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTime`|Precisión:<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: False|  
|`datetimeoffset`<br /><br /> Nota: Este tipo no se admite en SQL Server 2005 y SQL Server 2000.|N/D|`Edm.DateTimeOffset`|Precisión:<br /><br /> -Valor predeterminado: 7<br /><br /> -Constante: False|  
|`nvarchar`<br /><br /> Nota: Este tipo no se admite en [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.String`|MaxLength:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Valor predeterminado: 4000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`varchar`<br /><br /> Nota: Este tipo no se admite en [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|N/D|`Edm.String`|MaxLength:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`char`|N/D|`Edm.String`|MaxLength:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 8000<br /><br /> -Valor predeterminado: 8000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True|  
|`nchar`|N/D|`Edm.String`|MaxLength:<br /><br /> -Mínimo: 1<br /><br /> -Máximo: 4000<br /><br /> -Valor predeterminado: 4000<br /><br /> -Constante: False<br /><br /> Unicode:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True|  
|`varchar`(`max`)|N/D|`Edm.String`|MaxLength:<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`nvarchar`(`max`)|N/D|`Edm.String`|MaxLength:<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`ntext`|Igual comparable: False<br /><br /> Orden comparable: False|`Edm.String`|MaxLength:<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`text`|Igual comparable: False<br /><br /> Orden comparable: False|`Edm.String`|MaxLength:<br /><br /> -Valor predeterminado: 2147483647<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
|`Unique`<br /><br /> `identifier`|Igual comparable: True<br /><br /> Orden comparable: True|`Edm.Guid`|N/D|  
|`xml`|Igual comparable: False<br /><br /> Orden comparable: False|`Edm.String`|MaxLength:<br /><br /> -Valor predeterminado: 1073741823<br /><br /> -Constante: True<br /><br /> Unicode:<br /><br /> -Valor predeterminado: True<br /><br /> -Constante: True<br /><br /> FixedLength:<br /><br /> -Valor predeterminado: False<br /><br /> -Constante: True|  
  
## <a name="see-also"></a>Vea también  
 [Especificaciones CSDL, SSDL MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
