---
title: Operaciones básicas de consulta
ms.date: 07/20/2015
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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266383"
---
# <a name="basic-query-operations-visual-basic"></a>Operaciones básicas de consulta (Visual Basic)
En este tema se proporciona una breve introducción a las expresiones de Language-Integrated Query (LINQ) en Visual Basic y a algunos de los tipos típicos de operaciones que se realizan en una consulta. Para obtener más información, vea los temas siguientes:  
  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Consultas](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Tutorial: Escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Especificación del origen de datos (desde)  
 En una consulta LINQ, el primer paso es especificar el origen de datos que desea consultar. Por lo `From` tanto, la cláusula de una consulta siempre es lo primero. Los operadores de consulta seleccionan y dan forma al resultado en función del tipo de origen.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 La `From` cláusula especifica el `customers`origen de datos `cust`, y una variable de *rango*, . La variable de rango es como una variable de iteración de bucle, excepto que en una expresión de consulta, no se produce ninguna iteración real. Cuando se ejecuta la consulta, `For Each` a menudo mediante un bucle, la `customers`variable de rango sirve como referencia a cada elemento sucesivo en . Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente. Para obtener ejemplos de consultas escritas con y sin escritura explícita, vea Relaciones de tipo en operaciones de [consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Para obtener más información `From` acerca de cómo usar la cláusula en Visual Basic, vea [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtrado de datos (dónde)  
 Probablemente la operación de consulta más común es aplicar un filtro en forma de una expresión booleana. A continuación, la consulta devuelve solo los elementos para los que la expresión es true. Se `Where` utiliza una cláusula para realizar el filtrado. El filtro especifica qué elementos del origen de datos se incluirán en la secuencia resultante. En el ejemplo siguiente, solo se incluyen los clientes que tienen una dirección en Londres.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Puede utilizar operadores `And` lógicos como y `Or` `Where` combinar expresiones de filtro en una cláusula. Por ejemplo, para devolver solo aquellos clientes que son de Londres y cuyo nombre es Devon, utilice el código siguiente:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 Para devolver clientes de Londres o París, utilice el siguiente código:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 Para obtener más información `Where` acerca de cómo usar la cláusula en Visual Basic, vea [Cláusula Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Datos de pedido (pedido por)  
 A menudo es conveniente ordenar los datos devueltos en un orden determinado. La `Order By` cláusula hará que los elementos de la secuencia devuelta se ordenen en un campo o campos especificados. Por ejemplo, la siguiente consulta ordena `Name` los resultados en función de la propiedad. Dado `Name` que es una cadena, los datos devueltos se ordenarán alfabéticamente, de la A a la Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Para ordenar los resultados en orden inverso, de la Z a la A, use la cláusula `Order By...Descending`. El valor `Ascending` predeterminado `Ascending` `Descending` es cuando no se especifica ni se especifica.  
  
 Para obtener más información `Order By` acerca de cómo usar la cláusula en Visual Basic, vea [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Selección de datos (Seleccionar)  
 La `Select` cláusula especifica el formulario y el contenido de los elementos devueltos. Por ejemplo, puede especificar si los `Customer` resultados consistirán `Customer` en objetos completos, una sola propiedad, un subconjunto de propiedades, una combinación de propiedades de varios orígenes de datos o algún nuevo tipo de resultado basado en un cálculo. Cuando la cláusula `Select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*.  
  
 Para recuperar una colección `Customer` que consta de objetos completos, seleccione la propia variable de rango:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Si `Customer` una instancia es un objeto grande que tiene muchos campos y todo `cust.Name`lo que desea recuperar es el nombre, puede seleccionar , como se muestra en el ejemplo siguiente. La inferencia de tipo local reconoce que esto `Customer` cambia el tipo de resultado de una colección de objetos a una colección de cadenas.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Para seleccionar varios campos del origen de datos, tiene dos opciones:  
  
- En `Select` la cláusula, especifique los campos que desea incluir en el resultado. El compilador definirá un tipo anónimo que tiene esos campos como sus propiedades. Para obtener más información, consulte [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) (Guía de programación de C#).  
  
     Dado que los elementos devueltos en el ejemplo siguiente son instancias de un tipo anónimo, no puede hacer referencia al tipo por nombre en otro lugar del código. El nombre designado por el compilador para el tipo contiene caracteres que no son válidos en el código normal de Visual Basic. En el ejemplo siguiente, los elementos de la `londonCusts4` colección devueltos por la consulta son instancias de un tipo anónimo  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     O bien  
  
- Defina un tipo con nombre que contenga los campos concretos que desea incluir en `Select` el resultado y cree e inicialice instancias del tipo en la cláusula. Utilice esta opción solo si tiene que usar resultados individuales fuera de la colección en la que se devuelven, o si tiene que pasarlos como parámetros en las llamadas a métodos. El tipo `londonCusts5` de en el ejemplo siguiente es IEnumerable(Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Para obtener más información `Select` acerca de cómo usar la cláusula en Visual Basic, vea [Seleccionar cláusula](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Unirdatos (unirse y unirse a grupos)  
 Puede combinar más de un `From` origen de datos en la cláusula de varias maneras. Por ejemplo, el código siguiente utiliza dos orígenes de datos y combina implícitamente propiedades de ambos en el resultado. La consulta selecciona los alumnos cuyos apellidos comienzan con una vocal.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> Puede ejecutar este código con la lista de alumnos creados en [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 La `Join` palabra clave `INNER JOIN` es equivalente a un en SQL. Combina dos colecciones basadas en valores de clave coincidentes entre los elementos de las dos colecciones. La consulta devuelve todos o parte de los elementos de colección que tienen valores de clave coincidentes. Por ejemplo, el código siguiente duplica la acción de la combinación implícita anterior.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`combina colecciones en una única colección jerárquica, al igual que una `LEFT JOIN` en SQL. Para obtener más información, consulte Cláusula de [unión](../../../../visual-basic/language-reference/queries/join-clause.md) y Cláusula de [unión de grupo](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Agrupar datos (Agrupar por)  
 Puede agregar `Group By` una cláusula para agrupar los elementos de un resultado de consulta según uno o varios campos de los elementos. Por ejemplo, el código siguiente agrupa a los alumnos por año de clase.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Si ejecuta este código utilizando la lista de alumnos creados en `For Each` [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), la salida de la instrucción es:  
  
 Año: Junior  
  
 Tucker, Michael  
  
 García, Hugo  
  
 García, Debra  
  
 Tucker, Lance  
  
 Año: Senior  
  
 Omelchenko  
  
 Osada  
  
 Fakhouri  
  
 Feng  
  
 Adams, Terry  
  
 Año: Primer año  
  
 Mortensen  
  
 García, Cesar  
  
 La variación que se muestra en el código siguiente ordena los años de clase y, a continuación, ordena a los alumnos dentro de cada año por apellido.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Para obtener `Group By`más información acerca de , consulte [Agrupar por cláusula](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Collections.Generic.IEnumerable%601>
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
