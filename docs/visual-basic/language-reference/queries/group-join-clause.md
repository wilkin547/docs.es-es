---
title: Cláusula Group Join
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
ms.openlocfilehash: 0546c86322663ce6c56a89e63311d0f02f88cfe4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346851"
---
# <a name="group-join-clause-visual-basic"></a>Group Join (Cláusula, Visual Basic)
Combina dos colecciones en una sola colección jerárquica. La operación de combinación se basa en las claves coincidentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`element`|Obligatorio. Variable de control de la colección que se va a combinar.|  
|`type`|Opcional. Tipo de `element`. Si no se especifica ningún `type`, el tipo de `element` se deduce de `collection`.|  
|`collection`|Obligatorio. Colección que se va a combinar con la colección que se encuentra en el lado izquierdo del operador `Group Join`. Una cláusula `Group Join` puede estar anidada en una cláusula `Join` o en otra cláusula `Group Join`.|  
|`key1` `Equals` `key2`|Obligatorio. Identifica las claves para las colecciones que se están combinando. Debe utilizar el operador `Equals` para comparar las claves de las colecciones que se están combinando. Puede combinar condiciones de combinación mediante el operador `And` para identificar varias claves. El parámetro `key1` debe ser de la colección en el lado izquierdo del operador `Join`. El parámetro `key2` debe ser de la colección del lado derecho del operador `Join`.<br /><br /> Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección. Sin embargo, cada expresión clave solo puede contener elementos de su colección respectiva.|  
|`expressionList`|Obligatorio. Una o más expresiones que identifican el modo en que se agregan los grupos de elementos de la colección. Para identificar un nombre de miembro para los resultados agrupados, use la palabra clave `Group` (`<alias> = Group`). También puede incluir funciones de agregado para aplicar al grupo.|  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Group Join` combina dos colecciones basadas en los valores de clave coincidentes de las colecciones que se van a combinar. La colección resultante puede contener un miembro que hace referencia a una colección de elementos de la segunda colección que coinciden con el valor de clave de la primera colección. También puede especificar las funciones de agregado que se van a aplicar a los elementos agrupados de la segunda colección. Para obtener información sobre las funciones de agregado, vea [cláusula Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Considere, por ejemplo, una colección de administradores y una colección de empleados. Los elementos de ambas colecciones tienen una propiedad ManagerID que identifica a los empleados que informan a un administrador determinado. Los resultados de una operación de combinación contendrían un resultado para cada administrador y empleado con un valor de ManagerID coincidente. Los resultados de una operación de `Group Join` contienen la lista completa de administradores. Cada resultado de administrador tendría un miembro que hacía referencia a la lista de empleados que coincidían con el administrador específico.  
  
 La colección resultante de una operación de `Group Join` puede contener cualquier combinación de valores de la colección identificada en la cláusula `From` y las expresiones identificadas en la cláusula `Into` de la cláusula `Group Join`. Para obtener más información sobre las expresiones válidas para la cláusula `Into`, consulte [Aggregate (cláusula](../../../visual-basic/language-reference/queries/aggregate-clause.md)).  
  
 Una operación `Group Join` devolverá todos los resultados de la colección identificada en el lado izquierdo del operador `Group Join`. Esto es así incluso si no hay ninguna coincidencia en la colección que se está combinando. Esto es como un `LEFT OUTER JOIN` en SQL.  
  
 Puede usar la cláusula `Join` para combinar colecciones en una sola colección. Esto es equivalente a un `INNER JOIN` en SQL.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Group Join`.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Join (cláusula)](../../../visual-basic/language-reference/queries/join-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By (cláusula)](../../../visual-basic/language-reference/queries/group-by-clause.md)
