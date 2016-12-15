---
title: "Type Relationships in Query Operations (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variable relationships [LINQ in Visual Basic]"
  - "type information inferred [LINQ in Visual Basic]"
  - "type relationships [LINQ in Visual Basic]"
  - "queries [LINQ in Visual Basic], type relationships"
  - "data sources [LINQ in Visual Basic], type relationships"
  - "LINQ [Visual Basic], type relationships"
  - "inferring type information [LINQ in Visual Basic]"
  - "relationships [LINQ in Visual Basic]"
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
caps.handback.revision: 32
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type Relationships in Query Operations (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las variables que se usan en las operaciones de consulta de [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] están fuertemente tipadas y deben ser compatibles entre sí.  El tipado fuerte se usa en el origen de datos, en la propia consulta y en la ejecución de la consulta.  La ilustración siguiente identifica los términos que se utilizan para describir una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  Para obtener más información sobre las partes de una consulta, vea [Operaciones básicas de consulta \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Consulta de pseudocódigo con elementos resaltados.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Partes de una consulta LINQ  
  
 El tipo de la variable de rango de la consulta debe ser compatible con el tipo de los elementos del origen de datos.  El tipo de la variable de consulta debe ser compatible con el elemento de secuencia definido en la cláusula `Select`.  Finalmente, el tipo de los elementos de secuencia también debe ser compatible con el tipo de la variable de control del bucle que se utiliza en la instrucción `For Each` que ejecuta la consulta.  Este tipado fuerte facilita la identificación de los errores de tipos en tiempo de compilación.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] simplifica el tipado fuerte al implementar la inferencia de tipo de variable local, lo que también se conoce como *tipo implícito*.  Esta característica se utiliza en el ejemplo anterior y, como observará, se utiliza en los ejemplos y la documentación de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  En Visual Basic, la inferencia de tipo de variable local se consigue simplemente utilizando una instrucción `Dim` sin una cláusula `As`.  En el ejemplo siguiente, `city` está fuertemente tipado como cadena.  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  La inferencia de tipo de variable local sólo funciona cuando `Option Infer` se establece en `On`.  Para obtener más información, consulte [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Sin embargo, aun cuando se utiliza la inferencia de tipo de variable local en una consulta, las mismas relaciones de tipo se encuentran entre las variables del origen de datos, la variable de consulta y el bucle de ejecución de la consulta.  Es útil conocer los fundamentos de estas relaciones de tipos para escribir consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] o trabajar con los ejemplos y ejemplos de código de la documentación.  
  
 Puede que tenga que especificar un tipo explícito para una variable de rango que no coincide con el tipo devuelto por el origen de datos.  Puede especificar el tipo de la variable de rango mediante una cláusula `As`.  Sin embargo, esto hace que se produzca un error si se trata de una [conversión de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y `Option Strict` se ha establecido en `On`.  Por consiguiente, se recomienda realizar la conversión en los valores recuperados del origen de datos.  Puede convertir los valores del origen de datos en el tipo de variable de rango explícito con el método <xref:System.Linq.Enumerable.Cast%2A>.  También puede convertir los valores seleccionados en la cláusula `Select` en un tipo explícito distinto al de la variable de rango.  Estos puntos se reflejan en el código siguiente.  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## Consultas que devuelven elementos completos de los datos de origen  
 En el ejemplo siguiente se muestra una operación de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] que devuelve una secuencia de elementos seleccionados de los datos de origen.  El origen, `names`, contiene una matriz de cadenas y el resultado de la consulta es una secuencia que contiene cadenas que empiezan por la letra M.  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Es equivalente al código siguiente, pero es mucho más corto y más fácil de escribir.  En Visual Basic, se prefiere la inferencia de tipo de variable local en las consultas.  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 En los dos ejemplos de código anteriores existen las siguientes relaciones, se determinen los tipos de forma implícita o explícita.  
  
1.  El tipo de los elementos del origen de datos, `names`, es el tipo de la variable de rango, `name`, en la consulta.  
  
2.  El tipo de objeto seleccionado, `name`, determina el tipo de la variable de consulta, `mNames`.  Aquí `name` es una cadena, por lo que la variable de consulta es IEnumerable\(Of String\) en Visual Basic.  
  
3.  La consulta definida en `mNames` se ejecuta en el bucle `For Each` El bucle recorre en iteración el resultado de ejecutar la consulta.  Dado que `mNames`, cuando se ejecuta, devuelve una secuencia de cadenas, la variable de iteración del bucle, `nm`, también es una cadena.  
  
## Consultas que devuelven un campo de los elementos seleccionados  
 En el ejemplo siguiente se muestra una operación de consulta [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] que devuelve una secuencia que contiene sólo una parte de cada elemento seleccionado del origen de datos.  La consulta utiliza una colección de objetos `Customer` como origen de datos y proyecta sólo la propiedad `Name` en el resultado.  Dado que el nombre del cliente es una cadena, la consulta genera una secuencia de cadenas como resultado.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Las relaciones entre las variables son como las del ejemplo más sencillo.  
  
1.  El tipo de los elementos del origen de datos, `customers`, es el tipo de la variable de rango, `cust`, en la consulta.  En este ejemplo, ese tipo es `Customer`.  
  
2.  La instrucción `Select` devuelve la propiedad `Name` de cada objeto `Customer` en lugar del objeto completo.  Dado que `Name` es una cadena, la variable de consulta, `custNames`, será de nuevo IEnumerable\(Of String\), no `Customer`.  
  
3.  Dado que `custNames` representa una secuencia de cadenas, la variable de iteración del bucle `For Each`, `custName`, debe ser una cadena.  
  
 Sin la inferencia de tipo de variable local, el ejemplo anterior sería más difícil de escribir y de entender, como demuestra el ejemplo siguiente.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Consultas que requieren tipos anónimos  
 En el ejemplo siguiente se muestra una situación más compleja.  En el ejemplo anterior, no era apropiado especificar explícitamente los tipos de todas las variables.  En este ejemplo, no se puede.  En lugar de seleccionar los elementos `Customer` completos del origen de datos o un campo único de cada elemento, la cláusula `Select` de esta consulta devuelve dos propiedades del objeto `Customer` original: `Name` y `City`.  Como respuesta a la cláusula `Select`, el compilador define un tipo anónimo que contiene esas dos propiedades.  El resultado de ejecutar `nameCityQuery` en el bucle `For Each` es una colección de instancias del nuevo tipo anónimo.  Dado que el tipo anónimo no tiene ningún nombre utilizable, no puede especificar explícitamente el tipo de `nameCityQuery` o `custInfo`.  Es decir, con un tipo anónimo, no hay ningún nombre de tipo que se pueda utilizar en lugar de `String` en `IEnumerable(Of String)`.  Para obtener más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Aunque no es posible especificar los tipos de todas las variables en el ejemplo anterior, las relaciones siguen siendo las mismas.  
  
1.  El tipo de los elementos del origen de datos es de nuevo el tipo de la variable de rango de la consulta.  En este ejemplo, `cust` es una instancia de `Customer`.  
  
2.  Dado que la instrucción `Select` genera un tipo anónimo, el tipo de la variable de consulta, `nameCityQuery`, debe declararse implícitamente como un tipo anónimo.  Un tipo anónimo no tiene un nombre utilizable y, por consiguiente, no se puede especificar explícitamente.  
  
3.  El tipo de la variable de iteración en el bucle `For Each` es el tipo anónimo creado en el paso 2.  Dado que el tipo no tiene ningún nombre utilizable, el tipo de la variable de iteración del bucle se debe determinar implícitamente.  
  
## Vea también  
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)