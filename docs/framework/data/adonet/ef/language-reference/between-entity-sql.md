---
description: 'Más información acerca de: entre (Entity SQL)'
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 35ac16e94f2e55f6a0f76591daf0f91f9708aa53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697119"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)

Determina si el resultado de una expresión es un valor incluido en un intervalo especificado. La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión between tiene la misma funcionalidad que la expresión Transact-SQL between.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión válida que se va a probar en el intervalo definido por `begin_expression` y `end_expression`. `expression` debe ser del mismo tipo que `begin_expression` y `end_expression`.  
  
 `begin_expression`  
 Cualquier expresión válida. `begin_expression` debe ser del mismo tipo que `expression` y `end_expression`. `begin_expression` debe ser menor que `end_expression`; de lo contrario, el valor devuelto se negará.  
  
 `end_expression`  
 Cualquier expresión válida. `end_expression` debe ser del mismo tipo que `expression` y `begin_expression`.  
  
 NOT  
 Especifica que el resultado de BETWEEN se niega.  
  
 y  
 Actúa como un marcador de posición que indica que `expression` debe estar dentro del intervalo indicado por `begin_expression` y `end_expression`.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` si `expression` está dentro del intervalo indicado por `begin_expression` y `end_expression`; de lo contrario, `false`. Se devolverá `null` si `expression` es `null` o si `begin_expression` o `end_expression` es `null`.  
  
## <a name="remarks"></a>Observaciones  

 Para especificar un intervalo exclusivo, utilice los operadores mayor que (>) y menor que (<) en lugar de entre.  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente utiliza el operador BETWEEN para determinar si el resultado de una expresión es un valor incluido en un intervalo especificado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
