---
description: 'Más información acerca de: MULTISET (Entity SQL)'
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: f963638d018299e1cae7435f6dd3b7eaf855b4eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696599"
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)

Crea una instancia de un conjunto múltiple a partir de una lista de valores. Todos los valores en el constructor MULTISET deben ser de un tipo `T`compatible. No se permiten los constructores MULTISET vacíos.

## <a name="syntax"></a>Sintaxis

```sql
MULTISET ( expression [{, expression }] )
-- or
{ expression [{, expression }] }
```

## <a name="arguments"></a>Argumentos

`expression`  
 Cualquier lista válida de valores.

## <a name="return-value"></a>Valor devuelto

Colección de tipo MULTISET \<T> .

## <a name="remarks"></a>Observaciones

<!-- markdownlint-disable DOCSMD001 -->

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona tres tipos de constructores: los constructores ROW, los constructores de objeto y los constructores MULTISET (o colección). Para obtener más información, vea [construir tipos](constructing-types-entity-sql.md).

El constructor MULTISET crea una instancia de un conjunto múltiple a partir de una lista de valores. Todos los valores en el constructor deben ser de un tipo compatible.

Por ejemplo, la expresión siguiente crea un conjunto múltiple de números enteros.

`MULTISET(1, 2, 3)`

`{1, 2, 3}`

> [!NOTE]
> Los literales de conjunto múltiple anidados solo se admiten cuando un conjunto múltiple de ajuste tiene un único elemento MultiSet; por ejemplo, `{{1, 2, 3}}` . Cuando el conjunto múltiple contenedor tiene varios elementos (por ejemplo, `{{1, 2}, {3, 4}}`), no se admiten los literales de conjunto múltiple anidados.

## <a name="example"></a>Ejemplo

La consulta de Entity SQL siguiente utiliza el operador MULTISET para crear una instancia de un conjunto múltiple a partir de una lista de valores. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:

1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :

[!code-sql[DP EntityServices Concepts#MULTISET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiset)]

## <a name="see-also"></a>Vea también

- [Tipos de constructores](constructing-types-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
