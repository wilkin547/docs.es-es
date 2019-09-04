---
title: '- Dividir (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: d4e4c1449b665e6dea22bfcc0ee2277478b4da1a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251055"
---
# <a name="-divide-entity-sql"></a>/ (Dividir) (Entity SQL)
Divide un número entre otro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a>Argumentos  
 `dividend`  
 Expresión numérica que se va a dividir. `dividend` es una expresión válida de cualquier tipo de datos numérico.  
  
 `divisor`  
 Expresión numérica entre la que se divide el dividendo. `divisor` es una expresión válida de cualquier tipo de datos numérico.  
  
## <a name="result-types"></a>Tipos de resultado  
 El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos. Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador aritmético/para dividir un número entre otro. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
