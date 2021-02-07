---
description: 'Más información sobre: cláusula FROM (Visual Basic)'
title: Cláusula From
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
ms.openlocfilehash: e35188412deb7fd9f2d8306c85057d050a60d030
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700564"
---
# <a name="from-clause-visual-basic"></a>From (Cláusula, Visual Basic)

Especifica una o varias variables de rango y una colección que se va a consultar.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`element`|Obligatorio. Una *variable de rango* que se usa para recorrer en iteración los elementos de la colección. Una variable de rango se utiliza para hacer referencia a cada miembro de `collection` , ya que la consulta recorre en iteración la `collection` . Debe ser un tipo Enumerable.|  
|`type`|Opcional. Tipo de `element`. Si no `type` se especifica, el tipo de `element` se deduce de `collection` .|  
|`collection`|Necesario. Hace referencia a la colección que se va a consultar. Debe ser un tipo Enumerable.|  
  
## <a name="remarks"></a>Observaciones  

 La `From` cláusula se utiliza para identificar los datos de origen de una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen. Estas variables se denominan *variables de rango*. La `From` cláusula es necesaria para una consulta, excepto cuando `Aggregate` se usa la cláusula para identificar una consulta que devuelve solo resultados agregados. Para obtener más información, vea [cláusula Aggregate](aggregate-clause.md).  
  
 Puede especificar varias `From` cláusulas en una consulta para identificar varias colecciones que se van a combinar. Cuando se especifican varias colecciones, se recorren en iteración de forma independiente o puede combinarlas si están relacionadas. Puede combinar las colecciones implícitamente mediante la `Select` cláusula o explícitamente mediante las `Join` `Group Join` cláusulas o. Como alternativa, puede especificar varias colecciones y variables de rango en una sola `From` cláusula, con cada variable de rango relacionada y colección separadas de las otras mediante una coma. En el ejemplo de código siguiente se muestran ambas opciones de sintaxis para la `From` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 La `From` cláusula define el ámbito de una consulta, que es similar al ámbito de un `For` bucle. Por lo tanto, cada `element` variable de rango en el ámbito de una consulta debe tener un nombre único. Dado que puede especificar varias `From` cláusulas para una consulta, las `From` cláusulas posteriores pueden hacer referencia a las variables de rango de la `From` cláusula o pueden hacer referencia a las variables de rango de una `From` cláusula anterior. Por ejemplo, en el ejemplo siguiente se muestra una cláusula anidada en la `From` que la colección de la segunda cláusula se basa en una propiedad de la variable de rango de la primera cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 Cada `From` cláusula puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta. Puede refinar la consulta de las siguientes maneras:  
  
- Combine varias colecciones implícitamente mediante el uso de las `From` `Select` cláusulas y, o explícitamente mediante el uso de las `Join` `Group Join` cláusulas o.  
  
- Utilice la `Where` cláusula para filtrar el resultado de la consulta.  
  
- Ordene el resultado mediante la `Order By` cláusula.  
  
- Agrupe resultados similares juntos mediante la `Group By` cláusula.  
  
- Utilice la `Aggregate` cláusula para identificar las funciones de agregado que se van a evaluar para todo el resultado de la consulta.  
  
- Utilice la `Let` cláusula para introducir una variable de iteración cuyo valor se determina mediante una expresión en lugar de una colección.  
  
- Utilice la `Distinct` cláusula para omitir los resultados de la consulta duplicada.  
  
- Identifique las partes del resultado que se van a devolver mediante las `Skip` `Take` `Skip While` cláusulas,, y `Take While` .  
  
## <a name="example"></a>Ejemplo  

 La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `cust` de rango para cada `Customer` objeto de la `customers` colección. La `Where` cláusula usa la variable de rango para restringir la salida a los clientes de la región especificada. El `For Each` bucle muestra el nombre de la compañía para cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>Vea también

- [Consultas](index.md)
- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Instrucción For Each...Next](../statements/for-each-next-statement.md)
- [Instrucción For...Next](../statements/for-next-statement.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula WHERE](where-clause.md)
- [Aggregate Clause](aggregate-clause.md)
- [Cláusula Distinct](distinct-clause.md)
- [Cláusula Join](join-clause.md)
- [Cláusula Group Join](group-join-clause.md)
- [Cláusula order by](order-by-clause.md)
- [Cláusula Let](let-clause.md)
- [Cláusula Skip](skip-clause.md)
- [Cláusula Take](take-clause.md)
- [Cláusula Skip While](skip-while-clause.md)
- [Cláusula Take While](take-while-clause.md)
