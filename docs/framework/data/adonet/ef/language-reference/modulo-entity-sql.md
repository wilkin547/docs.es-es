---
title: (Módulo) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 4bbdbe53403cfec2568cfac320fc7ab1ad2725b0
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319598"
---
# <a name="modulo-entity-sql"></a>(Módulo) (Entity SQL)
Devuelve el resto de una expresión dividida entre otra.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a>Argumentos  
 `dividend`  
 Expresión numérica que se va a dividir. `dividend` es una expresión válida de cualquier tipo de datos numérico.  
  
 `divisor`  
 Expresión numérica entre la que se divide el dividendo. `divisor` es una expresión válida de cualquier tipo de datos numérico.  
  
## <a name="result-types"></a>Tipos de resultado  
 Edm.Int32  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético % para devolver el resto de una expresión dividida entre otra. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
