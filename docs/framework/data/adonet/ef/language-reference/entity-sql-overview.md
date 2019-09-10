---
title: Información general sobre Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 8f40a34f361669d2b8d89b63b3187cae6bf705d2
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854489"
---
# <a name="entity-sql-overview"></a>Información general sobre Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]es un lenguaje similar a SQL que permite consultar modelos conceptuales en el Entity Framework. Los modelos conceptuales representan los datos como entidades y [!INCLUDE[esql](../../../../../../includes/esql-md.md)] relaciones, y permiten consultar esas entidades y relaciones en un formato conocido para los usuarios que han usado SQL.  
      
 El Entity Framework funciona con proveedores de datos específicos del almacenamiento para traducir [!INCLUDE[esql](../../../../../../includes/esql-md.md)] los genéricos en consultas específicas del almacenamiento. El proveedor EntityClient proporciona una forma de ejecutar un comando de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en un modelo de entidades y devolver tipos enriquecidos de datos incluidos resultados escalares, conjuntos de resultados y gráficos de objetos. Cuando crea objetos <xref:System.Data.EntityClient.EntityCommand>, puede especificar un nombre de procedimiento guardado o el texto de una consulta asignando una cadena de consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] a su propiedad <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>. <xref:System.Data.EntityClient.EntityDataReader> muestra los resultados de ejecutar <xref:System.Data.EntityClient.EntityCommand> en un EDM. Para ejecutar el comando que devuelve el <xref:System.Data.EntityClient.EntityDataReader>, llame a <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  
  
 Además del proveedor de EntityClient, el Entity Framework permite utilizar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para ejecutar consultas en un modelo conceptual y devolver los datos como objetos CLR fuertemente tipados que son instancias de tipos de entidad. Para obtener más información, vea [trabajar con objetos](../working-with-objects.md).  
  
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
  
 [Precedencia de operadores](operator-precedence-entity-sql.md)  
  
 [Paginación](paging-entity-sql.md)  
  
 [Semántica de comparación](comparison-semantics-entity-sql.md)  
  
 [Creación de consultas anidadas de Entity SQL](composing-nested-entity-sql-queries.md)  
  
 [Tipos estructurados que aceptan valores NULL](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Lenguaje Entity SQL](entity-sql-language.md)
- [Especificaciones CSDL, SSDL MSL](csdl-ssdl-and-msl-specifications.md)
