---
title: Relaciones de tipos en operaciones de consulta (Visual Basic) | Documentos de Microsoft
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
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
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
ms.openlocfilehash: a966b69feca7a7021cafbccb7971913ea781c479
ms.lasthandoff: 03/13/2017

---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Relaciones entre tipos en operaciones de consulta (Visual Basic)
Las variables usadas en [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] consulta operaciones están fuertemente tipadas y deben ser compatibles entre sí. Establecimiento inflexible de tipos se utiliza en el origen de datos, en la propia consulta y en la ejecución de consultas. La ilustración siguiente identifica los términos utilizados para describir un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta. Para obtener más información acerca de los elementos de una consulta, vea [operaciones básicas de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Consulta de pseudocódigo con elementos resaltados.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Partes de una consulta LINQ  
  
 El tipo de la variable de rango en la consulta debe ser compatible con el tipo de los elementos del origen de datos. El tipo de la variable de consulta debe ser compatible con el elemento de secuencia definido en el `Select` cláusula. Por último, el tipo de los elementos de secuencia también debe ser compatible con el tipo de la variable de control de bucle que se utiliza en el `For Each` instrucción que ejecuta la consulta. Establecimiento inflexible de tipos facilita la identificación de errores de tipo en tiempo de compilación.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]hace establecimiento inflexible de tipos adecuada al implementar la inferencia de tipo local, también conocido como *tipos implícitos*. Que se usa la característica en el ejemplo anterior y verá que se utiliza en el [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] ejemplos y documentación. En Visual Basic, la inferencia de tipo local se logra simplemente mediante una `Dim` instrucción sin un `As` cláusula. En el ejemplo siguiente, `city` está fuertemente tipada como una cadena.  
  
 [!code-vb[1 VbLINQTypeRels](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  Inferencia de tipo local sólo funciona cuando `Option Infer` está establecido en `On`. Para obtener más información, consulte [Option Infer instrucción](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Sin embargo, incluso si utiliza la inferencia de tipo local en una consulta, las mismas relaciones de tipo están presentes entre las variables en el origen de datos, la variable de consulta y el bucle de ejecución de la consulta. Resulta útil tener un conocimiento básico de estas relaciones de tipos cuando se escribe [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultas o trabajar con los ejemplos y ejemplos de código en la documentación.  
  
 Debe especificar un tipo explícito para una variable de rango que no coincide con el tipo devuelto desde el origen de datos. Puede especificar el tipo de la variable de rango mediante una `As` cláusula. Sin embargo, esto produce un error si la conversión es un [conversión de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y `Option Strict` está establecido en `On`. Por lo tanto, se recomienda realizar la conversión en los valores recuperados del origen de datos. Puede convertir los valores del origen de datos para el tipo de variable de rango explícito mediante el <xref:System.Linq.Enumerable.Cast%2A>método.</xref:System.Linq.Enumerable.Cast%2A> También puede convertir los valores seleccionados en el `Select` cláusula para un tipo explícito que sea diferente del tipo de la variable de rango. Estos puntos se reflejan en el código siguiente.  
  
 [!code-vb[VbLINQTypeRels Nº&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Consultas que devuelven elementos completos de los datos de origen  
 El ejemplo siguiente muestra un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] operación que devuelve una secuencia de elementos seleccionados del origen de datos de consulta. El origen, `names`, contiene una matriz de cadenas, y el resultado de la consulta es una secuencia que contiene cadenas que empiezan por la letra M.  
  
 [!code-vb[VbLINQTypeRels&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Esto es equivalente al código siguiente, pero es mucho más corto y más fácil de escribir. Dependencia de la inferencia de tipo local en las consultas es el estilo preferido en Visual Basic.  
  
 [!code-vb[VbLINQTypeRels&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 Existen las siguientes relaciones en ambos ejemplos de código anteriores, si se determinan los tipos de forma implícita o explícita.  
  
1.  El tipo de los elementos del origen de datos, `names`, es el tipo de la variable de rango, `name`, en la consulta.  
  
2.  El tipo del objeto seleccionado, `name`, determina el tipo de la variable de consulta, `mNames`. Aquí `name` es una cadena, por lo que la variable de consulta es IEnumerable (Of String) en Visual Basic.  
  
3.  La consulta definida en `mNames` se ejecuta en el `For Each` bucle. El bucle recorre en iteración el resultado de ejecutar la consulta. Porque `mNames`, cuando se ejecuta, devuelve una secuencia de cadenas, la variable de iteración del bucle, `nm`, también es una cadena.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Consultas que devuelven un campo de los elementos seleccionados  
 El ejemplo siguiente muestra un [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] operación que devuelve una secuencia que contiene sólo una parte de cada elemento seleccionado del origen de datos de consulta. La consulta toma una colección de `Customer` objetos como origen de datos y proyectos de sólo el `Name` propiedad en el resultado. Dado que el nombre del cliente es una cadena, la consulta genera una secuencia de cadenas como resultado.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Las relaciones entre las variables son como las del ejemplo más sencillo.  
  
1.  El tipo de los elementos del origen de datos, `customers`, es el tipo de la variable de rango, `cust`, en la consulta. En este ejemplo, que es de tipo `Customer`.  
  
2.  El `Select` instrucción devuelve el `Name` propiedad de cada `Customer` objeto en lugar de todo el objeto. Porque `Name` es una cadena, la variable de consulta, `custNames`, volverán a ser IEnumerable (Of String), no de `Customer`.  
  
3.  Porque `custNames` representa una secuencia de cadenas, la `For Each` variable de iteración del bucle, `custName`, debe ser una cadena.  
  
 Sin la inferencia de tipo local, el ejemplo anterior sería más difícil de escribir y comprender, como se muestra en el ejemplo siguiente.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="queries-that-require-anonymous-types"></a>Consultas que requieren tipos anónimos  
 En el ejemplo siguiente se muestra una situación más compleja. En el ejemplo anterior, no era apropiado especificar explícitamente los tipos de todas las variables. En este ejemplo, es imposible. En lugar de seleccionar todo `Customer` elementos desde el origen de datos o un campo único de cada elemento, la `Select` cláusula en esta consulta devuelve dos propiedades del original `Customer` objeto: `Name` y `City`. En respuesta a la `Select` cláusula, el compilador define un tipo anónimo que contiene esas dos propiedades. El resultado de ejecutar `nameCityQuery` en el `For Each` bucle es una colección de instancias del nuevo tipo anónimo. Dado que el tipo anónimo no tiene ningún nombre utilizable, no puede especificar el tipo de `nameCityQuery` o `custInfo` explícitamente. Es decir, con un tipo anónimo, no tiene ningún nombre de tipo para usar en lugar de `String` en `IEnumerable(Of String)`. Para obtener más información, consulte [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Aunque no es posible especificar los tipos de todas las variables en el ejemplo anterior, las relaciones siguen siendo los mismos.  
  
1.  El tipo de los elementos del origen de datos nuevo es el tipo de la variable de rango en la consulta. En este ejemplo, `cust` es una instancia de `Customer`.  
  
2.  Dado que la `Select` instrucción genera un tipo anónimo, la variable de consulta, `nameCityQuery`, debe declararse implícitamente como un tipo anónimo. Un tipo anónimo no tiene ningún nombre utilizable y, por tanto, no se puede especificar explícitamente.  
  
3.  El tipo de la variable de iteración en la `For Each` bucle es el tipo anónimo creado en el paso 2. Dado que el tipo no tiene ningún nombre utilizable, implícitamente se determinará el tipo de la variable de iteración del bucle.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)
