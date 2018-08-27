---
title: From (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 71573de48cc51c48291fc4b82a0628d2d0f96caa
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932493"
---
# <a name="from-clause-visual-basic"></a>From (Cláusula, Visual Basic)
Especifica uno o más variables de rango y una colección a la consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`element`|Requerido. Un *variable de rango* utiliza para recorrer en iteración los elementos de la colección. Una variable de rango se usa para referirse a cada miembro de la `collection` como la consulta se recorre el `collection`. Debe ser un tipo enumerable.|  
|`type`|Opcional. Tipo de `element`. Si no hay ningún `type` se especifica, el tipo de `element` se deduce del `collection`.|  
|`collection`|Requerido. Hace referencia a la colección que se van a consultar. Debe ser un tipo enumerable.|  
  
## <a name="remarks"></a>Comentarios  
 El `From` cláusula se usa para identificar los datos de origen para una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen. Estas variables se denominan *las variables de rango*. El `From` cláusula se requiere para una consulta, excepto cuando la `Aggregate` cláusula se usa para identificar una consulta que devuelve resultados agregados solo. Para obtener más información, consulte [cláusula Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Puede especificar varios `From` cláusulas en una consulta para identificar varias colecciones a unirse. Cuando se especifican varias colecciones, se iteran en forma independiente o combinarlas si están relacionadas. Puede combinar colecciones implícitamente mediante el uso de la `Select` cláusula, o explícitamente mediante la `Join` o `Group Join` cláusulas. Como alternativa, puede especificar varias variables de rango y colecciones en una sola `From` cláusula con cada variable de rango relacionado y la colección separados de los demás por una coma. El ejemplo de código siguiente muestra ambas opciones de sintaxis para el `From` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 El `From` cláusula define el ámbito de una consulta, que es similar al ámbito de un `For` bucle. Por lo tanto, cada uno de ellos `element` variable de rango en el ámbito de una consulta debe tener un nombre único. Dado que puede especificar varios `From` cláusulas para una consulta, posteriores `From` cláusulas pueden hacer referencia a las variables de rango en la `From` cláusula, o bien pueden hacer referencia a las variables de rango en una anterior `From` cláusula. Por ejemplo, en el ejemplo siguiente se muestra un anidada `From` cláusula donde la colección en la segunda cláusula se basa en una propiedad de la variable de rango en la primera cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Cada `From` cláusula puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta. Puede refinar la consulta de las maneras siguientes:  
  
-   Combinar varias colecciones implícitamente mediante la `From` y `Select` cláusulas, o explícitamente mediante la `Join` o `Group Join` cláusulas.  
  
-   Use el `Where` cláusula para filtrar el resultado de la consulta.  
  
-   Ordenar el resultado mediante la `Order By` cláusula.  
  
-   Agrupar resultados similares mediante el uso de la `Group By` cláusula.  
  
-   Use el `Aggregate` cláusula para identificar las funciones de agregado que se evalúa para el resultado de toda la consulta.  
  
-   Use el `Let` cláusula para introducir una variable de iteración cuyo valor viene determinado por una expresión en lugar de una colección.  
  
-   Use el `Distinct` cláusula para pasar por alto los resultados de consulta duplicada.  
  
-   Identificar las partes del resultado para devolver mediante el uso de la `Skip`, `Take`, `Skip While`, y `Take While` cláusulas.  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para cada `Customer` objeto en el `customers` colección. El `Where` cláusula usa la variable de rango para restringir los resultados a los clientes de la región especificada. El `For Each` bucle muestra el nombre de la empresa para cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Consultas](../../../visual-basic/language-reference/queries/index.md)  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Distinct (cláusula)](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [Join (cláusula)](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Group Join (cláusula)](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Let (cláusula)](../../../visual-basic/language-reference/queries/let-clause.md)  
 [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)
