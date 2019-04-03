---
title: Select (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 367d810c2358963bfe2f092a390443eccdc66941
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814450"
---
# <a name="select-clause-visual-basic"></a>Select (Cláusula, Visual Basic)
Define el resultado de una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Elementos  
 `var1`  
 Opcional. Un alias que se puede usar para hacer referencia a los resultados de la expresión de columna.  
  
 `fieldName1`  
 Obligatorio. El nombre del campo para devolver resultados de la consulta.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Select` cláusula para definir los resultados se devuelven desde una consulta. Esto le permite definir los miembros de un nuevo tipo anónimo creado por una consulta, o a los miembros de un tipo con nombre devuelto por una consulta de destino. El `Select` cláusula no es necesaria para una consulta. Si no hay ningún `Select` cláusula se especifica, la consulta devolverá un tipo basado en todos los miembros de las variables de rango identificadas para el ámbito actual. Para más información, vea [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Cuando una consulta crea un tipo con nombre, devolverá un resultado de tipo <xref:System.Collections.Generic.IEnumerable%601> donde `T` es el tipo creado.  
  
 El `Select` cláusula puede hacer referencia a las variables en el ámbito actual. Esto incluye las variables de rango identificadas en el `From` cláusula (o `From` cláusulas). También incluye las variables nuevas creadas con un alias mediante la `Aggregate`, `Let`, `Group By`, o `Group Join` cláusulas o variables en una anterior `Select` cláusula en la expresión de consulta. El `Select` cláusula también puede incluir valores estáticos. Por ejemplo, en el ejemplo de código siguiente se muestra una expresión de consulta en el que el `Select` cláusula define el resultado de la consulta como un nuevo tipo anónimo con cuatro miembros: `ProductName`, `Price`, `Discount`, y `DiscountedPrice`. El `ProductName` y `Price` se toman los valores de miembro de la variable de rango de producto que se define en el `From` cláusula. El `DiscountedPrice` se calcula el valor del miembro en el `Let` cláusula. El `Discount` miembro es un valor estático.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 El `Select` cláusula presenta un nuevo conjunto de variables de rango para las cláusulas de consulta subsiguientes, y las variables de rango anteriores ya no están en ámbito. La última `Select` cláusula en una expresión de consulta determina el valor devuelto de la consulta. Por ejemplo, la consulta siguiente devuelve a la compañía de nombre y el identificador de cada pedido del cliente para el que el total superior a 500. La primera `Select` cláusula identifica las variables de rango para el `Where` cláusula y el segundo `Select` cláusula. El segundo `Select` cláusula identifica los valores devueltos por la consulta como un nuevo tipo anónimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Si el `Select` cláusula identifica un único elemento va a devolver, la expresión de consulta devuelve una colección del tipo de ese elemento único. Si el `Select` cláusula identifica varios elementos que se devolverán, la expresión de consulta devuelve una colección de un nuevo tipo anónimo, en función de los elementos seleccionados. Por ejemplo, las dos consultas siguientes devuelven colecciones de dos tipos diferentes, según la `Select` cláusula. La primera consulta devuelve una colección de nombres de compañía como cadenas. La segunda consulta devuelve una colección de `Customer` objetos que se rellena con los nombres de la empresa y la información de dirección.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para el `customers` colección. El `Select` cláusula selecciona el nombre del cliente y el valor de identificador y rellena el `CompanyName` y `CustomerID` las columnas de la nueva variable de rango. El `For Each` instrucción recorre en iteración cada objeto devuelto y muestra el `CompanyName` y `CustomerID` columnas para cada registro.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
- [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
