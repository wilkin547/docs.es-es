---
description: 'Más información sobre: funciones canónicas de agregado'
title: Funciones canónicas de agregado
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: e26888ac15553a592f7d2cb9b1a0941161115615
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697301"
---
# <a name="aggregate-canonical-functions"></a>Funciones canónicas de agregado

Los agregados son expresiones que reducen una serie de valores de entrada a un único valor, por ejemplo. Los agregados suelen usarse junto con la cláusula GROUP BY de la expresión SELECT y hay restricciones con respecto a dónde se pueden usar.

## <a name="aggregate-entity-sql-canonical-functions"></a>Funciones canónicas de agregado Entity SQL

A continuación se muestran las funciones canónicas Entity SQL agregadas.

### <a name="avgexpression"></a>Avg(expresión)

Devuelve el promedio de los valores no NULL.

**Argumentos**

`Int32`,, `Int64` `Double` Y `Decimal` .

**Valor devuelto**

El tipo de `expression` , o `null` si todos los valores de entrada son `null` valores.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a>BigCount(expresión)

Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.

**Argumentos**

Cualquier tipo.

**Valor devuelto**

Una clase `Int64`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a>Count(expresión)

Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.

**Argumentos**

Cualquier tipo.

**Valor devuelto**

Una clase `Int32`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a>Max(expresión)

Devuelve el máximo de los valores no NULL.

**Argumentos**

Valor de tipo `Byte``Int16``Int32``Int64``Byte``Single``Double``Decimal``DateTime``DateTimeOffset``Time``String`.

**Valor devuelto**

El tipo de `expression` , o `null` si todos los valores de entrada son `null` valores.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a>Min(expresión)

Devuelve el mínimo de los valores no NULL.

**Argumentos**

Valor de tipo `Byte``Int16``Int32``Int64``Byte``Single``Double``Decimal``DateTime``DateTimeOffset``Time``String`.

**Valor devuelto**

El tipo de `expression` , o `null` si todos los valores de entrada son `null` valores.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a>StDev(expresión)

Devuelve la desviación estándar de los valores no NULL.

**Argumentos**

Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.

**Valor devuelto**

Objeto `Double`. `Null` si los valores de entrada son `null`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a>StDevP(expresión)

Devuelve la desviación estándar de la población para todos los valores.

**Argumentos**

Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.

**Valor devuelto**

`Double`O `null` si todos los valores de entrada son `null` valores.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a>Sum(expresión)

Devuelve la suma de los valores no NULL.

**Argumentos**

Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.

**Valor devuelto**

`Double`O `null` si todos los valores de entrada son `null` valores.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a>Var(expresión)

Devuelve la varianza de todos los valores no nulos.

**Argumentos**

Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.

**Valor devuelto**

`Double`O `null` si todos los valores de entrada son `null` valores.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a>VarP(expresión)

Devuelve la varianza de la población para todos los valores no nulos.

**Argumentos**

Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.

**Valor devuelto**

`Double`O `null` si todos los valores de entrada son `null` valores.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client. Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).

## <a name="collection-based-aggregates"></a>Agregados basados en una colección

Los agregados basados en una colección (funciones de colección) operan en las colecciones y devuelven un valor. Por ejemplo, si ORDERs es una colección de todos los pedidos, puede calcular la fecha de envío más temprana con la expresión siguiente:

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

Las expresiones que se encuentran dentro de agregados basados en una colección se evalúan dentro del ámbito actual de la resolución de nombres.

## <a name="group-based-aggregates"></a>Agregados basados en grupos

Los agregados basados en un grupo se calculan sobre un grupo según define la cláusula GROUP BY. Para cada grupo del resultado, se calcula un agregado diferente utilizando los elementos de cada grupo como entrada del cálculo del agregado. Cuando se usa una cláusula GROUP-BY en una expresión SELECT, solo se pueden presentar en la cláusula ORDER-BY o de la proyección los nombres de la expresión de agrupamiento, los agregados o las expresiones constantes.

En el ejemplo siguiente se calcula la cantidad promedio pedida de cada producto:

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

Es posible tener un agregado basado en un grupo sin una cláusula Group-by explícita en la expresión SELECT. En este caso, todos los elementos se tratan como un solo grupo. Esto es equivalente a especificar una agrupación basada en una constante. Tome como ejemplo la siguiente expresión:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

Es equivalente a la siguiente:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

Las expresiones que se encuentran dentro del agregado basado en un grupo se evalúan dentro del ámbito de resolución de nombres que sería visible para la expresión de la cláusula WHERE.

Como en Transact-SQL, los agregados basados en grupos también pueden especificar un modificador ALL o DISTINCt. Si se especifica el modificador DISTINCT, los duplicados se eliminan de la colección de entrada del agregado, antes de calcularlo. Si se especifica el modificador ALL o no se especifica ningún modificador, no se lleva a cabo la eliminación de los duplicados.

## <a name="see-also"></a>Vea también

- [Funciones canónicas](canonical-functions.md)
