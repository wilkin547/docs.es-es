---
title: Relaciones entre tipos en las operaciones de consulta LINQ
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
ms.openlocfilehash: e839271ac254a5e96f8c99f59397016fb99540aa
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636918"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Relaciones entre tipos en operaciones de consulta (Visual Basic)

Las variables que se usan en las operaciones de consulta de Language-Integrated Query (LINQ) están fuertemente tipadas y deben ser compatibles entre sí. El establecimiento de tipos seguros se usa en el origen de datos, en la propia consulta y en la ejecución de la consulta. En la ilustración siguiente se identifican los términos que se usan para describir una consulta LINQ. Para obtener más información acerca de las partes de una consulta, consulte [operaciones básicas de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).

![Captura de pantalla que muestra una consulta de pseudocódigo con elementos resaltados.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

El tipo de la variable de rango de la consulta debe ser compatible con el tipo de los elementos del origen de datos. El tipo de la variable de consulta debe ser compatible con el elemento de secuencia definido en la cláusula `Select`. Por último, el tipo de los elementos de la secuencia también debe ser compatible con el tipo de la variable de control de bucle que se utiliza en la instrucción `For Each` que ejecuta la consulta. Este fuertemente tipado facilita la identificación de los errores de tipo en tiempo de compilación.

Visual Basic hace que el establecimiento de tipos seguros sea conveniente implementando la inferencia de tipo local, también conocida como *tipos implícitos*. Esa característica se usa en el ejemplo anterior y la verá utilizada en los ejemplos y la documentación de LINQ. En Visual Basic, la inferencia de tipo de variable local se realiza simplemente mediante una instrucción de `Dim` sin una cláusula `As`. En el ejemplo siguiente, `city` se escribe fuertemente tipada como una cadena.

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> La inferencia de tipo local solo funciona cuando `Option Infer` está establecido en `On`. Para obtener más información, vea [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).

Sin embargo, incluso si utiliza la inferencia de tipo de variable local en una consulta, las mismas relaciones de tipo están presentes entre las variables en el origen de datos, la variable de consulta y el bucle de ejecución de la consulta. Resulta útil tener un conocimiento básico de estas relaciones de tipo al escribir consultas LINQ o al trabajar con los ejemplos y ejemplos de código de la documentación.

Es posible que tenga que especificar un tipo explícito para una variable de rango que no coincida con el tipo devuelto desde el origen de datos. Puede especificar el tipo de la variable de rango mediante el uso de una cláusula `As`. Sin embargo, esto genera un error si la conversión es una [conversión de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y `Option Strict` está establecido en `On`. Por lo tanto, se recomienda realizar la conversión en los valores recuperados del origen de datos. Puede convertir los valores del origen de datos al tipo de variable de rango explícito mediante el método <xref:System.Linq.Enumerable.Cast%2A>. También puede convertir los valores seleccionados en la cláusula `Select` a un tipo explícito distinto del tipo de la variable de rango. Estos puntos se muestran en el código siguiente.

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Consultas que devuelven elementos completos de los datos de origen

En el ejemplo siguiente se muestra una operación de consulta LINQ que devuelve una secuencia de elementos seleccionados a partir de los datos de origen. El origen, `names`, contiene una matriz de cadenas y el resultado de la consulta es una secuencia que contiene cadenas que comienzan por la letra M.

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

Esto es equivalente al código siguiente, pero es mucho más corto y más fácil de escribir. La dependencia de la inferencia de tipo local en las consultas es el estilo preferido en Visual Basic.

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

Las siguientes relaciones existen en los dos ejemplos de código anteriores, tanto si los tipos se determinan implícita o explícitamente.

1. El tipo de los elementos del origen de datos, `names`, es el tipo de la variable de rango, `name`, en la consulta.

2. El tipo del objeto que está seleccionado, `name`, determina el tipo de la variable de consulta, `mNames`. Aquí `name` es una cadena, por lo que la variable de consulta es IEnumerable (of String) en Visual Basic.

3. La consulta definida en `mNames` se ejecuta en el bucle de `For Each`. El bucle recorre en iteración el resultado de la ejecución de la consulta. Dado que `mNames`, cuando se ejecuta, devolverá una secuencia de cadenas, la variable de iteración del bucle, `nm`, también es una cadena.

## <a name="queries-that-return-one-field-from-selected-elements"></a>Consultas que devuelven un campo de los elementos seleccionados

En el ejemplo siguiente se muestra una [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operación de consulta que devuelve una secuencia que contiene solo una parte de cada elemento seleccionado del origen de datos. La consulta toma una colección de objetos `Customer` como origen de datos y proyecta solo la propiedad `Name` en el resultado. Dado que el nombre del cliente es una cadena, la consulta genera una secuencia de cadenas como salida.

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

1. El tipo de los elementos del origen de datos, `customers`, es el tipo de la variable de rango, `cust`, en la consulta. En este ejemplo, ese tipo es `Customer`.

2. La instrucción `Select` devuelve la propiedad `Name` de cada objeto `Customer` en lugar de todo el objeto. Dado que `Name` es una cadena, la variable de consulta, `custNames`, volverá a ser IEnumerable (de cadena), no `Customer`.

3. Dado que `custNames` representa una secuencia de cadenas, la variable de iteración del bucle de `For Each`, `custName`, debe ser una cadena.

Sin la inferencia de tipo local, el ejemplo anterior sería más complicado de escribir y comprender, como se muestra en el ejemplo siguiente.

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

En el ejemplo siguiente se muestra una situación más compleja. En el ejemplo anterior, no era conveniente especificar explícitamente los tipos para todas las variables. En este ejemplo, es imposible. En lugar de seleccionar todos los elementos `Customer` del origen de datos, o un único campo de cada elemento, la cláusula `Select` de esta consulta devuelve dos propiedades del objeto de `Customer` original: `Name` y `City`. En respuesta a la cláusula `Select`, el compilador define un tipo anónimo que contiene esas dos propiedades. El resultado de ejecutar `nameCityQuery` en el bucle de `For Each` es una colección de instancias del nuevo tipo anónimo. Dado que el tipo anónimo no tiene ningún nombre utilizable, no se puede especificar el tipo de `nameCityQuery` o `custInfo` explícitamente. Es decir, con un tipo anónimo, no hay ningún nombre de tipo para usar en lugar de `String` en `IEnumerable(Of String)`. Para obtener más información, consulte [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) (Tipos anónimos [Guía de programación de C#]).

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

Aunque no es posible especificar tipos para todas las variables en el ejemplo anterior, las relaciones siguen siendo las mismas.

1. El tipo de los elementos del origen de datos es de nuevo el tipo de la variable de rango en la consulta. En este ejemplo, `cust` es una instancia de `Customer`.

2. Dado que la instrucción `Select` genera un tipo anónimo, la variable de consulta, `nameCityQuery`, se debe escribir implícitamente como un tipo anónimo. Un tipo anónimo no tiene ningún nombre utilizable y, por lo tanto, no se puede especificar explícitamente.

3. El tipo de la variable de iteración en el bucle `For Each` es el tipo anónimo creado en el paso 2. Dado que el tipo no tiene ningún nombre utilizable, el tipo de la variable de iteración del bucle se debe determinar de forma implícita.

## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
