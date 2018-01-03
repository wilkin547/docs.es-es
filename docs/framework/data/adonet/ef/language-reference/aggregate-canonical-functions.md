---
title: "Funciones canónicas de agregado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 071c6b41d24465a599afa87a296c0797e8ca6ed9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="aggregate-canonical-functions"></a>Funciones canónicas de agregado

Los agregados son expresiones que reducen una serie de valores de entrada a un único valor, por ejemplo. Los agregados suelen usarse junto con la cláusula GROUP BY de la expresión SELECT y hay restricciones con respecto a dónde se pueden usar.

En la tabla siguiente se muestran las funciones canónicas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] de agregado.

| Función | Descripción |
| -------- | ----------- |
| `Avg(expression)` | Devuelve el promedio de los valores no NULL.<br><br>**Argumentos**<br><br>Un `Int32`, `Int64`, `Double`, y `Decimal`.<br><br>**Valor devuelto**<br><br>Tipo de `expression`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)][!code-sql[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)] |
| `BigCount(expression)` | Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.<br><br>**Argumentos**<br><br>Cualquier tipo.<br><br>**Valor devuelto**<br><br>Una clase `Int64`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)][!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)] |
| `Count(expression)` | Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.<br><br>**Argumentos**<br><br>Cualquier tipo.<br><br>**Valor devuelto**<br><br>Una clase `Int32`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)][!code-sql[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)] |
| `Max(expression)` | Devuelve el máximo de los valores no NULL.<br><br>**Argumentos**<br><br>Valor de tipo `Int16``Byte``Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , .<br><br>**Valor devuelto**<br><br>Tipo de `expression`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)][!code-sql[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)] |
| `Min(expression)` | Devuelve el mínimo de los valores no NULL.<br><br>**Argumentos**<br><br>Valor de tipo `Int16``Byte``Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , .<br><br>**Valor devuelto**<br><br>Tipo de `expression`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)][!code-sql[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)] |
| `StDev(expression)` | Devuelve la desviación estándar de los valores no NULL.<br><br>**Argumentos**<br><br>Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.<br><br>**Valor devuelto**<br><br>Objeto `Double`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)][!code-sql[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)] |
| `StDevP(expression)` | Devuelve la desviación estándar de la población para todos los valores.<br><br>**Argumentos**<br><br>Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.<br><br>**Valor devuelto**<br><br>Objeto `Double`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)][!code-sql[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)] |
| `Sum(expression)` | Devuelve la suma de los valores no NULL.<br><br>**Argumentos**<br><br>Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.<br><br>**Valor devuelto**<br><br>Objeto `Double`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)][!code-sql[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)] |
| `Var(expression)` | Devuelve la varianza de todos los valores no nulos.<br><br>**Argumentos**<br><br>Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.<br><br>**Valor devuelto**<br><br>Objeto `Double`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)][!code-sql[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)] |
| `VarP(expression)` | Devuelve la varianza de la población para todos los valores no nulos.<br><br>**Argumentos**<br><br>Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.<br><br>**Valor devuelto**<br><br>Objeto `Double`. `Null` si los valores de entrada son `null`.<br><br>**En el ejemplo se** [!code-csharp [DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)][!code-sql[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] |

La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client. Para obtener más información, consulte [SqlClient para Entity Framework funciones](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).

## <a name="collection-based-aggregates"></a>Agregados basados en colecciones

Los agregados basados en una colección (funciones de colección) operan en las colecciones y devuelven un valor. Por ejemplo si ORDERS es una colección de todos los pedidos, puede calcular la fecha de envío más reciente con la siguiente expresión:

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

Las expresiones que se encuentran dentro de agregados basados en una colección se evalúan dentro del ámbito de resolución de nombres actual

## <a name="group-based-aggregates"></a>Agregados basados en grupo

Los agregados basados en un grupo se calculan sobre un grupo según define la cláusula GROUP BY. Para cada grupo del resultado, se calcula un agregado diferente utilizando los elementos de cada grupo como entrada del cálculo del agregado. Cuando se usa una cláusula GROUP-BY en una expresión SELECT, solo se pueden presentar en la cláusula ORDER-BY o de la proyección los nombres de la expresión de agrupamiento, los agregados o las expresiones constantes.

En el ejemplo siguiente se calcula la cantidad promedio pedida de cada producto:

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol 
  group by ol.Product as p
```

Es posible tener un agregado basado en el grupo sin una cláusula group-by explícita en la expresión SELECT. En este caso, todos los elementos se tratan como un único grupo. Esto es equivalente a especificar una agrupación basada en una constante. Tome como ejemplo la siguiente expresión:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

Es equivalente a la siguiente:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

Las expresiones que se encuentran dentro del agregado basado en un grupo se evalúan dentro del ámbito de resolución de nombres que sería visible para la expresión de la cláusula WHERE.

Como en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], los agregados basados en el grupo también pueden especificar un ALL o modificador DISTINCT. Si se especifica el modificador DISTINCT, los duplicados se eliminan de la colección de entrada del agregado, antes de calcularlo. Si se especifica el modificador ALL o no se especifica ningún modificador, no se lleva a cabo la eliminación de los duplicados.  

## <a name="see-also"></a>Vea también

[Funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
