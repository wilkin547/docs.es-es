---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 40a5afd7eb99dba7cae8fe14ed0a45213fda94a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149952"
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
Devuelve una referencia a una instancia de entidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida que produzca una instancia de un tipo de entidad.  
  
## <a name="return-value"></a>Valor devuelto  
 Referencia a la instancia de la entidad especificada.  
  
## <a name="remarks"></a>Observaciones  
 La referencia a una entidad está compuesta de la clave de entidad y de un nombre de conjunto de entidades. Dado que diferentes conjuntos de entidades pueden basarse en el mismo tipo de entidad, una clave de entidad en particular podría aparecer en varios conjuntos de entidades. Sin embargo, una referencia a entidad siempre es única. Si la expresión de entrada representa una entidad conservada, se devolverá una referencia a esta entidad. Si la expresión de entrada no es una entidad conservada, se devolverá una referencia nula.  
  
 Si el operador de extracción de propiedad (.) se usa para tener acceso a una propiedad de una entidad, las referencias de un valor de referencia se desreferencian automáticamente.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador REF para devolver la referencia para un argumento de entidad de entrada. La misma consulta desreferencia la referencia porque se usa un operador de extracción de propiedad (.) para tener acceso a una propiedad de la entidad Product. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: Ejecutar una consulta que devuelva resultados de PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a>Consulte también

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [Clave](key-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
- [Definiciones de tipo](type-definitions-entity-sql.md)
