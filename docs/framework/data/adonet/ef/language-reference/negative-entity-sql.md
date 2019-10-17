---
title: '- Afectar (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 7716b9115587a873531be9c14b7da93c7a148ed8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319536"
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
 Tipo de datos de `expression`.  
  
## <a name="remarks"></a>Comentarios  
 Si `expression` es un tipo sin signo, el tipo del resultado será el tipo con signo que más se aproxime al tipo de `expression`. Por ejemplo, si `expression` es de tipo Byte, se devolverá un valor de tipo Int16.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético - para devolver el valor negativo de una expresión numérica. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
