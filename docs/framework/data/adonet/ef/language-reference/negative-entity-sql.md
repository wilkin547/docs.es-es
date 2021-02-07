---
description: Más información acerca de:-(negativo) (Entity SQL)
title: '- Afectar (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: f3d30ce36b95e44755d148dc06279f67f15b0664
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712888"
---
# <a name="--negative-entity-sql"></a>- (Negativo) (Entity SQL)

Devuelve el valor negativo de una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Expresión válida de cualquier tipo de datos numérico.  
  
## <a name="result-types"></a>Tipos de resultado  

 El tipo de datos de `expression`.  
  
## <a name="remarks"></a>Observaciones  

 Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`. Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
