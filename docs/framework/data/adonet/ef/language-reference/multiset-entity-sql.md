---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: eb676feeb168e1fb184f3869a18e138bff34211b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929340"
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
 Colección de tipo MultiSet\<T >.  
  
## <a name="remarks"></a>Comentarios  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona tres tipos de constructores: los constructores ROW, los constructores de objeto y los constructores MULTISET (o colección). Para obtener más información, vea [construir tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 El constructor MULTISET crea una instancia de un conjunto múltiple a partir de una lista de valores. Todos los valores en el constructor deben ser de un tipo compatible.  
  
 Por ejemplo, la expresión siguiente crea un conjunto múltiple de números enteros.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
> Los literales de conjunto múltiple anidados solo se admiten cuando un conjunto múltiple de ajuste tiene un único elemento MultiSet; por ejemplo, `{{1, 2, 3}}`. Cuando el conjunto múltiple contenedor tiene varios elementos (por ejemplo, `{{1, 2}, {3, 4}}`), no se admiten los literales de conjunto múltiple anidados.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador MULTISET para crear una instancia de un conjunto múltiple a partir de una lista de valores. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>Vea también

- [Tipos de constructores](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
