---
description: 'Más información acerca de: < (menor que) (Entity SQL)'
title: < (menor que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 523defa6c19ca43a5827258277bbe3f489b9b8c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748289"
---
# <a name="-less-than-entity-sql"></a>\< (Menor que) (Entity SQL)

Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor menor que el de la expresión de la derecha.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.  
  
## <a name="result-types"></a>Tipos de resultado  

 `true` si la expresión izquierda tiene un valor menor que el de la expresión derecha; de lo contrario, `false`.  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente utiliza el operador de comparación < para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor menor que el de la expresión derecha. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
