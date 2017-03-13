---
title: "Operaciones b&#225;sicas de consulta (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "orígenes de datos [LINQ en Visual Basic]"
  - "Join (cláusula) [LINQ en Visual Basic]"
  - "ordenar datos [LINQ en Visual Basic]"
  - "proyecciones [LINQ in Visual Basic]"
  - "LINQ [Visual Basic], operaciones de consulta"
  - "Order By (cláusula) [LINQ en Visual Basic]"
  - "combinar datos [LINQ en Visual Basic]"
  - "consultas [LINQ en Visual Basic], operaciones básicas"
  - "seleccionar datos [LINQ en Visual Basic]"
  - "Group By (cláusula) [LINQ en Visual Basic]"
  - "agrupar datos [LINQ en Visual Basic]"
  - "Select (cláusula) [LINQ en Visual Basic]"
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 35
---
# Operaciones b&#225;sicas de consulta (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este tema se proporciona una breve introducción a las expresiones [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] en Visual Basic y algunos de los tipos de operaciones que suelen realizarse en las consultas.  Para obtener más información, vea los temas siguientes:  
  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [Tutorial: Escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## Especificar el origen de datos \(From\)  
 En una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], el primer paso es especificar el origen de datos que se desea consultar.  Por consiguiente, la cláusula de `From` en una consulta incluye siempre primero. Vea operadores seleccionar y calcula el resultado basándose en el tipo de origen.  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 La cláusula `From` especifica el origen de datos, `customers`, y una *variable de rango*, `cust`.  La variable de rango es como una variable de iteración de bucle, con la diferencia de que, en una expresión de consulta, realmente no se produce ninguna iteración.  Cuando se ejecuta la consulta, a menudo mediante un bucle `For Each`, la variable de rango actúa como referencia para cada elemento sucesivo de `customers`.  Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente.  Para obtener ejemplos de consultas escritas con y sin establecimiento inflexible de tipos, vea [Type Relationships in Query Operations \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Para obtener más información sobre cómo utilizar la cláusula `From` en Visual Basic, vea [From \(Cláusula\)](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## Filtrar los datos \(Where\)  
 Probablemente la operación de consulta más común es aplicar un filtro en forma de expresión booleana.  Así, la consulta devuelve sólo los elementos para los que la expresión es verdadera.  La cláusula `Where` se utiliza para realizar el filtrado.  El filtro especifica qué elementos del origen de datos se incluirán en la secuencia resultante.  En el ejemplo siguiente, sólo se incluyen los clientes que tienen una dirección en Londres \(London\).  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 Puede utilizar operadores lógicos como `And` y `Or` para combinar expresiones de filtro en una cláusula `Where`.  Por ejemplo, para devolver sólo los clientes de Londres que se llamen Devon, utilice el código siguiente:  
  
```vb#  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Para devolver los clientes de Londres o París, utilice el código siguiente:  
  
```vb#  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Para obtener más información sobre cómo utilizar la cláusula `Where` en Visual Basic, vea [Where \(Cláusula\)](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## Ordenar los datos \(Order By\)  
 A menudo es útil ordenar los datos devueltos según un criterio determinado.  La cláusula `Order By` hará que se ordenen los elementos de la secuencia devuelta según uno o varios campos que se especifiquen.  Por ejemplo, la consulta siguiente ordena los resultados según la propiedad `Name`.  Dado que `Name` es una cadena, los datos devueltos se ordenarán alfabéticamente, de la A a la Z.  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Para ordenar los resultados en orden inverso, de la Z a la A, utilice la cláusula `Order By...Descending`.  Cuando no se especifica `Ascending` ni `Descending`, se usa `Ascending` de manera predeterminada.  
  
 Para obtener más información sobre cómo utilizar la cláusula `Order By` en Visual Basic, vea [Order By \(Cláusula\)](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## Seleccionar los datos \(Select\)  
 La cláusula `Select` especifica la forma y el contenido de los elementos devueltos.  Por ejemplo, puede especificar si sus resultados estarán formados por objetos `Customer` completos, sólo una propiedad `Customer`, un subconjunto de propiedades, una combinación de propiedades de varios orígenes de datos o algún tipo de resultado nuevo basado en un cálculo.  Cuando la cláusula `Select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*.  
  
 Para recuperar una colección formada por objetos `Customer` completos, seleccione la variable de rango:  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Si una instancia de `Customer` es un objeto grande con muchos campos y lo único que desea recuperar es el nombre, puede seleccionar `cust.Name`, como se muestra en el ejemplo siguiente.  La inferencia de tipo de variable local reconoce que se cambia el tipo de resultado de una colección de objetos `Customer` a una colección de cadenas.  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Para seleccionar varios campos del origen de datos, tiene dos opciones:  
  
-   En la cláusula `Select`, especifique los campos que desea incluir en el resultado.  El compilador definirá un tipo anónimo que tiene esos campos como propiedades.  Para obtener más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Dado que los elementos devueltos en el ejemplo siguiente son instancias de un tipo anónimo, no puede hacer referencia al tipo por su nombre en ninguna otra parte del código.  El nombre designado para el tipo por el compilador contiene caracteres que no son válidos en el código de Visual Basic normal.  En el ejemplo siguiente, los elementos de la colección devuelta por la consulta en `londonCusts4` son todos instancias de un tipo anónimo.  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     O bien  
  
-   Defina un tipo con nombre que contenga los campos concretos que desea incluir en el resultado y cree e inicialice instancias del tipo en la cláusula `Select`.  Utilice esta opción sólo si tiene que utilizar los resultados individuales fuera de la colección en la que se devuelven, o si tiene que pasarlos como parámetros en llamadas a método.  El tipo de `londonCusts5` en el ejemplo siguiente es IEnumerable\(Of NamePhone\).  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Para obtener más información sobre cómo utilizar la cláusula `Select` en Visual Basic, vea [Select \(Cláusula\)](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## Combinar los datos \(Join y Group Join\)  
 Puede combinar más de un origen de datos en la cláusula `From` de varias maneras.  Por ejemplo, el código siguiente utiliza dos orígenes de datos y combina implícitamente las propiedades de ambos en el resultado.  La consulta selecciona los estudiantes cuyos apellidos empiezan por vocal.  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Puede ejecutar este código con la lista de estudiantes creada en [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 La palabra clave `Join` es equivalente a `INNER JOIN` en SQL.  Combina dos colecciones según los valores de clave coincidentes entre los elementos de las dos colecciones.  La consulta devuelve la totalidad o una parte de los elementos de la colección que tienen valores de clave coincidentes.  Por ejemplo, el código siguiente duplica la acción de la combinación implícita anterior.  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join` combina las colecciones en una sola colección jerárquica, igual que `LEFT JOIN` en SQL.  Para obtener más información, consulte [Join \(Cláusula\)](../../../../visual-basic/language-reference/queries/join-clause.md) y [Group Join \(Cláusula\)](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## Agrupar los datos \(Group By\)  
 Puede agregar una cláusula `Group By` para agrupar los elementos de un resultado de consulta según uno o más campos de los elementos.  Por ejemplo, el código siguiente agrupa los estudiantes por año de clase.  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 Si ejecuta este código utilizando la lista de estudiantes creada en [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), el resultado de la instrucción `For Each` es:  
  
 Year: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Year: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng, Hanying  
  
 Adams, Terry  
  
 Year: Freshman  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 La variación mostrada en el código siguiente ordena los años de clase y, a continuación, ordena los estudiantes de cada año por apellido.  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Para obtener más información sobre `Group By`, vea [Group By \(Cláusula\)](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## Vea también  
 <xref:System.Collections.Generic.IEnumerable%601>   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Basic LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)