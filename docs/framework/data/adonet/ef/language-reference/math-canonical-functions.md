---
title: Funciones canónicas matemáticas
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228775"
---
# <a name="math-canonical-functions"></a>Funciones canónicas matemáticas

Entity SQL incluye las siguientes funciones canónicas matemáticas:
  
## <a name="absvalue"></a>Abs(valor)

Devuelve el valor absoluto de `value`.

**Argumentos**

Un `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, y `Decimal`.

**Valor devuelto**

Tipo de `value`.

**Ejemplo**

`Abs(-2)`

## <a name="ceilingvalue"></a>Ceiling(valor)

Devuelve el menor entero que es mayor o igual que `value`.

**Argumentos**

Un `Single`, `Double`, y `Decimal`.

**Valor devuelto**

Tipo de `value`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a>Floor(valor)

Devuelve el mayor entero que es menor o igual que `value`.

**Argumentos**

Un `Single`, `Double`, y `Decimal`.

**Valor devuelto**

Tipo de `value`.

**Ejemplo**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a>Power(valor, exponente)

Devuelve el resultado del `value` especificado al `exponent` especificado.

**Argumentos**

|  |  |
|--|--|
|`value` | Un `Int32, Int64, Double`, o `Decimal`. |
|`exponent` | Un `Int64`, `Double`, o `Decimal`. |

**Valor devuelto**

Tipo de `value`.

**Ejemplo**

`Power(748.58,2)`

## <a name="roundvalue"></a>Round(valor)

Devuelve la parte entera de `value`, redondeada al entero más próximo.

**Argumentos**

Un `Single`, `Double`, y `Decimal`.

**Valor devuelto**

Tipo de `value`.

**Ejemplo**

`Round(748.58)`

## <a name="roundvalue-digits"></a>Round(valor, dígitos)

Devuelve `value`, redondeado a los `digits` especificados más próximos.

**Argumentos**

|  |  |
|--|--|
|`value`|`Double` o `Decimal`.|
|`digits`|`Int16` o `Int32`.|

**Valor devuelto**

Tipo de `value`.

**Ejemplo**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a>Truncate(valor, dígitos)

Devuelve `value`, truncado a los `digits` especificados más próximos.

**Argumentos**

|  |  |
|--|--|
|`value`|`Double` o `Decimal`.|
|`digits`|`Int16` o `Int32`.|

**Valor devuelto**

Tipo de `value`.

**Ejemplo**

`Truncate(748.58,1)`  
  
 Estas funciones devolverán `null` si se proporciona la entrada `null`.  
  
 La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client. Para obtener más información, consulte [SqlClient para las funciones de Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Vea también

- [Funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
