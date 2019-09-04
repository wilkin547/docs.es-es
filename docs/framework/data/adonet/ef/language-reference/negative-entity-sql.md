---
title: '- Afectar (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: effd537bcd53052830f2195e18ca959b49d87255
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249922"
---
# <a name="--negative-entity-sql"></a>- (Negativo) (Entity SQL)
Devuelve el valor negativo de una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
1. Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
