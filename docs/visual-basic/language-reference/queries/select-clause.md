---
title: "Select (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9d8cabcbd8554ca2aee639eaac8a52f0485a266
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="select-clause-visual-basic"></a>Select (Cláusula, Visual Basic)
Define el resultado de una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Elementos  
 `var1`  
 Opcional. Un alias que puede utilizarse para hacer referencia a los resultados de la expresión de columna.  
  
 `fieldName1`  
 Obligatorio. El nombre del campo que se va a devolver en el resultado de la consulta.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Select` cláusula para definir los resultados para devolver desde una consulta. Esto le permite definir los miembros de un nuevo tipo anónimo creado por una consulta, o a los miembros de un tipo con nombre que es devuelto por una consulta de destino. El `Select` cláusula no es necesaria para una consulta. Si no hay ningún `Select` cláusula se especifica, la consulta devolverá un tipo basado en todos los miembros de las variables de rango identificados para el ámbito actual. Para más información, vea [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Cuando una consulta crea un tipo con nombre, devolverá un resultado de tipo <xref:System.Collections.Generic.IEnumerable%601> donde `T` es el tipo creado.  
  
 El `Select` cláusula puede hacer referencia a las variables en el ámbito actual. Esto incluye las variables de rango identificadas en el `From` cláusula (o `From` cláusulas). También incluye las variables nuevas creadas con un alias mediante la `Aggregate`, `Let`, `Group By`, o `Group Join` cláusulas o variables desde anterior `Select` cláusula en la expresión de consulta. El `Select` cláusula también puede incluir valores estáticos. Por ejemplo, en el ejemplo de código siguiente se muestra una expresión de consulta en el que el `Select` cláusula define el resultado de la consulta como un nuevo tipo anónimo con cuatro miembros: `ProductName`, `Price`, `Discount`, y `DiscountedPrice`. El `ProductName` y `Price` valores de miembro se toman de la variable de rango de producto que se define en el `From` cláusula. El `DiscountedPrice` se calcula el valor del miembro en el `Let` cláusula. El `Discount` miembro es un valor estático.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 El `Select` cláusula presenta un nuevo conjunto de variables de rango para las cláusulas de consulta subsiguientes y las variables de rango anteriores ya no están en ámbito. La última `Select` cláusula en una expresión de consulta determina el valor devuelto de la consulta. Por ejemplo, la consulta siguiente devuelve a la compañía nombre y el identificador de cada pedido del cliente para el que el total sea superior a 500. La primera `Select` cláusula identifica las variables de rango para el `Where` cláusula y el segundo `Select` cláusula. El segundo `Select` cláusula identifica los valores devueltos por la consulta como un nuevo tipo anónimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 Si el `Select` cláusula identifica un solo elemento para devolver, la expresión de consulta devuelve una colección del tipo de ese elemento único. Si el `Select` cláusula identifica varios elementos que se devolverán, la expresión de consulta devuelve una colección de un nuevo tipo anónimo, en función de los elementos seleccionados. Por ejemplo, las dos consultas siguientes devuelven colecciones de dos tipos diferentes en función de la `Select` cláusula. La primera consulta devuelve una colección de nombres de compañía como cadenas. La segunda consulta devuelve una colección de `Customer` objetos que se llena con los nombres de las compañías y la información de dirección.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para el `customers` colección. El `Select` cláusula selecciona el nombre del cliente y el valor de identificador y rellena el `CompanyName` y `CustomerID` las columnas de la nueva variable de rango. El `For Each` instrucción recorre en iteración cada objeto devuelto y muestra el `CompanyName` y `CustomerID` columnas para cada registro.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
