---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 58b21d3be8e13a0a2204a4fd6d355f734207c509
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150472"
---
# <a name="case-entity-sql"></a>CASE (Entity SQL)
Evalúa un conjunto de expresiones `Boolean` para determinar el resultado.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression
    [ ...n ]
     [
    ELSE else_result_expression
     ]
END  
```  
  
## <a name="arguments"></a>Argumentos  
 `n`  
 Es un marcador de posición que indica que se pueden usar varias cláusulas WHEN `Boolean_expression` THEN `result_expression` .  
  
 THEN `result_expression`  
 Es la expresión devuelta cuando `Boolean_expression` se evalúa como `true`. `result expression` es cualquier expresión válida.  
  
 ELSE `else_result_expression`  
 Expresión que se devuelve si ninguna operación de comparación se evalúa como `true`. Si se omite este argumento y ninguna comparación se evalúa como `true`, CASE devuelve NULL. `else_result_expression` es cualquier expresión válida. Los tipos de datos de `else_result_expression` y cualquier `result_expression` deben ser iguales o deben ser una conversión implícita.  
  
 WHEN `Boolean_expression`  
 Es la expresión `Boolean` que se evalúa cuando se usa el formato CASE buscado. `Boolean_expression` es cualquier expresión `Boolean` válida.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve el tipo de prioridad más alto del conjunto de tipos de `result_expression` y de la expresión `else_result_expression`opcional.  
  
## <a name="remarks"></a>Observaciones  
 La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión case es similar a la expresión case de Transact-SQLTransact-SQL . Puede usar la expresión case para efectuar una serie de pruebas condicionales que permitan determinar qué expresión dará el resultado apropiado. Este formato de expresión case se aplica a una serie de una o varias expresiones `Boolean` para determinar la que produce el resultado correcto.  
  
 La función CASE evalúa la `Boolean_expression` de cada cláusula WHEN en el orden especificado, y devuelve la `result_expression` de la primera `Boolean_expression` que se evalúa como `true`. Las expresiones restantes no se evalúan. Si ninguna `Boolean_expression` se evalúa como `true`, el motor de base de datos devuelve la `else_result_expression` si se especifica una cláusula ELSE, o un valor Null en otro caso.  
  
 Una instrucción CASE no puede devolver un conjunto múltiple.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` en orden con el fin de determinar el resultado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: Ejecutar una consulta que devuelva resultados de PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Consulte también

- [Entonces](then-entity-sql.md)
- [Seleccione](select-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
