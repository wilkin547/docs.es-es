---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: d4293b8e027f7f0f7eabac7ad9c8a9852ddd3a80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178482"
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Crea una instancia de un conjunto múltiple a partir de una lista de valores. Todos los valores en el constructor MULTISET deben ser de un tipo `T`compatible. No se permiten los constructores MULTISET vacíos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier lista válida de valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Una colección de tipo MULTISET\<T >.  
  
## <a name="remarks"></a>Comentarios  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona tres tipos de constructores: row, constructores de objetos y los constructores multiset (o colección). Para obtener más información, consulte [construir tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 El constructor MULTISET crea una instancia de un conjunto múltiple a partir de una lista de valores. Todos los valores en el constructor deben ser de un tipo compatible.  
  
 Por ejemplo, la expresión siguiente crea un conjunto múltiple de números enteros.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  Solo se admiten los literales de conjunto múltiple anidados cuando un conjunto múltiple contenedor tiene un único elemento de conjunto múltiple; Por ejemplo, `{{1, 2, 3}}`. Cuando el conjunto múltiple contenedor tiene varios elementos (por ejemplo, `{{1, 2}, {3, 4}}`), no se admiten los literales de conjunto múltiple anidados.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador MULTISET para crear una instancia de un conjunto múltiple a partir de una lista de valores. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>Vea también

- [Tipos de constructores](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
