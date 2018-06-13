---
title: Funciones canónicas matemáticas
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 9d823eb45babca4b8f5dd717b4fb92c1984d1c8c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765105"
---
# <a name="math-canonical-functions"></a>Funciones canónicas matemáticas
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] incluye funciones canónicas matemáticas.  
  
 En la tabla siguiente se muestran las funciones canónicas matemáticas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Función|Descripción|  
|--------------|-----------------|  
|`Abs(` `value` `)`|Devuelve el valor absoluto de `value`.<br /><br /> **Argumentos**<br /><br /> Un `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, y `Decimal`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `value`.<br /><br /> **Ejemplo**<br /><br /> `Abs(-2)`|  
|`Ceiling(` `value` `)`|Devuelve el menor entero que es mayor o igual que `value`.<br /><br /> **Argumentos**<br /><br /> A `Single`, `Double`, y `Decimal`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `value`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
 [!code-sql[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]|  
|`Floor(` `value` `)`|Devuelve el mayor entero que es menor o igual que `value`.<br /><br /> **Argumentos**<br /><br /> A `Single`, `Double`, y `Decimal`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `value`.<br /><br /> **Ejemplo**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
 [!code-sql[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]|  
|`Power(` `value`, `exponent``)`|Devuelve el resultado del `value` especificado al `exponent` especificado.<br /><br /> **Argumentos**<br /><br /> `value`: Un `Int32, Int64, Double`, o `Decimal`.<br /><br /> `exponent`: Un `Int64``, Double`, o `Decimal`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `value`.<br /><br /> **Ejemplo**<br /><br /> `Power(748.58,2)`|  
|`Round(` `value` `)`|Devuelve la parte entera de `value`, redondeada al entero más próximo.<br /><br /> **Argumentos**<br /><br /> A `Single`, `Double`, y `Decimal`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `value`.<br /><br /> **Ejemplo**<br /><br /> `Round(748.58)`|  
|`Round(` `value`, `digits``)`|Devuelve `value`, redondeado a los `digits` especificados más próximos.<br /><br /> **Argumentos**<br /><br /> `value`: `Double` o `Decimal`.<br /><br /> `digits`: `Int16` o `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `value`.<br /><br /> **Ejemplo**<br /><br /> `Round(748.58,1)`|  
|`Truncate(` `value`, `digits``)`|Devuelve `value`, truncado a los `digits` especificados más próximos.<br /><br /> **Argumentos**<br /><br /> `value`: `Double` o `Decimal`.<br /><br /> `digits`: `Int16` o `Int32`.<br /><br /> **Valor devuelto**<br /><br /> Tipo de `value`.<br /><br /> **Ejemplo**<br /><br /> `Truncate(748.58,1)`|  
  
 Estas funciones devolverán `null` si se proporciona la entrada `null`.  
  
 La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client. Para obtener más información, consulte [SqlClient para Entity Framework funciones](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Vea también  
 [Funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
