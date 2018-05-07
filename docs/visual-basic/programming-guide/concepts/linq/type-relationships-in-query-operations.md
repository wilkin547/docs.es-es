---
title: Relaciones entre tipos en operaciones de consulta (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: ed0072eeb44a17201ddab2af6f6a44fd14461029
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Relaciones entre tipos en operaciones de consulta (Visual Basic)
Las variables utilizadas en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] consulta operaciones están fuertemente tipadas y deben ser compatibles entre sí. Establecimiento inflexible de tipos se usa en el origen de datos, en la propia consulta y en la ejecución de la consulta. La ilustración siguiente identifica los términos que se usan para describir un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta. Para obtener más información acerca de las partes de una consulta, vea [operaciones básicas de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Consulta de pseudocódigo con elementos resaltados. ] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Partes de una consulta LINQ  
  
 El tipo de la variable de rango en la consulta debe ser compatible con el tipo de los elementos del origen de datos. El tipo de la variable de consulta debe ser compatible con el elemento de secuencia definido en el `Select` cláusula. Por último, el tipo de los elementos de secuencia también debe ser compatible con el tipo de la variable de control de bucle que se utiliza en el `For Each` instrucción que ejecuta la consulta. Este establecimiento inflexible de tipos facilita la identificación de los errores de tipo en tiempo de compilación.  
  
 Visual Basic, establecimiento inflexible de tipos fácil implementando la inferencia de tipo local, también conocido como *tipos implícitos*. Que se usa la característica en el ejemplo anterior y verá que se utilizan a lo largo del [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] documentación y ejemplos. En Visual Basic, la inferencia de tipo local se logra simplemente mediante un `Dim` instrucción sin un `As` cláusula. En el ejemplo siguiente, `city` está fuertemente tipado como una cadena.  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  Inferencia de tipo local sólo funcionará cuando `Option Infer` está establecido en `On`. Para obtener más información, consulte [Option Infer instrucción](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Sin embargo, incluso si utiliza la inferencia de tipo local en una consulta, las mismas relaciones de tipo están presentes entre las variables en el origen de datos, la variable de consulta y el bucle de ejecución de consulta. Resulta útil tener un conocimiento básico de estas relaciones de tipo cuando se escribe [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consultas o trabajar con los ejemplos y ejemplos de código en la documentación.  
  
 Debe especificar un tipo explícito para una variable de rango que no coincide con el tipo devuelto desde el origen de datos. Puede especificar el tipo de la variable de rango mediante una `As` cláusula. Sin embargo, esto provoca un error si la conversión es un [conversión de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y `Option Strict` está establecido en `On`. Por lo tanto, se recomienda realizar la conversión en los valores recuperados del origen de datos. Puede convertir los valores del origen de datos para el tipo de variable de rango explícito mediante el <xref:System.Linq.Enumerable.Cast%2A> método. También puede convertir los valores seleccionados en el `Select` cláusula para un tipo explícito que sea diferente del tipo de la variable de rango. Estos puntos se reflejan en el código siguiente.  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Consultas que devuelven elementos completos de los datos de origen  
 El ejemplo siguiente muestra un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] operación que devuelve una secuencia de elementos seleccionados del origen de datos de consulta. El origen, `names`, contiene una matriz de cadenas, y el resultado de la consulta es una secuencia que contiene las cadenas que empiecen por la letra M.  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Esto es equivalente al código siguiente, pero es mucho más cortos y fáciles de escribir. Dependencia de la inferencia de tipo local en las consultas es el estilo preferido en Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 Las siguientes relaciones existen en ambos de los ejemplos de código anterior, si se determinan los tipos de forma implícita o explícita.  
  
1.  El tipo de los elementos del origen de datos, `names`, es el tipo de la variable de rango, `name`, en la consulta.  
  
2.  El tipo del objeto que se selecciona, `name`, determina el tipo de la variable de consulta, `mNames`. Aquí `name` es una cadena, por lo que la variable de consulta es IEnumerable (Of String) en Visual Basic.  
  
3.  La consulta definida en `mNames` se ejecuta en el `For Each` bucle. El bucle recorre en iteración el resultado de ejecutar la consulta. Dado que `mNames`, cuando se ejecuta, devuelve una secuencia de cadenas, la variable de iteración del bucle, `nm`, también es una cadena.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Consultas que devuelven un campo de elementos seleccionados  
 El ejemplo siguiente muestra un [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operación que devuelve una secuencia que contiene solo una parte de cada elemento seleccionado en el origen de datos de consulta. La consulta toma una colección de `Customer` objetos como origen de datos y solo para proyectos de la `Name` propiedad en el resultado. Dado que el nombre del cliente es una cadena, la consulta genera una secuencia de cadenas como salida.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim custNames = From cust In customers   
                Where cust.City = "London"   
                Select cust.Name  
  
For Each custName In custNames  
    Console.WriteLine(custName)  
Next  
```  
  
 Las relaciones entre las variables son similares a las del ejemplo más sencillo.  
  
1.  El tipo de los elementos del origen de datos, `customers`, es el tipo de la variable de rango, `cust`, en la consulta. En este ejemplo, que es de tipo `Customer`.  
  
2.  El `Select` instrucción devuelve el `Name` propiedad de cada `Customer` objeto en lugar de todo el objeto. Dado que `Name` es una cadena, la variable de consulta, `custNames`, volverá a estar IEnumerable (Of String), no de `Customer`.  
  
3.  Dado que `custNames` representa una secuencia de cadenas, la `For Each` variable de iteración del bucle, `custName`, debe ser una cadena.  
  
 Sin la inferencia de tipo local, el ejemplo anterior sería más difícil de escribir y comprender, como se muestra en el ejemplo siguiente.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()  
 Dim custNames As IEnumerable(Of String) =  
     From cust As Customer In customers   
     Where cust.City = "London"   
     Select cust.Name  
  
 For Each custName As String In custNames  
     Console.WriteLine(custName)  
 Next  
```  
  
## <a name="queries-that-require-anonymous-types"></a>Consultas que requieren tipos anónimos  
 En el ejemplo siguiente se muestra una situación más compleja. En el ejemplo anterior, es conveniente especificar explícitamente los tipos de todas las variables. En este ejemplo, es imposible. En lugar de seleccionar todo `Customer` elementos desde el origen de datos o un campo único de cada elemento, el `Select` cláusula en esta consulta devuelve dos propiedades de la versión original `Customer` objeto: `Name` y `City`. En respuesta a la `Select` cláusula, el compilador define un tipo anónimo que contiene esas dos propiedades. El resultado de ejecutar `nameCityQuery` en el `For Each` bucle es una colección de instancias del nuevo tipo anónimo. Dado que el tipo anónimo no tiene ningún nombre utilizable, no se puede especificar el tipo de `nameCityQuery` o `custInfo` explícitamente. Es decir, con un tipo anónimo, no tiene ningún nombre de tipo que se utilizará en lugar de `String` en `IEnumerable(Of String)`. Para más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim nameCityQuery = From cust In customers   
                    Where cust.City = "London"   
                    Select cust.Name, cust.City  
  
For Each custInfo In nameCityQuery  
    Console.WriteLine(custInfo.Name)  
Next  
```  
  
 Aunque no es posible especificar tipos para todas las variables en el ejemplo anterior, las relaciones siguen siendo los mismos.  
  
1.  El tipo de los elementos del origen de datos nuevo es el tipo de la variable de rango en la consulta. En este ejemplo, `cust` es una instancia de `Customer`.  
  
2.  Dado que la `Select` instrucción genera un tipo anónimo, la variable de consulta, `nameCityQuery`, debe escribirse de forma implícita como un tipo anónimo. Un tipo anónimo no tiene ningún nombre utilizable y, por tanto, no se puede especificar explícitamente.  
  
3.  El tipo de la variable de iteración en la `For Each` bucle es el tipo anónimo creado en el paso 2. Dado que el tipo no tiene ningún nombre utilizable, el tipo de la variable de iteración del bucle debe determinarse implícitamente.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)
