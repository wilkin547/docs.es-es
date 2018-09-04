---
title: Join (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499430"
---
# <a name="join-clause-visual-basic"></a>Join (Cláusula, Visual Basic)
Combina dos colecciones en una sola colección. La operación de combinación se basa en claves coincidentes y usa el `Equals` operador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Elementos  
 `element`  
 Requerido. La variable de control para la colección que se está combina.  
  
 `collection`  
 Requerido. La colección para combinar con la colección identificado en el lado izquierdo de la `Join` operador. Un `Join` cláusula puede estar anidada en otro `Join` cláusula, o en un `Group Join` cláusula.  
  
 `joinClause`  
 Opcional. Uno o más adicionales `Join` cláusulas aún más refinar la consulta.  
  
 `groupJoinClause`  
 Opcional. Uno o más adicionales `Group Join` cláusulas aún más refinar la consulta.  
  
 `key1` `Equals` `key2`  
 Requerido. Identifica las claves para las colecciones que se están combina. Debe usar el `Equals` operador para comparar las claves de las colecciones que se están combina. Puede combinar condiciones de combinación utilizando el `And` operador para identificar varias claves. `key1` debe ser de la colección en el lado izquierdo de la `Join` operador. `key2` debe ser de la colección en el lado derecho de la `Join` operador.  
  
 Las claves usadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección. Sin embargo, cada expresión de clave solo puede contener elementos de su colección respectiva.  
  
## <a name="remarks"></a>Comentarios  
 El `Join` cláusula combina dos colecciones basadas en valores de clave de las colecciones que se están combinando coincidentes. La colección resultante puede contener cualquier combinación de valores de la colección identificado en el lado izquierdo de la `Join` operador y la colección identificado en el `Join` cláusula. La consulta devolverá solo los resultados para el que la condición especificada por el `Equals` operador se cumple. Esto es equivalente a un `INNER JOIN` en SQL.  
  
 Puede usar varios `Join` cláusulas en una consulta para combinar dos o más colecciones en una sola colección.  
  
 Puede realizar una combinación implícita para combinar colecciones sin el `Join` cláusula. Para ello, incluyen varias `In` cláusulas en su `From` cláusula y especifique un `Where` cláusula que identifica las claves que desee usar para la combinación.  
  
 Puede usar el `Group Join` cláusula para combinar colecciones en una sola colección jerárquica. Esto es similar a un `LEFT OUTER JOIN` en SQL.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente realiza una combinación implícita para combinar una lista de clientes con sus pedidos.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente combina dos colecciones mediante el uso de la `Join` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 En este ejemplo genera una salida similar al siguiente:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente combina dos colecciones mediante el uso de la `Join` cláusula con dos columnas de clave.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 En el ejemplo se genera una salida similar al siguiente:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/index.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Group Join (cláusula)](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
