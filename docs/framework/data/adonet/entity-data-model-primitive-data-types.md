---
description: 'Más información acerca de: Entity Data Model: tipos de datos primitivos'
title: 'Entity Data Model: tipos de datos primitivos'
ms.date: 03/30/2017
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
ms.openlocfilehash: bdc34f3232e78d29e6c2ce25d8f159d7f5238f2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724471"
---
# <a name="entity-data-model-primitive-data-types"></a>Entity Data Model: tipos de datos primitivos

El Entity Data Model (EDM) admite un conjunto de tipos de datos primitivos abstractos (como String, Boolean, Int32, etc.) que se usan para definir [propiedades](property.md) en un modelo conceptual. Estos tipos de datos primitivos son representantes de los tipos de datos primitivos reales compatibles con el entorno de almacenamiento o de hospedaje, como una base de datos de SQL Server o Common Language Runtime (CLR). EDM no define la semántica de las operaciones o conversiones sobre los tipos de datos primitivos; es el propio entorno de almacenamiento o de hospedaje el que lo hace. Normalmente, los tipos de datos primitivos de EDM se asignan a los tipos de datos primitivos correspondientes del entorno de almacenamiento o de hospedaje. Para obtener información sobre cómo asigna el Entity Framework tipos primitivos en el EDM a SQL Server tipos de datos, vea [SqlClient para Entity Framework](./ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
> EDM no admite colecciones de tipos de datos primitivos.  
  
 Para obtener información sobre los tipos de datos estructurados en el EDM, vea [tipo de entidad](entity-type.md) y [tipo complejo](complex-type.md).  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>Tipos de datos primitivos admitidos en Entity Data Model  

 En la tabla siguiente se enumeran los tipos de datos primitivos admitidos por EDM. En la tabla también se enumeran las [caras](facet.md) que se pueden aplicar a cada tipo de datos primitivo.  
  
|Tipo de datos primitivo|Descripción|Facetas aplicables|  
|-------------------------|-----------------|-----------------------|  
|Binary|Contiene datos binarios.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|Contiene el valor `true` o `false`.|Nullable, Default|  
|Byte|Contiene un valor entero de 8 bits sin signo.|Precision, Nullable, Default|  
|DateTime|Representa una fecha y hora.|Precision, Nullable, Default|  
|DateTimeOffset|Contiene una fecha y hora como un desplazamiento en minutos con respecto a GMT.|Precision, Nullable, Default|  
|Decimal|Contiene un valor numérico con una precisión y escala fijas.|Precision, Nullable, Default|  
|Double|Contiene un número de punto flotante con una precisión de 15 dígitos.|Precision, Nullable, Default|  
|Float|Contiene un número de punto flotante con una precisión de siete dígitos.|Precision, Nullable, Default|  
|Guid|Contiene un identificador único de 16 bytes.|Precision, Nullable, Default|  
|Int16|Contiene un valor entero de 16 bits con signo.|Precision, Nullable, Default|  
|Int32|Contiene un valor entero de 32 bits con signo.|Precision, Nullable, Default|  
|Int64|Contiene un valor entero de 64 bits con signo.|Precision, Nullable, Default|  
|SByte|Contiene un valor entero de 8 bits con signo.|Precision, Nullable, Default|  
|String|Contiene datos de caracteres.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|Hora|Contiene una hora del día.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
