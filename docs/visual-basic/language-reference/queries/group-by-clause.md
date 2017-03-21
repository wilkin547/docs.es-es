---
title: "Group By (cláusula, Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement
- Group By clause
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a40074c4602d6c0164c784d497fbfb134402bf62
ms.lasthandoff: 03/13/2017

---
# <a name="group-by-clause-visual-basic"></a>Group By (Cláusula, Visual Basic)
Agrupa los elementos de los resultados de una consulta. También se puede usar para aplicar funciones de agregado a cada grupo. La operación de agrupación se basa en una o varias claves.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a>Elementos  
  
-   `listField1`, `listField2`  
  
     Opcional. Uno o más campos de la variable o las variables de consulta que identifican explícitamente los campos que se incluirán en el resultado agrupado. Si no se especifica ningún campo, se incluyen todos los campos de la variable o las variables de consulta en el resultado agrupado.  
  
-   `keyExp1`  
  
     Obligatorio. Expresión que identifica la clave que se va a usar para determinar los grupos de elementos. Puede especificar más de una clave para especificar una clave compuesta.  
  
-   `keyExp2`  
  
     Opcional. Uno o más claves adicionales que se combinan con `keyExp1` para crear una clave compuesta.  
  
-   `aggregateList`  
  
     Obligatorio. Una o más expresiones que identifican cómo se agregan los grupos. Para identificar un nombre de miembro para los resultados agrupados, use la palabra clave `Group` , que puede estar en cualquiera de los formatos siguientes:  
  
    ```  
    Into Group  
    ```  
  
     O bien  
  
    ```  
    Into <alias> = Group  
    ```  
  
     También puede incluir funciones de agregado para aplicar al grupo.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la cláusula `Group By` para dividir los resultados de una consulta en grupos. La agrupación se basa en una clave o una clave compuesta formada por varias claves. Los elementos que están asociados con valores de clave coincidentes se incluyen en el mismo grupo.  
  
 El parámetro `aggregateList` de la cláusula `Into` y la palabra clave `Group` se usan para identificar el nombre del miembro usado para hacer referencia al grupo. También puede incluir funciones de agregado en la cláusula `Into` para calcular los valores de los elementos agrupados. Para obtener una lista de funciones de agregado estándar, consulte [cláusula Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se agrupa una lista de clientes según su ubicación (país) y se proporciona un recuento de los clientes de cada grupo. Los resultados se ordenan por nombre de país. Los resultados agrupados se ordenan por nombre de ciudad.  
  
 [!code-vb[VbSimpleQuerySamples&#11;](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [FROM (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Group Join (cláusula)](../../../visual-basic/language-reference/queries/group-join-clause.md)
