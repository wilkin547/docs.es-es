---
description: 'Más información sobre: + (concatenación de cadenas) (Entity SQL)'
title: + (Concatenación de cadenas) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 7b6aac5b865e2127bb23446248e20d83ea3c7ea3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791847"
---
# <a name="-string-concatenation-entity-sql"></a>+ (Concatenación de cadenas) (Entity SQL)

Concatena dos cadenas.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión válida de los tipos de datos EDM.String. Ambas expresiones deben ser del mismo tipo de datos o una se debe poder convertir implícitamente en el tipo de datos de la otra.  
  
## <a name="result-types"></a>Tipos de resultado  

 El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos. Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador +  para concatenar dos cadenas. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Tipos de modelos conceptuales (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
