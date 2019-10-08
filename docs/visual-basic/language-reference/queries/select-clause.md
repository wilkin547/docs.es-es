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
ms.openlocfilehash: 087472c51d203be083fea0d39ade6f12066cfcb4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004739"
---
# <a name="select-clause-visual-basic"></a>Select (Cláusula, Visual Basic)
Define el resultado de una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Elementos  
 `var1`  
 Opcional. Un alias que se puede utilizar para hacer referencia a los resultados de la expresión de columna.  
  
 `fieldName1`  
 Obligatorio. Nombre del campo que se va a devolver en el resultado de la consulta.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la cláusula `Select` para definir los resultados que se van a devolver desde una consulta. Esto le permite definir los miembros de un nuevo tipo anónimo creado por una consulta o establecer como destino los miembros de un tipo con nombre devuelto por una consulta. La cláusula `Select` no es necesaria para una consulta. Si no se especifica ninguna cláusula `Select`, la consulta devolverá un tipo basado en todos los miembros de las variables de rango identificadas para el ámbito actual. Para más información, vea [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Cuando una consulta crea un tipo con nombre, devolverá un resultado de tipo <xref:System.Collections.Generic.IEnumerable%601> donde `T` es el tipo creado.  
  
 La cláusula `Select` puede hacer referencia a cualquier variable del ámbito actual. Esto incluye las variables de rango identificadas en la cláusula `From` (o en las cláusulas `From`). También incluye las nuevas variables creadas con un alias mediante las cláusulas `Aggregate`, `Let`, `Group By` o `Group Join`, o las variables de una cláusula `Select` anterior en la expresión de consulta. La cláusula `Select` también puede incluir valores estáticos. Por ejemplo, en el ejemplo de código siguiente se muestra una expresión de consulta en la que la cláusula `Select` define el resultado de la consulta como un nuevo tipo anónimo con cuatro miembros: `ProductName`, `Price`, `Discount` y `DiscountedPrice`. Los valores de miembro `ProductName` y `Price` se toman de la variable de rango de producto que se define en la cláusula `From`. El valor del miembro `DiscountedPrice` se calcula en la cláusula `Let`. El miembro `Discount` es un valor estático.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 La cláusula `Select` introduce un nuevo conjunto de variables de rango para las cláusulas de consulta subsiguientes, y las variables de rango anteriores ya no están en el ámbito. La última cláusula `Select` en una expresión de consulta determina el valor devuelto de la consulta. Por ejemplo, la consulta siguiente devuelve el nombre de la compañía y el ID. de pedido de cada pedido de cliente cuyo total supera el 500. La primera cláusula `Select` identifica las variables de rango para la cláusula `Where` y la segunda cláusula `Select`. La segunda cláusula `Select` identifica los valores devueltos por la consulta como un nuevo tipo anónimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Si la cláusula `Select` identifica un solo elemento que se va a devolver, la expresión de consulta devuelve una colección del tipo de ese único elemento. Si la cláusula `Select` identifica varios elementos que se van a devolver, la expresión de consulta devuelve una colección de un nuevo tipo anónimo, basado en los elementos seleccionados. Por ejemplo, las dos consultas siguientes devuelven colecciones de dos tipos diferentes basados en la cláusula `Select`. La primera consulta devuelve una colección de nombres de compañía como cadenas. La segunda consulta devuelve una colección de objetos `Customer` rellenados con los nombres e información de dirección de la compañía.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `cust` para la colección `customers`. La cláusula `Select` selecciona el nombre del cliente y el valor del identificador y rellena las columnas `CompanyName` y `CustomerID` de la nueva variable de rango. La instrucción `For Each` recorre en bucle cada objeto devuelto y muestra las columnas `CompanyName` y `CustomerID` para cada registro.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
- [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
