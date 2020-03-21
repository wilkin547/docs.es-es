---
title: Información general sobre Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 880b81f2b6d4c4b893d28c919490f88dfb2a42e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150381"
---
# <a name="entity-sql-overview"></a>Información general sobre Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]es un lenguaje similar a SQL que le permite consultar modelos conceptuales en Entity Framework. Los modelos conceptuales representan datos [!INCLUDE[esql](../../../../../../includes/esql-md.md)] como entidades y relaciones y le permiten consultar esas entidades y relaciones en un formato que es familiar para aquellos que han utilizado SQL.  

 Entity Framework funciona con proveedores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] datos específicos del almacenamiento para traducir genéricos en consultas específicas del almacenamiento. El proveedor EntityClient proporciona una forma de ejecutar un comando de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en un modelo de entidades y devolver tipos enriquecidos de datos incluidos resultados escalares, conjuntos de resultados y gráficos de objetos. Cuando crea objetos <xref:System.Data.EntityClient.EntityCommand>, puede especificar un nombre de procedimiento guardado o el texto de una consulta asignando una cadena de consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] a su propiedad <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>. <xref:System.Data.EntityClient.EntityDataReader> muestra los resultados de ejecutar <xref:System.Data.EntityClient.EntityCommand> en un EDM. Para ejecutar el comando que devuelve el <xref:System.Data.EntityClient.EntityDataReader>, llame a <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  
  
 Además del proveedor EntityClient, Entity Framework [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permite ejecutar consultas en un modelo conceptual y devolver datos como objetos CLR fuertemente tipados que son instancias de tipos de entidad. Para obtener más información, consulte [Trabajar con objetos](../working-with-objects.md).  
  
 En esta sección se proporciona información conceptual de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
 [Diferencias entre Entity SQL y Transact-SQL](how-entity-sql-differs-from-transact-sql.md)  
  
 [Referencia rápida de Entity SQL](entity-sql-quick-reference.md)  
  
 [Sistema de tipos](type-system-entity-sql.md)  
  
 [Definiciones de tipo](type-definitions-entity-sql.md)  
  
 [Tipos de constructores](constructing-types-entity-sql.md)  
  
 [Almacenamiento en caché del plan de consulta](query-plan-caching-entity-sql.md)  
  
 [Espacios de nombres](namespaces-entity-sql.md)  
  
 [Identificadores](identifiers-entity-sql.md)  
  
 [Parámetros](parameters-entity-sql.md)  
  
 [Variables](variables-entity-sql.md)  
  
 [Expresiones no admitidas](unsupported-expressions-entity-sql.md)  
  
 [Literales](literals-entity-sql.md)  
  
 [Literales NULL e inferencia de tipos](null-literals-and-type-inference-entity-sql.md)  
  
 [Juego de caracteres de entrada](input-character-set-entity-sql.md)  
  
 [Expresiones de consulta](query-expressions-entity-sql.md)  
  
 [Funciones](functions-entity-sql.md)  
  
 [Precedencia del operador](operator-precedence-entity-sql.md)  
  
 [Paginación](paging-entity-sql.md)  
  
 [Semántica de comparación](comparison-semantics-entity-sql.md)  
  
 [Crear consultas anidadas de Entity SQL](composing-nested-entity-sql-queries.md)  
  
 [Tipos estructurados que aceptan valores NULL](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Lenguaje Entity SQL](entity-sql-language.md)
- [Especificaciones CSDL, SSDL MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
