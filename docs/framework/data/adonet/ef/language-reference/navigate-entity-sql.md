---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 2c6c2ae4c593da1d5fe8cdf3015eb0e31e4b12b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249937"
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Navega por la relación establecida entre entidades.

## <a name="syntax"></a>Sintaxis

```
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>Argumentos

`instance-expression`Instancia de una entidad.

`relationship-type`El nombre de tipo de la relación, del archivo de lenguaje de definición de esquemas conceptuales (CSDL). Se califica como espacio \<de nombres >\<. `relationship-type` nombre del tipo de relación >.

`to`Final de la relación.

`from`Principio de la relación.

## <a name="return-value"></a>Valor devuelto

Si la cardinalidad del extremo final es 1, el valor devuelto será `Ref<T>`. Si la cardinalidad del extremo final es n, el valor devuelto será `Collection<Ref<T>>`.

## <a name="remarks"></a>Comentarios

Las relaciones son construcciones de primera clase en el Entity Data Model (EDM). Se pueden establecer relaciones entre dos o más tipos de entidad y los usuarios pueden navegar en la relación de un extremo (entidad) al otro. `from` y `to` son condicionalmente opcionales cuando no hay ambigüedad en la resolución de nombres dentro de la relación.

NAVIGATE es válido en espacios O y C.

La forma general de una estructura de navegación es la siguiente:

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Por ejemplo:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Donde OrderCustomer es el valor de `relationship`, y Customer y Order son los valores de `to-end` (cliente) y `from-end` (pedido) de la relación. Si OrderCustomer era una relación de n:1, el tipo de resultado de la expresión Navigate\<es Ref Customer >.

Lo forma más simple de esta expresión es la siguiente:

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Del mismo modo, en una consulta de la forma siguiente, la expresión Navigate produciría una\<colección < orden de referencia > >.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

El valor de instance-expression debe ser de tipo entidad/referencia.

## <a name="example"></a>Ejemplo

La consulta de Entity SQL siguiente utiliza el operador NAVIGATE para navegar por la relación establecida entre los tipos de entidad Address y SalesOrderHeader. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:

1. Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.

2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :

 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]

## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Procedimientos: Navegar por las relaciones con el operador Navigate](navigate-entity-sql.md)
