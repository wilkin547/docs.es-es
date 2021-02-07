---
description: 'Más información acerca de: <= (menor o igual que) (Entity SQL)'
title: <= (menor o igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: f720c4ef87cdd0cceea175b1ea70caf5ac6e1deb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748263"
---
# <a name="-less-than-or-equal-to-entity-sql"></a>\<= (Menor o igual que) (Entity SQL)

Compara dos expresiones para determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión válida. Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.  
  
## <a name="result-types"></a>Tipos de resultado  

 `true` si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha; de lo contrario, `false`.  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente utiliza el operador de comparación <= para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
