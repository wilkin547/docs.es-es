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
ms.openlocfilehash: 8d5f3ec80cb39825a3a283907d614b9be28e6e91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869908"
---
# <a name="group-join-clause-visual-basic"></a>Group Join (Cláusula, Visual Basic)

Combina dos colecciones en una sola colección jerárquica. La operación de combinación se basa en las claves coincidentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`element`|Obligatorio. Variable de control de la colección que se va a combinar.|  
|`type`|Opcional. Tipo de `element`. Si no `type` se especifica, el tipo de `element` se deduce de `collection` .|  
|`collection`|Obligatorio. Colección que se va a combinar con la colección que se encuentra en el lado izquierdo del `Group Join` operador. Una `Group Join` cláusula se puede anidar en una `Join` cláusula o en otra `Group Join` cláusula.|  
|`key1` `Equals` `key2`|Obligatorio. Identifica las claves para las colecciones que se están combinando. Debe utilizar el `Equals` operador para comparar las claves de las colecciones que se están combinando. Puede combinar condiciones de combinación mediante el `And` operador para identificar varias claves. El `key1` parámetro debe ser de la colección en el lado izquierdo del `Join` operador. El `key2` parámetro debe ser de la colección del lado derecho del `Join` operador.<br /><br /> Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección. Sin embargo, cada expresión clave solo puede contener elementos de su colección respectiva.|  
|`expressionList`|Obligatorio. Una o más expresiones que identifican el modo en que se agregan los grupos de elementos de la colección. Para identificar un nombre de miembro para los resultados agrupados, use la `Group` palabra clave ( `<alias> = Group` ). También puede incluir funciones de agregado para aplicar al grupo.|  
  
## <a name="remarks"></a>Comentarios  

 La `Group Join` cláusula combina dos colecciones basadas en los valores de clave coincidentes de las colecciones que se están combinando. La colección resultante puede contener un miembro que hace referencia a una colección de elementos de la segunda colección que coinciden con el valor de clave de la primera colección. También puede especificar las funciones de agregado que se van a aplicar a los elementos agrupados de la segunda colección. Para obtener información sobre las funciones de agregado, vea [cláusula Aggregate](aggregate-clause.md).  
  
 Considere, por ejemplo, una colección de administradores y una colección de empleados. Los elementos de ambas colecciones tienen una propiedad ManagerID que identifica a los empleados que informan a un administrador determinado. Los resultados de una operación de combinación contendrían un resultado para cada administrador y empleado con un valor de ManagerID coincidente. Los resultados de una `Group Join` operación contienen la lista completa de administradores. Cada resultado de administrador tendría un miembro que hacía referencia a la lista de empleados que coincidían con el administrador específico.  
  
 La colección resultante de una `Group Join` operación puede contener cualquier combinación de valores de la colección identificada en la `From` cláusula y las expresiones identificadas en la `Into` cláusula de la `Group Join` cláusula. Para obtener más información sobre las expresiones válidas para la `Into` cláusula, consulte [Aggregate (cláusula](aggregate-clause.md)).  
  
 Una `Group Join` operación devolverá todos los resultados de la colección identificada en el lado izquierdo del `Group Join` operador. Esto es así incluso si no hay ninguna coincidencia en la colección que se está combinando. Es como un `LEFT OUTER JOIN` en SQL.  
  
 Puede usar la `Join` cláusula para combinar colecciones en una sola colección. Esto es equivalente a `INNER JOIN` en SQL.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se combinan dos colecciones mediante la `Group Join` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula FROM](from-clause.md)
- [Join (cláusula)](join-clause.md)
- [Cláusula WHERE](where-clause.md)
- [Cláusula Group By](group-by-clause.md)
