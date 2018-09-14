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
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45609877"
---
# <a name="order-by-clause-visual-basic"></a>Order By (Cláusula, Visual Basic)
Especifica el criterio de ordenación para un resultado de la consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Elementos  
 `orderExp1`  
 Requerido. Uno o varios campos del resultado de la consulta actual que identifican cómo ordenar los valores devueltos. Los nombres de campo deben estar separados por comas (,). Puede identificar cada campo ordenado en orden ascendente o descendente mediante el uso de la `Ascending` o `Descending` palabras clave. Si no hay ningún `Ascending` o `Descending` se especifica la palabra clave, el criterio de ordenación predeterminado es ascendente. Los campos del criterio de ordenación tienen precedencia de izquierda a derecha.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Order By` cláusula para ordenar los resultados de una consulta. El `Order By` cláusula solo puede ordenar un resultado basado en la variable de rango para el ámbito actual. Por ejemplo, el `Select` cláusula presenta un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para ese ámbito. Las variables definidas antes de rango un `Select` cláusula en una consulta no están disponibles después de la `Select` cláusula. Por lo tanto, si desea ordenar los resultados por un campo que no está disponible en el `Select` cláusula, debe colocar el `Order By` cláusula antes el `Select` cláusula. Un ejemplo de cuándo se tendría que hacer esto es cuando desea ordenar la consulta por campos que no se devuelven como parte del resultado.  
  
 Orden ascendente y descendente para un campo está determinado por la implementación de la <xref:System.IComparable> interfaz para el tipo de datos del campo. Si el tipo de datos no implementa la <xref:System.IComparable> se omite la interfaz, el criterio de ordenación.  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `book` para el `books` colección. El `Order By` cláusula ordena el resultado de la consulta por precio ascendente (el valor predeterminado). Los libros en pantalla con el mismo precio se ordenan por título en orden ascendente. El `Select` cláusula selecciona el `Title` y `Price` propiedades como los valores devueltos por la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza el `Order By` cláusula para ordenar el resultado de la consulta por precio en orden descendente. Los libros en pantalla con el mismo precio se ordenan por título en orden ascendente.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `Select` cláusula para seleccionar el título del libro, precio, fecha de publicación y crear. A continuación, rellena el `Title`, `Price`, `PublishDate`, y `Author` campos de la variable de rango del nuevo ámbito. El `Order By` cláusula ordena la nueva variable de rango por el nombre del autor, título de libro y, a continuación, el precio. Cada columna está ordenada en el orden predeterminado (ascendente).  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/index.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
