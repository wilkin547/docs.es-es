---
title: + (Agregar)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: 1c525a1cd56d1d8b7ed0dad3a7cec686cb6b1ab3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580660"
---
# <a name="-add"></a>+ (Sumar)
Suma dos números.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Expresión válida de cualquier tipo de datos numérico.  
  
## <a name="result-types"></a>Tipos de resultado  
 El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos. Para obtener más información acerca de la promoción de tipos implícita, vea [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## <a name="remarks"></a>Comentarios  
 Para los tipos EDM.String, la suma es una concatenación.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador aritmético +  para sumar dos números. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a>Vea también
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Tipos de modelos conceptuales (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
