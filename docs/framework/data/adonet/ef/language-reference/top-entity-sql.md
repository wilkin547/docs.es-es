---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 8b55519b7f95deb6463af4c0a6a2a53975e5b5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248974"
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)

La cláusula SELECT puede tener una subcláusula TOP opcional después del modificador opcional ALL/DISTINCT. La subcláusula TOP especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.

## <a name="syntax"></a>Sintaxis

```
[ TOP (n) ]
```

## <a name="arguments"></a>Argumentos

`n`Expresión numérica que especifica el número de filas que se van a devolver. `n` puede ser un literal numérico único o un parámetro único.

## <a name="remarks"></a>Comentarios

La expresión TOP debe ser un literal numérico único o un parámetro único. Si se utiliza un literal constante, el tipo de literal debe poderse promocionar implícitamente a Edm.Int64 (byte, int16, int32 o int64, o cualquier tipo de proveedor que se asigna a un tipo que se puede promocionar a Edm.Int64) y su valor debe ser igual o mayor que cero. De lo contrario, se producirá una excepción. Si un parámetro se utiliza como una expresión, el tipo de parámetro también debe poderse promocionar implícitamente a Edm.Int64, pero no habrá ninguna validación del valor de parámetro real durante la compilación porque los valores de parámetro se enlazan en tiempo de ejecución.

El siguiente es un ejemplo de expresión TOP constante:

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

El siguiente es un ejemplo de expresión TOP parametrizada:

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

TOP es no determinista a menos que la consulta esté ordenada. Si necesita un resultado determinista, utilice las subcláusulas [SKIP](skip-entity-sql.md) y [LIMIT](limit-entity-sql.md) en la cláusula [ORDER BY](order-by-entity-sql.md) . TOP y SKIP/LIMIT se excluyen mutuamente.

## <a name="example"></a>Ejemplo

La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa la cláusula TOP para especificar la fila superior que se va a devolver del resultado de la consulta. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:

1. Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.

2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :

    [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]

## <a name="see-also"></a>Vea también

- [SELECT](select-entity-sql.md)
- [SKIP](skip-entity-sql.md)
- [LIMIT](limit-entity-sql.md)
- [ORDER BY](order-by-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
