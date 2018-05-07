---
title: Order By (Cláusula, Visual Basic)
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
ms.openlocfilehash: 7c60156ee81618530b42d5f61dbcac6f59c4f675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="order-by-clause-visual-basic"></a>Order By (Cláusula, Visual Basic)
Especifica el criterio de ordenación para un resultado de consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Elementos  
 `orderExp1`  
 Requerido. Uno o varios campos de resultados de la consulta actual que identifican cómo ordenar los valores devueltos. Los nombres de campo deben estar separados por comas (,). Puede identificar cada campo en orden ascendente o descendente mediante el uso de la `Ascending` o `Descending` palabras clave. Si no hay ningún `Ascending` o `Descending` se especifica la palabra clave, el criterio de ordenación predeterminado es ascendente. Los campos de criterio de ordenación tienen prioridad, de izquierda a derecha.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Order By` cláusula para ordenar los resultados de una consulta. El `Order By` cláusula sólo puede ordenar un resultado basándose en la variable de rango para el ámbito actual. Por ejemplo, el `Select` cláusula incluye un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para ese ámbito. Las variables definidas antes de rango un `Select` cláusula en una consulta no están disponibles después de la `Select` cláusula. Por lo tanto, si desea ordenar los resultados por un campo que no está disponible en la `Select` cláusula, se debe incluir el `Order By` cláusula antes de la `Select` cláusula. Un ejemplo de cuándo tendría que hacer esto es si desea ordenar la consulta por campos que no se devuelven como parte del resultado.  
  
 Orden ascendente y descendente en un campo se determina mediante la implementación de la <xref:System.IComparable> interfaz para el tipo de datos del campo. Si el tipo de datos no implementa la <xref:System.IComparable> se omite la interfaz, el criterio de ordenación.  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `book` para el `books` colección. El `Order By` cláusula ordena el resultado de la consulta por precio de forma ascendente (el valor predeterminado). Libros con el mismo precio se ordenan por título en orden ascendente. El `Select` cláusula selecciona el `Title` y `Price` propiedades como los valores devueltos por la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza el `Order By` cláusula para ordenar el resultado de la consulta por precio en orden descendente. Libros con el mismo precio se ordenan por título en orden ascendente.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `Select` cláusula para seleccionar el título del libro, precio, fecha de publicación y crear. A continuación, rellena la `Title`, `Price`, `PublishDate`, y `Author` campos de la variable de rango para el nuevo ámbito. El `Order By` cláusula ordena la nueva variable de rango por nombre de autor, título del libro y, a continuación, precio. Cada columna está ordenada en el orden predeterminado (ascendente).  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
