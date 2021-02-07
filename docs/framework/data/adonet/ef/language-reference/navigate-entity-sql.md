---
description: 'Más información acerca de: navegar (Entity SQL)'
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 7fa39a988429fe0a658b01078d2369ad4767f4a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696508"
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Navega por la relación establecida entre entidades.

## <a name="syntax"></a>Sintaxis

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>Argumentos

`instance-expression` Instancia de una entidad.

`relationship-type` El nombre de tipo de la relación, del archivo de lenguaje de definición de esquemas conceptuales (CSDL). `relationship-type`Se califica como \<namespace> . \<relationship type name> .

`to` Final de la relación.

`from` Principio de la relación.

## <a name="return-value"></a>Valor devuelto

Si la cardinalidad del extremo final es 1, el valor devuelto será `Ref<T>`. Si la cardinalidad del extremo final es n, el valor devuelto será `Collection<Ref<T>>`.

## <a name="remarks"></a>Observaciones

Las relaciones son construcciones de primera clase en el Entity Data Model (EDM). Se pueden establecer relaciones entre dos o más tipos de entidad y los usuarios pueden navegar en la relación de un extremo (entidad) al otro. `from` y `to` son condicionalmente opcionales cuando no hay ambigüedad en la resolución de nombres dentro de la relación.

NAVIGATE es válido en espacios O y C.

La forma general de una estructura de navegación es la siguiente:

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Por ejemplo:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Donde OrderCustomer es el valor de `relationship`, y Customer y Order son los valores de `to-end` (cliente) y `from-end` (pedido) de la relación. Si OrderCustomer era una relación de n:1, el tipo de resultado de la expresión Navigate es Ref \<Customer> .

Lo forma más simple de esta expresión es la siguiente:

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Del mismo modo, en una consulta de la forma siguiente, la expresión Navigate produciría una colección<referencia \<Order>>.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

El valor de instance-expression debe ser de tipo entidad/referencia.

## <a name="example"></a>Ejemplo

La consulta de Entity SQL siguiente utiliza el operador NAVIGATE para navegar por la relación establecida entre los tipos de entidad Address y SalesOrderHeader. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:

1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Cómo navegar por las relaciones con el operador Navigate](navigate-entity-sql.md)
