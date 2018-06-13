---
title: Group Join (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 094281b0afb34451ae8539e4eb967043b21d379c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604762"
---
# <a name="group-join-clause-visual-basic"></a>Group Join (Cláusula, Visual Basic)
Combina dos colecciones en una sola colección jerárquica. La operación de combinación se basa en claves coincidentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`element`|Requerido. La variable de control de la colección que se está combinando.|  
|`type`|Opcional. Tipo de `element`. Si no hay ningún `type` se especifica, el tipo de `element` se deduce de `collection`.|  
|`collection`|Requerido. La colección que combine con la colección que se encuentra en el lado izquierdo de la `Group Join` operador. A `Group Join` cláusula puede estar anidada en una `Join` cláusula o en otro `Group Join` cláusula.|  
|`key1` `Equals` `key2`|Requerido. Identifica las claves para las colecciones que se está combina. Debe utilizar el `Equals` operador para comparar las claves de las colecciones que se está combina. Puede combinar condiciones de combinación mediante la `And` operador para identificar varias claves. El `key1` parámetro debe ser de la colección en el lado izquierdo de la `Join` operador. El `key2` parámetro debe ser de la colección en el lado derecho de la `Join` operador.<br /><br /> Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección. Sin embargo, cada expresión de clave solo puede contener elementos de su colección respectiva.|  
|`expressionList`|Requerido. Una o varias expresiones que identifican cómo se agregan los grupos de elementos de la colección. Para identificar un nombre de miembro para los resultados agrupados, utilice la `Group` palabra clave (`<alias> = Group`). También puede incluir funciones de agregado para aplicar al grupo.|  
  
## <a name="remarks"></a>Comentarios  
 El `Group Join` cláusula combina dos colecciones que coinciden con los valores de clave de las colecciones que se está combinando. La colección resultante puede contener a un miembro que hace referencia a una colección de elementos de la segunda colección que coinciden con el valor de clave de la primera colección. También puede especificar las funciones de agregado para aplicar a los elementos agrupados de la segunda colección. Para obtener información acerca de las funciones de agregado, vea [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Considere, por ejemplo, una colección de administradores y una colección de empleados. Elementos de ambas colecciones tienen una propiedad ManagerID que identifica a los empleados que dependen de un administrador determinado. Los resultados de una operación de combinación contendrían un resultado para cada administrador y empleado con un valor ManagerID coincidente. Los resultados de una `Group Join` operación contendría la lista completa de administradores. Cada resultado de administrador tendría un miembro que hace referencia a la lista de empleados que fueron una coincidencia para el administrador concreto.  
  
 La colección resultante de un `Group Join` operación puede contener cualquier combinación de valores de la colección identificado en el `From` cláusula y las expresiones identificadas en el `Into` cláusula de la `Group Join` cláusula. Para obtener más información sobre las expresiones válidas para la `Into` cláusula, vea [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 A `Group Join` operación devolverá todos los resultados de la colección identificado en el lado izquierdo de la `Group Join` operador. Esto ocurre incluso si no hay ninguna coincidencia en la colección que se está combinando. Esto es similar a una `LEFT OUTER JOIN` en SQL.  
  
 Puede usar el `Join` cláusula para combinar colecciones en una sola colección. Esto es equivalente a un `INNER JOIN` en SQL.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se combina dos colecciones mediante el uso de la `Group Join` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Join (cláusula)](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Group By (cláusula)](../../../visual-basic/language-reference/queries/group-by-clause.md)
