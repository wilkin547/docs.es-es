---
description: 'Más información acerca de: matrices en Visual Basic'
title: Matrices
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: b6e8349fe02e77f12fb827618f84d44288914b62
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454604"
---
# <a name="arrays-in-visual-basic"></a>Matrices en Visual Basic

Una matriz es un conjunto de valores, que son *elementos* denominados, que están relacionados lógicamente entre sí. Por ejemplo, una matriz puede consistir en el número de alumnos de cada grado en una escuela gramatical; cada elemento de la matriz es el número de alumnos en un solo grado. Del mismo modo, una matriz puede constar de las calificaciones de un estudiante para una clase. cada elemento de la matriz es un solo grado.

Es posible que las variables individuales almacenen cada uno de los elementos de datos. Por ejemplo, si nuestra aplicación analiza las calificaciones de los estudiantes, podemos usar una variable independiente para la calificación de cada estudiante, como `englishGrade1` , `englishGrade2` , etc. Este enfoque tiene tres limitaciones principales:

- Tenemos que saber en tiempo de diseño exactamente cuántos grados es necesario controlar.
- Administrar rápidamente un gran número de calificaciones se vuelve difícil. Esto, a su vez, hace que una aplicación tenga mucho más probabilidades de tener errores graves.
- Es difícil de mantener. Cada nuevo grado que agregues requiere que la aplicación se modifique, se vuelva a compilar y se vuelva a implementar.

Mediante el uso de una matriz, puede hacer referencia a estos valores relacionados con el mismo nombre y usar un número denominado *Índice* o *subíndice* para identificar un elemento individual en función de su posición en la matriz. Los índices de una matriz van de 0 a uno menos que el número total de elementos de la matriz. Cuando se usa Visual Basic sintaxis para definir el tamaño de una matriz, se especifica su índice más alto, no el número total de elementos de la matriz. Puede trabajar con la matriz como una unidad y la capacidad de recorrer en iteración sus elementos le libera de tener que saber exactamente cuántos elementos contiene en tiempo de diseño.

Veamos algunos ejemplos rápidos antes de la explicación:

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

' Declare a single-dimension array and set its 4 values.
Dim numbers = New Integer() {1, 2, 4, 8}

' Change the size of an existing array to 16 elements and retain the current values.
ReDim Preserve numbers(15)

' Redefine the size of an existing array and reset the values.
ReDim numbers(15)

' Declare a 6 x 6 multidimensional array.
Dim matrix(5, 5) As Double

' Declare a 4 x 3 multidimensional array and set array element values.
Dim matrix = New Integer(3, 2) {{1, 2, 3}, {2, 3, 4}, {3, 4, 5}, {4, 5, 6}}

' Declare a jagged array
Dim sales()() As Double = New Double(11)() {}
```

## <a name="array-elements-in-a-simple-array"></a>Elementos de matriz en una matriz simple

Vamos a crear una matriz denominada `students` para almacenar el número de alumnos en cada grado en una escuela gramatical. Los índices de los elementos van del 0 al 6. Usar esta matriz es más sencillo que declarar siete variables.

En la ilustración siguiente se muestra la `students` matriz. Para cada elemento de la matriz:

- El índice del elemento representa el curso (el índice 0 representa la guardería).

- El valor que se encuentra en el elemento representa el número de estudiantes en dicho curso.

![Diagrama que muestra una matriz de los números de estudiantes](./media/index/students-array-elements.gif)

El ejemplo siguiente contiene el código Visual Basic que crea y usa la matriz:

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

En el ejemplo se hace tres cosas:

- Declara una `students` matriz con siete elementos. El número `6` de la declaración de matriz indica el último índice de la matriz; es uno menos que el número de elementos de la matriz.
- Asigna valores a cada elemento de la matriz. Se obtiene acceso a los elementos de matriz utilizando el nombre de la matriz y se incluye el índice del elemento individual entre paréntesis.
- Muestra cada valor de la matriz. En el ejemplo se usa una [`For`](../../../language-reference/statements/for-next-statement.md) instrucción para tener acceso a cada elemento de la matriz por su número de índice.

La `students` matriz del ejemplo anterior es una matriz unidimensional porque utiliza un índice. Una matriz que usa más de un índice o subíndice se denomina *multidimensional*. Para obtener más información, vea el resto de este artículo y las [dimensiones de la matriz en Visual Basic](array-dimensions.md).

## <a name="creating-an-array"></a>Crear una matriz

Puede definir el tamaño de una matriz de varias maneras:

- Puede especificar el tamaño cuando se declara la matriz:

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- Puede usar una `New` cláusula para proporcionar el tamaño de una matriz cuando se crea:

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

Si tiene una matriz existente, puede volver a definir su tamaño mediante la [`ReDim`](../../../language-reference/statements/redim-statement.md) instrucción. Puede especificar que la `ReDim` instrucción Mantenga los valores que se encuentran en la matriz o puede especificar que cree una matriz vacía. El ejemplo siguiente muestra los diferentes usos de la instrucción `ReDim` para modificar el tamaño de una matriz existente.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

Para obtener más información, vea la [instrucción ReDim](../../../language-reference/statements/redim-statement.md).

## <a name="storing-values-in-an-array"></a>Almacenar valores en una matriz

Puede tener acceso a cada ubicación en una matriz mediante un índice del tipo `Integer`. Puede almacenar y recuperar los valores en una matriz haciendo referencia a cada ubicación de la matriz usando su índice entre paréntesis. Los índices de matrices multidimensionales se separan mediante comas (,). Necesita un índice para cada dimensión de la matriz.

En el ejemplo siguiente se muestran algunas instrucciones que almacenan y recuperan valores en las matrices.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>Rellenar una matriz con literales de matriz

Mediante el uso de un literal de matriz, puede rellenar una matriz con un conjunto inicial de valores al mismo tiempo que se crea. Un literal de matriz consta de una lista de valores separados por comas entre llaves (`{}`).

Cuando se crea una matriz mediante un literal de matriz, puede proporcionar el tipo de matriz o usar la inferencia de tipo para determinar el tipo de matriz. En el ejemplo siguiente se muestran ambas opciones.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

Cuando se usa la inferencia de tipos, el tipo de la matriz viene determinado por el *tipo dominante* en la lista de valores literales. El tipo dominante es el tipo al que se pueden ampliar todos los demás tipos de la matriz. Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que todos los demás tipos de la matriz se pueden restringir. Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`. Por ejemplo, si la lista de valores que se proporciona al literal de matriz contiene valores de tipo `Integer`, `Long`y `Double`, la matriz resultante es de tipo `Double`. Dado `Integer` `Long` que y se amplían solo a `Double` , `Double` es el tipo dominante. Para obtener más información, consulta [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).

> [!NOTE]
> Solo se puede usar la inferencia de tipos para las matrices definidas como variables locales en un miembro de tipo. Si falta una definición de tipo explícita, las matrices definidas con literales de matriz en el nivel de clase son de tipo `Object[]` . Para obtener más información, vea [inferencia de tipo local](../variables/local-type-inference.md).

Tenga en cuenta que en el ejemplo anterior `values` se define como una matriz de tipo, `Double` aunque todos los literales de matriz son del tipo `Integer` . Puede crear esta matriz porque los valores del literal de matriz pueden ampliarse a `Double` valores.

También puede crear y rellenar una matriz multidimensional utilizando *literales de matriz anidados*. Los literales de matriz anidados deben tener un número de dimensiones que sea coherente con la matriz resultante. En el ejemplo siguiente se crea una matriz bidimensional de enteros utilizando literales de matriz anidados.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

Cuando se usan literales de matriz anidados para crear y rellenar una matriz, se produce un error si el número de elementos de los literales de matriz anidados no coincide. También se produce un error si declara explícitamente que la variable de matriz tiene un número diferente de dimensiones que los literales de matriz.

Al igual que en el caso de las matrices unidimensionales, puede confiar en la inferencia de tipos al crear una matriz multidimensional con literales de matriz anidados. El tipo deducido es el tipo dominante para todos los valores de todos los literales de matriz para todos los niveles de anidamiento. En el ejemplo siguiente se crea una matriz bidimensional de tipo `Double[,]` a partir de valores que son de tipo `Integer` y `Double` .

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

Para consultar ejemplos adicionales, vea [Cómo: Inicializar una variable de matriz en Visual Basic](how-to-initialize-an-array-variable.md).

## <a name="iterating-through-an-array"></a>Recorrer en iteración una matriz

Cuando recorre en iteración una matriz, tiene acceso a cada elemento de la matriz desde el índice más bajo hasta el más alto o de mayor a menor. Normalmente, use la [... Instrucción siguiente](../../../language-reference/statements/for-next-statement.md) o [... Instrucción siguiente](../../../language-reference/statements/for-each-next-statement.md) para recorrer en iteración los elementos de una matriz. Si no conoce los límites superiores de la matriz, puede llamar al <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> método para obtener el valor más alto del índice. Aunque el valor de índice más bajo es casi siempre 0, puede llamar al <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> método para obtener el valor más bajo del índice.

En el ejemplo siguiente se recorre en iteración una matriz unidimensional mediante la [`For...Next`](../../../language-reference/statements/for-next-statement.md) instrucción.

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

En el ejemplo siguiente se recorre en iteración una matriz multidimensional mediante una [`For...Next`](../../../language-reference/statements/for-next-statement.md) instrucción. El método <xref:System.Array.GetUpperBound%2A> tiene un parámetro que especifica la dimensión. `GetUpperBound(0)` Devuelve el índice más alto de la primera dimensión y `GetUpperBound(1)` devuelve el índice más alto de la segunda dimensión.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

En el ejemplo siguiente se utiliza una [para cada... Instrucción siguiente](../../../language-reference/statements/for-each-next-statement.md)para recorrer en iteración una matriz unidimensional y una matriz bidimensional.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>Tamaño de la matriz

El tamaño de una matriz es el producto de las longitudes de todas sus dimensiones. Representa el número total de elementos contenidos actualmente en la matriz.  Por ejemplo, en el ejemplo siguiente se declara una matriz bidimensional con cuatro elementos en cada dimensión. Como muestra la salida del ejemplo, el tamaño de la matriz es 16 (o (3 + 1) * (3 + 1).

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> Esta explicación del tamaño de la matriz no se aplica a las matrices escalonadas. Para obtener información sobre las matrices escalonadas y determinar el tamaño de una matriz escalonada, consulte la sección [matrices escalonadas](#jagged-arrays) .

Puede encontrar el tamaño de una matriz mediante la propiedad <xref:System.Array.Length%2A?displayProperty=nameWithType>. Puede buscar la longitud de cada dimensión de una matriz multidimensional utilizando el <xref:System.Array.GetLength%2A?displayProperty=nameWithType> método.

Puede cambiar el tamaño de una variable de matriz asignando un nuevo objeto de matriz o usando la instrucción de [ `ReDim` instrucción](../../../language-reference/statements/redim-statement.md) . En el ejemplo siguiente se usa la `ReDim` instrucción para cambiar una matriz de 100 elementos a una matriz de elementos 51.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

Hay varios aspectos que se deben tener en cuenta cuando se trabaja con el tamaño de una matriz.

|||
|---|---|
|Longitud de la dimensión|El índice de cada dimensión es de base 0, lo que significa que va desde 0 hasta su límite superior. Por lo tanto, la longitud de una dimensión determinada es uno mayor que el límite superior declarado de esa dimensión.|
|Límites de longitud|La longitud de cada dimensión de una matriz se limita al valor máximo del tipo de `Integer` datos, que es <xref:System.Int32.MaxValue?displayProperty=nameWithType> o (2 ^ 31)-1. Sin embargo, el tamaño total de una matriz también está limitado por la memoria disponible en el sistema. Si intenta inicializar una matriz que supera la cantidad de memoria disponible, el tiempo de ejecución produce una excepción <xref:System.OutOfMemoryException> .|
|Tamaño y tamaño de elemento|El tamaño de la matriz es independiente del tipo de datos de sus elementos. El tamaño siempre representa el número total de elementos, no el número de bytes que consumen en la memoria.|
|Consumo de memoria|No es seguro dar nada por supuesto en lo que respecta al modo de almacenar una matriz en la memoria. El almacenamiento varía en función de las plataformas de diferentes anchos de datos, por lo que la misma matriz puede utilizar más memoria en un sistema de 64 bits que en un sistema de 32 bits. Según la configuración del sistema cuando inicializa una matriz, Common Language Runtime (CLR) puede asignar el almacenamiento para empaquetar los elementos tan juntos como sea posible o para alinearlos todos en los límites naturales del hardware. Asimismo, una matriz requiere una sobrecarga de almacenamiento para obtener su información de control y esta sobrecarga aumenta con cada dimensión agregada.|

## <a name="the-array-type"></a>El tipo de matriz

Cada matriz tiene un tipo de datos, que difiere del tipo de datos de sus elementos. No existe ningún tipo de datos para todas las matrices. En su lugar, el tipo de datos de una matriz lo determina el número de dimensiones, o *rango*, de la matriz y el tipo de datos de los elementos de la matriz. Dos variables de matriz son del mismo tipo de datos solo cuando tienen el mismo rango y sus elementos tienen el mismo tipo de datos. Las longitudes de las dimensiones de una matriz no influyen en el tipo de datos de la matriz.

Cada matriz hereda la clase <xref:System.Array?displayProperty=nameWithType> y puede declarar una variable del tipo `Array`, pero no puede crear una matriz del tipo `Array`. Por ejemplo, aunque el código siguiente declara la `arr` variable para que sea de tipo `Array` y llama al <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> método para crear una instancia de la matriz, el tipo de la matriz demuestra ser Object [].

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

Además, la [Instrucción ReDim](../../../language-reference/statements/redim-statement.md) no puede funcionar en una variable declarada de tipo `Array`. Por estos motivos, y para la seguridad de tipos, es aconsejable declarar cada matriz como un tipo específico.

Puede averiguar el tipo de datos de una matriz o de sus elementos de varias maneras.

- Puede llamar al <xref:System.Object.GetType%2A> método en la variable para obtener un <xref:System.Type> objeto que represente el tipo en tiempo de ejecución de la variable. El objeto <xref:System.Type> contiene amplia información en sus propiedades y métodos.
- Puede pasar la variable a la <xref:Microsoft.VisualBasic.Information.TypeName%2A> función para obtener un `String` con el nombre de tipo en tiempo de ejecución.

En el ejemplo siguiente se llama al `GetType` método y `TypeName` a la función para determinar el tipo de una matriz. El tipo de matriz es `Byte(,)` . Tenga en cuenta que la <xref:System.Type.BaseType%2A?displayProperty=nameWithType> propiedad también indica que el tipo base de la matriz de bytes es la <xref:System.Array> clase.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>Matrices como valores devueltos y parámetros

Para devolver una matriz desde un procedimiento `Function`, especifique el tipo de datos de matriz y el número de dimensiones como tipo de valor devuelto de la [Instrucción Function](../../../language-reference/statements/function-statement.md). Dentro de la función, declare una variable de matriz local con el mismo tipo de datos y número de dimensiones. En la [Instrucción Return](../../../language-reference/statements/return-statement.md), incluya la variable de matriz local sin paréntesis.

Para especificar una matriz como parámetro para un procedimiento `Sub` o `Function` , defina el parámetro como una matriz con un tipo de datos especificado y el número de dimensiones. En la llamada al procedimiento, pase una variable de matriz con el mismo tipo de datos y número de dimensiones.

En el ejemplo siguiente, la `GetNumbers` función devuelve una `Integer()` matriz unidimensional de tipo `Integer` . El procedimiento `ShowNumbers` acepta un argumento `Integer()` .

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

En el ejemplo siguiente, la `GetNumbersMultiDim` función devuelve un `Integer(,)` , una matriz bidimensional de tipo `Integer` .  El procedimiento `ShowNumbersMultiDim` acepta un argumento `Integer(,)` .

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>Matrices escalonadas

A veces la estructura de datos de la aplicación es bidimensional pero no rectangular. Por ejemplo, puede usar una matriz para almacenar datos sobre la temperatura alta de cada día del mes. La primera dimensión de la matriz representa el mes, pero la segunda dimensión representa el número de días, y el número de días de un mes no es uniforme. Una *matriz escalonada*, que también se denomina *matriz de matrices*, está diseñada para estos escenarios. Una matriz escalonada es una matriz cuyos elementos también son matrices. Una matriz escalonada y cada elemento de una matriz escalonada pueden tener una o más dimensiones.

En el ejemplo siguiente se utiliza una matriz de meses, donde cada elemento es una matriz de días. En el ejemplo se usa una matriz escalonada porque los distintos meses tienen un número diferente de días.  En el ejemplo se muestra cómo crear una matriz escalonada, asignarle valores y recuperar y mostrar sus valores.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

En el ejemplo anterior se asignan valores a la matriz escalonada en función de cada elemento mediante un `For...Next` bucle. También puede asignar valores a los elementos de una matriz escalonada utilizando literales de matriz anidados. Sin embargo, el intento de usar literales de matriz anidados (por ejemplo, `Dim valuesjagged = {{1, 2}, {2, 3, 4}}` ) genera el error del compilador [BC30568](../../../misc/bc30568.md). Para corregir el error, incluya los literales de matriz internos entre paréntesis. Los paréntesis fuerzan la evaluación de la expresión literal de matriz y los valores resultantes se usan con el literal de matriz externo, como se muestra en el ejemplo siguiente.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

Una matriz escalonada es una matriz unidimensional cuyos elementos contienen matrices. Por lo tanto, la <xref:System.Array.Length%2A?displayProperty=nameWithType> propiedad y el `Array.GetLength(0)` método devuelven el número de elementos de la matriz unidimensional y `Array.GetLength(1)` produce una excepción <xref:System.IndexOutOfRangeException> porque una matriz escalonada no es multidimensional. El número de elementos de cada submatriz se determina mediante la recuperación del valor de cada propiedad de la submatriz <xref:System.Array.Length%2A?displayProperty=nameWithType> . En el ejemplo siguiente se muestra cómo determinar el número de elementos de una matriz escalonada.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>Matrices de longitud cero

Visual Basic distingue entre una matriz no inicializada (una matriz cuyo valor es `Nothing` ) y una *matriz de longitud cero* o una matriz vacía (una matriz que no tiene elementos). Una matriz no inicializada es aquella que no se ha acotado o que no tiene asignado ningún valor. Por ejemplo:

```vb
Dim arr() As String
```

Una matriz de longitud cero se declara con una dimensión de-1. Por ejemplo:

```vb
Dim arrZ(-1) As String
```

Puede que tenga que crear una matriz de longitud cero en las circunstancias siguientes:

- Sin arriesgarse a una <xref:System.NullReferenceException> excepción, el código debe tener acceso a los miembros de la <xref:System.Array> clase, como <xref:System.Array.Length%2A> o <xref:System.Array.Rank%2A> , o llamar a una función de Visual Basic como <xref:Microsoft.VisualBasic.Information.UBound%2A> .

- Desea mantener el código sencillo sin tener que comprobar `Nothing` como caso especial.

- El código interactúa con una interfaz de programación de aplicaciones (API) que requiere pasar una matriz de longitud cero a uno o más procedimientos o que devuelve una matriz de longitud cero desde uno o más procedimientos.

## <a name="splitting-an-array"></a>Dividir una matriz

En algunos casos, puede que necesite dividir una matriz única en varias matrices. Esto implica identificar el punto o los puntos en los que se va a dividir la matriz y, a continuación, spitting la matriz en dos o más matrices independientes.

> [!NOTE]
> En esta sección no se explica la división de una cadena única en una matriz de cadenas basada en algún delimitador. Para obtener información sobre cómo dividir una cadena, vea el <xref:System.String.Split%2A?displayProperty=nameWithType> método.

Los criterios más comunes para dividir una matriz son:

- Número de elementos de la matriz. Por ejemplo, puede dividir una matriz de más de un número especificado de elementos en un número de partes aproximadamente iguales. Para este propósito, puede utilizar el valor devuelto por el <xref:System.Array.Length%2A?displayProperty=nameWithType> método o <xref:System.Array.GetLength%2A?displayProperty=nameWithType> .

- El valor de un elemento, que actúa como delimitador que indica dónde se debe dividir la matriz. Para buscar un valor específico, puede llamar a los <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> métodos y.

Una vez que haya determinado los índices en los que se debe dividir la matriz, puede crear las matrices individuales llamando al <xref:System.Array.Copy%2A?displayProperty=nameWithType> método.

En el ejemplo siguiente se divide una matriz en dos matrices de aproximadamente el mismo tamaño. (Si el número total de elementos de matriz es impar, la primera matriz tiene un elemento más que el segundo).

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

En el ejemplo siguiente se divide una matriz de cadenas en dos matrices en función de la presencia de un elemento cuyo valor es "Zzz", que actúa como delimitador de la matriz. Las nuevas matrices no incluyen el elemento que contiene el delimitador.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>Combinación de matrices

También puede combinar varias matrices en una sola matriz mayor. Para ello, también se usa el <xref:System.Array.Copy%2A?displayProperty=nameWithType> método.

> [!NOTE]
> En esta sección no se explica cómo combinar una matriz de cadenas en una sola cadena. Para obtener información sobre cómo combinar una matriz de cadenas, vea el <xref:System.String.Join%2A?displayProperty=nameWithType> método.

Antes de copiar los elementos de cada matriz en la nueva matriz, primero debe asegurarse de que ha inicializado la matriz para que sea lo suficientemente grande como para dar cabida a la nueva matriz. Puede hacerlo de una de las maneras siguientes:

- Use la [`ReDim Preserve`](../../../language-reference/statements/redim-statement.md) instrucción para expandir dinámicamente la matriz antes de agregarle nuevos elementos. Esta es la técnica más sencilla, pero puede producir una degradación del rendimiento y un consumo excesivo de memoria cuando se copian matrices de gran tamaño.
- Calcule el número total de elementos necesarios para la nueva matriz grande y, a continuación, agregue los elementos de cada matriz de origen a él.

En el ejemplo siguiente se usa el segundo método para agregar cuatro matrices con diez elementos cada una a una sola matriz.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

Puesto que en este caso las matrices de origen son pequeñas, también podemos expandir dinámicamente la matriz a medida que se agregan los elementos de cada nueva matriz a ella. En el siguiente ejemplo se realiza esto.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>Colecciones como alternativa a las matrices

Las matrices son muy útiles para crear y trabajar con un número fijo de objetos fuertemente tipados. Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos. A diferencia de las matrices, que requieren que se cambie explícitamente el tamaño de una matriz con la [ `ReDim` instrucción](../../../language-reference/statements/redim-statement.md), las colecciones crecen y reducen dinámicamente a medida que cambian las necesidades de una aplicación.

Cuando se usa `ReDim` para redimensionar una matriz, Visual Basic crea una nueva matriz y libera la anterior. Esto requiere tiempo de ejecución. Por lo tanto, si el número de elementos con los que trabaja cambia con frecuencia, o si no puede predecir el número máximo de elementos que necesita, normalmente obtendrá un mejor rendimiento si usa una colección.

Para algunas colecciones, puede asignar una clave a cualquier objeto que incluya en la colección para, de este modo, recuperar rápidamente el objeto con la clave.

Si la colección contiene elementos de un solo tipo de datos, puede usar una de las clases del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>. Una colección genérica cumple la seguridad de tipos para que ningún otro tipo de datos se pueda agregar a ella.

Para más información sobre las colecciones, vea [Colecciones](../../concepts/collections.md).

## <a name="related-topics"></a>Temas relacionados

|Término|Definición|
|----------|----------------|
|[Array Dimensions in Visual Basic](array-dimensions.md)|Explica el rango y las dimensiones de las matrices.|
|[Cómo: Inicializar una variable de matriz en Visual Basic](how-to-initialize-an-array-variable.md)|Describe cómo se llenan las matrices con valores iniciales.|
|[Cómo: Ordenar una matriz en Visual Basic](how-to-sort-an-array.md)|Muestra cómo ordenar alfabéticamente los elementos de una matriz.|
|[Procedimiento para asignar una matriz a otra](how-to-assign-one-array-to-another-array.md)|Describe las reglas y los pasos para asignar una matriz a otra variable de matriz.|
|[Solución de problemas de matrices](troubleshooting-arrays.md)|Describe algunos problemas comunes que surgen al trabajar con matrices.|

## <a name="see-also"></a>Consulte también

- <xref:System.Array?displayProperty=nameWithType>
- [Instrucción Dim](../../../language-reference/statements/dim-statement.md)
- [Instrucción ReDim](../../../language-reference/statements/redim-statement.md)
