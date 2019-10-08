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
ms.openlocfilehash: f8ee46b12e84f99629c3a92057fc3a7bb8a3c2e8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004954"
---
# <a name="order-by-clause-visual-basic"></a>Order By (Cláusula, Visual Basic)
Especifica el criterio de ordenación para el resultado de una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Elementos  
 `orderExp1`  
 Obligatorio. Uno o más campos del resultado de la consulta actual que identifican cómo ordenar los valores devueltos. Los nombres de campo deben estar separados por comas (,). Puede identificar cada campo como ordenado en orden ascendente o descendente mediante el uso de las palabras clave `Ascending` o `Descending`. Si no se especifica ninguna palabra clave `Ascending` o `Descending`, el criterio de ordenación predeterminado es ascendente. Los campos de criterio de ordenación tienen prioridad de izquierda a derecha.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la cláusula `Order By` para ordenar los resultados de una consulta. La cláusula `Order By` solo puede ordenar un resultado en función de la variable de rango del ámbito actual. Por ejemplo, la cláusula `Select` introduce un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para ese ámbito. Las variables de rango definidas antes de una cláusula `Select` en una consulta no están disponibles después de la cláusula `Select`. Por lo tanto, si desea ordenar los resultados por un campo que no está disponible en la cláusula `Select`, debe colocar la cláusula `Order By` antes de la cláusula @no__t 2. Un ejemplo de Cuándo tendría que hacer esto es cuando desea ordenar la consulta por campos que no se devuelven como parte del resultado.  
  
 El orden ascendente y descendente de un campo viene determinado por la implementación de la interfaz <xref:System.IComparable> para el tipo de datos del campo. Si el tipo de datos no implementa la interfaz <xref:System.IComparable>, se omite el criterio de ordenación.  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `book` para la colección `books`. La cláusula `Order By` ordena el resultado de la consulta por precio en orden ascendente (el valor predeterminado). Los libros con el mismo precio se ordenan por título en orden ascendente. La cláusula `Select` selecciona las propiedades `Title` y `Price` como los valores devueltos por la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta utiliza la cláusula `Order By` para ordenar el resultado de la consulta por precio en orden descendente. Los libros con el mismo precio se ordenan por título en orden ascendente.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta usa una cláusula `Select` para seleccionar el título del libro, el precio, la fecha de publicación y el autor. A continuación, rellena los campos `Title`, `Price`, `PublishDate` y `Author` de la variable de rango para el nuevo ámbito. La cláusula `Order By` ordena la nueva variable de rango por nombre de autor, título del libro y, a continuación, precio. Cada columna se ordena en el orden predeterminado (ascendente).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
