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
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004783"
---
# <a name="from-clause-visual-basic"></a>From (Cláusula, Visual Basic)
Especifica una o varias variables de rango y una colección que se va a consultar.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`element`|Obligatorio. Una *variable de rango* que se usa para recorrer en iteración los elementos de la colección. Una variable de rango se usa para hacer referencia a cada miembro del `collection`, ya que la consulta recorre en iteración el `collection`. Debe ser un tipo Enumerable.|  
|`type`|Opcional. Tipo de `element`. Si no se especifica `type`, el tipo de `element` se deduce de `collection`.|  
|`collection`|Obligatorio. Hace referencia a la colección que se va a consultar. Debe ser un tipo Enumerable.|  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `From` se utiliza para identificar los datos de origen de una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen. Estas variables se denominan *variables de rango*. La cláusula `From` es necesaria para una consulta, excepto cuando se usa la cláusula `Aggregate` para identificar una consulta que devuelve solo resultados agregados. Para obtener más información, vea [cláusula Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Puede especificar varias cláusulas `From` en una consulta para identificar varias colecciones que se van a combinar. Cuando se especifican varias colecciones, se recorren en iteración de forma independiente o puede combinarlas si están relacionadas. Puede combinar las colecciones implícitamente mediante la cláusula `Select`, o explícitamente mediante las cláusulas `Join` o `Group Join`. Como alternativa, puede especificar varias colecciones y variables de rango en una sola cláusula `From`, con cada variable de rango relacionada y colección separadas de las otras por una coma. En el ejemplo de código siguiente se muestran las dos opciones de sintaxis para la cláusula `From`.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 La cláusula `From` define el ámbito de una consulta, que es similar al ámbito de un bucle `For`. Por lo tanto, cada variable de rango `element` en el ámbito de una consulta debe tener un nombre único. Dado que puede especificar varias cláusulas `From` para una consulta, las cláusulas de `From` subsiguientes pueden hacer referencia a las variables de rango de la cláusula `From` o pueden hacer referencia a las variables de rango de una cláusula `From` anterior. Por ejemplo, en el ejemplo siguiente se muestra una cláusula anidada `From` en la que la colección de la segunda cláusula se basa en una propiedad de la variable de rango de la primera cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 Cada cláusula `From` puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta. Puede refinar la consulta de las siguientes maneras:  
  
- Combine varias colecciones implícitamente mediante el uso de las cláusulas `From` y `Select`, o explícitamente mediante las cláusulas `Join` o `Group Join`.  
  
- Utilice la cláusula `Where` para filtrar el resultado de la consulta.  
  
- Ordene el resultado mediante la cláusula `Order By`.  
  
- Agrupe resultados similares juntos mediante la cláusula `Group By`.  
  
- Utilice la cláusula `Aggregate` para identificar las funciones de agregado que se van a evaluar para todo el resultado de la consulta.  
  
- Utilice la cláusula `Let` para introducir una variable de iteración cuyo valor se determina mediante una expresión en lugar de una colección.  
  
- Utilice la cláusula `Distinct` para omitir los resultados de la consulta duplicada.  
  
- Identifique las partes del resultado que se van a devolver mediante las cláusulas `Skip`, `Take`, `Skip While` y `Take While`.  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `cust` para cada objeto `Customer` en la colección `customers`. La cláusula `Where` usa la variable de rango para restringir la salida a los clientes de la región especificada. El bucle `For Each` muestra el nombre de la compañía para cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>Vea también

- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
- [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Distinct (cláusula)](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Join (cláusula)](../../../visual-basic/language-reference/queries/join-clause.md)
- [Group Join (cláusula)](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Let (cláusula)](../../../visual-basic/language-reference/queries/let-clause.md)
- [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)
