---
title: "Operaciones básicas de consulta (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: 37
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87ff9173b5ff72385c8ecdc3ff13735e7be2a21d
ms.lasthandoff: 03/13/2017

---
# <a name="basic-query-operations-visual-basic"></a>Operaciones básicas de consulta (Visual Basic)
Este tema proporciona una breve introducción a [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] expresiones en Visual Basic y algunos de los tipos de operaciones que se realizan en una consulta. Para obtener más información, vea los temas siguientes:  
  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [Tutorial: Escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Especificar el origen de datos (desde)  
 En un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta, el primer paso es especificar el origen de datos que desea consultar. Por lo tanto, la `From` cláusula en una consulta siempre viene primero. Operadores de consulta seleccionan y forma al resultado basándose en el tipo de origen.  
  
 [!code-vb[1 VbLINQBasicOps](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 El `From` cláusula especifica el origen de datos, `customers`y un *variable de rango*, `cust`. La variable de rango es como una variable de iteración del bucle, excepto que en una expresión de consulta, se produce ninguna iteración real. Cuando se ejecuta la consulta, a menudo mediante un `For Each` el bucle, la variable de rango actúa como una referencia a cada elemento sucesivo de `customers`. Dado que el compilador puede inferir el tipo de `cust`, no es necesario especificar explícitamente. Para obtener ejemplos de las consultas escritas con y sin establecimiento explícito de tipos, vea [relaciones entre tipos en operaciones de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Para obtener más información acerca de cómo utilizar el `From` en Visual Basic, consulte [cláusula From](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtrar datos (dónde)  
 Probablemente la operación de consulta más común es aplicar un filtro en forma de una expresión booleana. La consulta devuelve sólo los elementos para los que la expresión es verdadera. Un `Where` cláusula se utiliza para realizar el filtrado. El filtro especifica qué elementos del origen de datos para incluir en la secuencia resultante. En el ejemplo siguiente, se incluyen sólo los clientes que tienen una dirección en Londres.  
  
 [!code-vb[VbLINQBasicOps&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 Puede usar operadores lógicos como `And` y `Or` para combinar expresiones de filtro en un `Where` cláusula. Por ejemplo, para devolver a sólo los clientes de Londres y cuyo nombre es Devon, utilice el siguiente código:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Para devolver a los clientes de Londres o París, utilice el código siguiente:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Para obtener más información acerca de cómo utilizar el `Where` en Visual Basic, consulte [cláusula Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Ordenar datos (Order By)  
 A menudo es conveniente ordenar los datos devueltos en un orden concreto. El `Order By` cláusula hará que los elementos de la secuencia devuelta se ordenen en un campo o campos especificados. Por ejemplo, la siguiente consulta ordena los resultados según la `Name` propiedad. Porque `Name` es una cadena, los datos devueltos se ordenarán alfabéticamente, de A Z.  
  
 [!code-vb[VbLINQBasicOps&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Para ordenar los resultados en orden inverso, de Z a, utilice el `Order By...Descending` cláusula. El valor predeterminado es `Ascending` cuando ninguno `Ascending` ni `Descending` especificado.  
  
 Para obtener más información acerca de cómo utilizar el `Order By` en Visual Basic, consulte [cláusula Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Seleccionar (Select) de datos  
 El `Select` cláusula especifica la forma y el contenido de elementos devueltos. Por ejemplo, puede especificar si sus resultados estarán compuestos de completa `Customer` objetos, sólo uno `Customer` propiedad, un subconjunto de propiedades, una combinación de propiedades de diversos orígenes de datos o algún tipo de resultado nuevo basado en un cálculo. Cuando el `Select` cláusula genera un valor distinto de una copia del elemento de origen, la operación se denomina un *proyección*.  
  
 Para recuperar una colección formada por completo `Customer` objetos, seleccione la variable de rango:  
  
 [!code-vb[VbLINQBasicOps Nº&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Si un `Customer` instancia es un objeto grande que tiene muchos campos, y todo lo que van a recuperar es el nombre, puede seleccionar `cust.Name`, como se muestra en el ejemplo siguiente. Inferencia de tipo local reconoce que se cambia el tipo de resultado de una colección de `Customer` objetos a una colección de cadenas.  
  
 [!code-vb[VbLINQBasicOps&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Para seleccionar varios campos del origen de datos, tiene dos opciones:  
  
-   En el `Select` cláusula, especificar los campos que desea incluir en el resultado. El compilador definirá un tipo anónimo que tiene esos campos como propiedades. Para obtener más información, consulte [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Dado que los elementos devueltos en el ejemplo siguiente son instancias de un tipo anónimo, imposible hacer referencia al tipo por su nombre en otra parte en el código. El nombre designado por el compilador del tipo contiene caracteres que no son válidos en el código de Visual Basic normal. En el ejemplo siguiente, los elementos de la colección devuelta por la consulta en `londonCusts4` son instancias de un tipo anónimo  
  
     [!code-vb[VbLINQBasicOps Nº&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     O bien  
  
-   Definir un tipo con nombre que contenga los campos concretos que desea incluir en el resultado y cree e inicialice instancias del tipo en el `Select` cláusula. Utilice esta opción sólo si tiene que utilizar los resultados individuales fuera de la colección en la que se devuelven, o si tiene que pasarlos como parámetros en llamadas a métodos. El tipo de `londonCusts5` en el ejemplo siguiente es IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps Nº&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Para obtener más información acerca de cómo utilizar el `Select` en Visual Basic, consulte [cláusula Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Combinar los datos (Join y Group Join)  
 Puede combinar más de un origen de datos en el `From` cláusula de varias maneras. Por ejemplo, el código siguiente utiliza dos orígenes de datos y combina implícitamente las propiedades de ambos en el resultado. La consulta selecciona los estudiantes cuyos apellidos comiencen con una vocal.  
  
 [!code-vb[VbLINQBasicOps&#9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Puede ejecutar este código con la lista de estudiantes creada en [Cómo: crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 El `Join` palabra clave es equivalente a una `INNER JOIN` en SQL. Combina dos colecciones basándose en los valores de clave coincidentes entre los elementos de las dos colecciones. La consulta devuelve todo o parte de los elementos de colección que tienen valores de clave coincidentes. Por ejemplo, el código siguiente duplica la acción de la combinación implícita anterior.  
  
 [!code-vb[VbLINQBasicOps&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join`combina las colecciones en una sola colección jerárquica, igual que un `LEFT JOIN` en SQL. Para obtener más información, consulte [cláusula Join](../../../../visual-basic/language-reference/queries/join-clause.md) y [cláusula Join de grupo](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Agrupar datos (Group By)  
 Puede agregar un `Group By` cláusula para agrupar los elementos de un resultado de consulta según uno o más campos de los elementos. Por ejemplo, el siguiente código agrupa los estudiantes por año de clase.  
  
 [!code-vb[VbLINQBasicOps&#11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 Si ejecuta este código utilizando la lista de estudiantes creada en [Cómo: crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), el resultado de la `For Each` instrucción es:  
  
 Año: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Gustavo  
  
 Tucker, Lance  
  
 Año: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Delia  
  
 Feng, Hanying  
  
 Adams, Terry  
  
 Año: Freshman  
  
 Maldonado Guerra, Sven  
  
 Garcia, Cesar  
  
 La variación que se muestra en el código siguiente ordena los años de clase y, a continuación, ordena los estudiantes de cada año por apellido.  
  
 [!code-vb[VbLINQBasicOps&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Para obtener más información acerca de `Group By`, consulte [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
