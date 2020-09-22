---
title: Cláusula Order By
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 05fa720237f4b0185b5c07217362c99b5dbf4303
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869792"
---
# <a name="order-by-clause-visual-basic"></a>Order By (Cláusula, Visual Basic)

Especifica el criterio de ordenación para el resultado de una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Partes  

 `orderExp1`  
 Obligatorio. Uno o más campos del resultado de la consulta actual que identifican cómo ordenar los valores devueltos. Los nombres de campo deben estar separados por comas (,). Puede identificar cada campo como ordenado en orden ascendente o descendente mediante el uso de las `Ascending` `Descending` palabras clave o. Si no `Ascending` `Descending` se especifica ninguna palabra clave o, el criterio de ordenación predeterminado es ascendente. Los campos de criterio de ordenación tienen prioridad de izquierda a derecha.  
  
## <a name="remarks"></a>Comentarios  

 Puede utilizar la `Order By` cláusula para ordenar los resultados de una consulta. La `Order By` cláusula solo puede ordenar un resultado en función de la variable de rango del ámbito actual. Por ejemplo, la `Select` cláusula introduce un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para ese ámbito. Las variables de rango definidas antes de una `Select` cláusula en una consulta no están disponibles después de la `Select` cláusula. Por lo tanto, si desea ordenar los resultados por un campo que no está disponible en la `Select` cláusula, debe colocar la `Order By` cláusula delante de la `Select` cláusula. Un ejemplo de Cuándo tendría que hacer esto es cuando desea ordenar la consulta por campos que no se devuelven como parte del resultado.  
  
 El orden ascendente y descendente de un campo viene determinado por la implementación de la <xref:System.IComparable> interfaz para el tipo de datos del campo. Si el tipo de datos no implementa la <xref:System.IComparable> interfaz, se omite el criterio de ordenación.  
  
## <a name="example"></a>Ejemplo  

 La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `book` de rango para la `books` colección. La `Order By` cláusula ordena el resultado de la consulta por precio en orden ascendente (el valor predeterminado). Los libros con el mismo precio se ordenan por título en orden ascendente. La `Select` cláusula selecciona las `Title` `Price` propiedades y como los valores devueltos por la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Ejemplo  

 La siguiente expresión de consulta utiliza la `Order By` cláusula para ordenar el resultado de la consulta por precio en orden descendente. Los libros con el mismo precio se ordenan por título en orden ascendente.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Ejemplo  

 La siguiente expresión de consulta utiliza una `Select` cláusula para seleccionar el título del libro, el precio, la fecha de publicación y el autor. A continuación, rellena los `Title` `Price` campos,, `PublishDate` y `Author` de la variable de rango para el nuevo ámbito. La `Order By` cláusula ordena la nueva variable de rango por nombre de autor, título del libro y, a continuación, precio. Cada columna se ordena en el orden predeterminado (ascendente).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula FROM](from-clause.md)
