---
title: Cláusula Select
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: d96423efbee075a7ad257df72471c71e38e09b63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875753"
---
# <a name="select-clause-visual-basic"></a>Select (Cláusula, Visual Basic)

Define el resultado de una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Partes  

 `var1`  
 Opcional. Un alias que se puede utilizar para hacer referencia a los resultados de la expresión de columna.  
  
 `fieldName1`  
 Obligatorio. Nombre del campo que se va a devolver en el resultado de la consulta.  
  
## <a name="remarks"></a>Comentarios  

 Puede utilizar la `Select` cláusula para definir los resultados que se van a devolver desde una consulta. Esto le permite definir los miembros de un nuevo tipo anónimo creado por una consulta o establecer como destino los miembros de un tipo con nombre devuelto por una consulta. La `Select` cláusula no es necesaria para una consulta. Si no `Select` se especifica ninguna cláusula, la consulta devolverá un tipo basado en todos los miembros de las variables de rango identificadas para el ámbito actual. Para obtener más información, consulte [Tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md) (Guía de programación de C#). Cuando una consulta crea un tipo con nombre, devolverá un resultado de tipo <xref:System.Collections.Generic.IEnumerable%601> donde `T` es el tipo creado.  
  
 La `Select` cláusula puede hacer referencia a cualquier variable del ámbito actual. Esto incluye las variables de rango identificadas en la `From` cláusula (o `From` cláusulas). También incluye las nuevas variables creadas con un alias por las `Aggregate` `Let` `Group By` cláusulas,, o `Group Join` , o las variables de una cláusula anterior `Select` en la expresión de consulta. La `Select` cláusula también puede incluir valores estáticos. Por ejemplo, en el ejemplo de código siguiente se muestra una expresión de consulta en la que la `Select` cláusula define el resultado de la consulta como un nuevo tipo anónimo con cuatro miembros: `ProductName` , `Price` , `Discount` y `DiscountedPrice` . Los `ProductName` valores de los `Price` miembros y se toman de la variable de rango de producto que se define en la `From` cláusula. El `DiscountedPrice` valor del miembro se calcula en la `Let` cláusula. El `Discount` miembro es un valor estático.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 La `Select` cláusula presenta un nuevo conjunto de variables de rango para las cláusulas de consulta subsiguientes y las variables de rango anteriores ya no están en el ámbito. La última `Select` cláusula de una expresión de consulta determina el valor devuelto de la consulta. Por ejemplo, la consulta siguiente devuelve el nombre de la compañía y el ID. de pedido de cada pedido de cliente cuyo total supera el 500. La primera `Select` cláusula identifica las variables de rango para la `Where` cláusula y la segunda `Select` cláusula. La segunda `Select` cláusula identifica los valores devueltos por la consulta como un nuevo tipo anónimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Si la `Select` cláusula identifica un solo elemento que se va a devolver, la expresión de consulta devuelve una colección del tipo de ese único elemento. Si la `Select` cláusula identifica varios elementos que se van a devolver, la expresión de consulta devuelve una colección de un nuevo tipo anónimo, basado en los elementos seleccionados. Por ejemplo, las dos consultas siguientes devuelven colecciones de dos tipos diferentes basados en la `Select` cláusula. La primera consulta devuelve una colección de nombres de compañía como cadenas. La segunda consulta devuelve una colección de `Customer` objetos rellenados con los nombres e información de dirección de la compañía.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Ejemplo  

 La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `cust` de rango para la `customers` colección. La `Select` cláusula selecciona el nombre del cliente y el valor del identificador y rellena las `CompanyName` `CustomerID` columnas y de la nueva variable de rango. La `For Each` instrucción recorre en bucle cada objeto devuelto y muestra las `CompanyName` `CustomerID` columnas y de cada registro.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Cláusula FROM](from-clause.md)
- [Cláusula WHERE](where-clause.md)
- [Cláusula order by](order-by-clause.md)
- [Tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
