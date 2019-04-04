---
title: Matrices en Visual Basic
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: 6b131d073e10f99feaf770fe5fd3c393551fa5a3
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675970"
---
# <a name="arrays-in-visual-basic"></a>Matrices en Visual Basic

Una matriz es un conjunto de valores, que se denomina *elementos*, que se relacionan lógicamente entre sí. Por ejemplo, una matriz puede constar del número de alumnos de cada curso en una escuela primaria; cada elemento de la matriz es el número de alumnos en un único nivel. De forma similar, una matriz puede constar de las calificaciones de un estudiante de una clase; cada elemento de la matriz es un único nivel.

Es posible variables individuales para almacenar cada uno de nuestros elementos de datos. Por ejemplo, si nuestra aplicación analiza alumnos, podemos usamos una variable independiente para el nivel de cada alumno, tales como `englishGrade1`, `englishGrade2`, etcetera. Este enfoque tiene tres principales limitaciones:

- Tenemos que saber en tiempo de diseño exactamente cuántas calificaciones se tiene que controlar.
- Controlar un gran número de grados de rápidamente es difícil de manejar. A su vez, esto hace que una aplicación mucho más probable que tengan errores graves.
- Es difícil de mantener. Cada curso nueva que agregamos requiere que la aplicación se puede modificar, vuelve a compilar y volver a implementar.

Mediante el uso de una matriz, puede hacer referencia a estos valores relacionados con el mismo nombre y usar un número que se llama a un *índice* o *subíndice* para identificar un elemento individual en función de su posición en la matriz. Los índices de una matriz van desde 0 hasta uno menos que el número total de elementos de la matriz. Cuando usa la sintaxis de Visual Basic para definir el tamaño de una matriz, especificar su índice más alto, no el número total de elementos de la matriz. Puede trabajar con la matriz como una unidad y la capacidad para recorrer en iteración sus elementos le libera de la necesidad de saber exactamente cuántos elementos contiene en tiempo de diseño.

Veamos algunos ejemplos rápidos antes de la explicación:

```vb
' Declare a single-dimension array of 5 numbers.
Dim numbers(4) As Integer

'Declare a single-dimension array and set its 4 values.
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

## <a name="array-elements-in-a-simple-array"></a>Elementos de la matriz en una matriz sencilla

Vamos a crear una matriz llamada `students` para almacenar el número de alumnos de cada curso en una escuela primaria. Los índices de los elementos van del 0 al 6. Uso de esta matriz es más fácil que declarar siete variables.

La siguiente ilustración muestra el `students` matriz. Para cada elemento de la matriz:

- El índice del elemento representa el curso (el índice 0 representa la guardería).

- El valor que se encuentra en el elemento representa el número de estudiantes en dicho curso.

![Diagrama que muestra una matriz de los números de estudiantes](./media/index/students-array-elements.gif)

El ejemplo siguiente contiene el código de Visual Basic que crea y utiliza la matriz:

[!code-vb[simple-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]

El ejemplo hace tres cosas:

- Declara un `students` matriz con siete elementos. El número `6` en la matriz declaración indica el último índice de la matriz; es uno menos que el número de elementos de la matriz.
- Asigna valores a cada elemento de la matriz. Se tiene acceso a los elementos de matriz utilizando el nombre de la matriz y el índice del elemento individual se incluyen entre paréntesis.
- Enumera cada valor de la matriz. El ejemplo se usa un [ `For` ](../../../language-reference/statements/for-next-statement.md) instrucción para tener acceso a cada elemento de la matriz por su número de índice.

El `students` matriz en el ejemplo anterior es una matriz unidimensional porque utiliza un índice. Una matriz que se usa más de un índice o subíndice se denomina *multidimensionales*. Para obtener más información, vea el resto de este artículo y [dimensiones de la matriz en Visual Basic](../../language-features/arrays/array-dimensions.md).

## <a name="creating-an-array"></a>Creación de una matriz

Puede definir el tamaño de una matriz de varias maneras:

- Puede especificar el tamaño cuando se declara la matriz:

  [!code-vb[creating1](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]

- Puede usar un `New` cláusula para proporcionar el tamaño de la matriz cuando se crea:

  [!code-vb[creating2](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]

Si tiene una matriz existente, puede volver a definir su tamaño utilizando la [ `ReDim` ](../../../language-reference/statements/redim-statement.md) instrucción. Puede especificar que el `ReDim` instrucción mantenga los valores que se encuentran en la matriz, o puede especificar que crear una matriz vacía. El ejemplo siguiente muestra los diferentes usos de la instrucción `ReDim` para modificar el tamaño de una matriz existente.

[!code-vb[redimensioning](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]

Para obtener más información, consulte el [instrucción ReDim](../../../language-reference/statements/redim-statement.md).

## <a name="storing-values-in-an-array"></a>Almacenar valores en una matriz

Puede tener acceso a cada ubicación en una matriz mediante un índice del tipo `Integer`. Puede almacenar y recuperar los valores en una matriz haciendo referencia a cada ubicación de la matriz usando su índice entre paréntesis. Los índices para las matrices multidimensionales se separan mediante comas (,). Necesita un índice para cada dimensión de la matriz.

El ejemplo siguiente muestra algunas instrucciones que almacenan y recuperan valores de las matrices.

[!code-vb[store-and-retrieve](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]

## <a name="populating-an-array-with-array-literals"></a>Rellenar una matriz con literales de matriz

Mediante el uso de un literal de matriz, puede rellenar una matriz con un conjunto inicial de valores al mismo tiempo que la crea. Un literal de matriz consta de una lista de valores separados por comas entre llaves (`{}`).

Cuando se crea una matriz mediante un literal de matriz, puede proporcionar el tipo de matriz o usar la inferencia de tipo para determinar el tipo de matriz. El ejemplo siguiente muestra ambas opciones.

[!code-vb[create-with-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]

Cuando se usa la inferencia de tipos, el tipo de la matriz viene determinada por la *tipo dominante* en la lista de valores literales. El tipo dominante es el tipo al que se pueden ampliar todos los demás tipos de la matriz. Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que todos los demás tipos de la matriz se pueden restringir. Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`. Por ejemplo, si la lista de valores que se proporciona al literal de matriz contiene valores de tipo `Integer`, `Long`y `Double`, la matriz resultante es de tipo `Double`. Dado que `Integer` y `Long` amplían solo a `Double`, `Double` es el tipo dominante. Para obtener más información, consulta [Widening and Narrowing Conversions](../../language-features/data-types/widening-and-narrowing-conversions.md).

> [!NOTE]
> Puede usar la inferencia solo para las matrices que se definen como las variables locales en un miembro de tipo. Si falta una definición de tipo explícito, las matrices definidas con literales de matriz en el nivel de clase son de tipo `Object[]`. Para obtener más información, consulte [inferencia de tipos Local](../variables/local-type-inference.md).

Tenga en cuenta que el ejemplo anterior se define `values` como una matriz de tipo `Double` , aunque todos los literales de matriz son del tipo `Integer`. Puede crear esta matriz porque los valores del literal de matriz se pueden ampliar `Double` valores.

También puede crear y rellenar una matriz multidimensional mediante *anidar los literales de matriz*. Literales de matriz anidados deben tener un número de dimensiones que sea coherente con la matriz resultante. El ejemplo siguiente crea una matriz bidimensional de enteros mediante el uso de literales de matriz anidados.

[!code-vb[nested-array-literals](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]

Al usar literales de matriz anidados para crear y rellenar una matriz, se produce un error si el número de elementos en los literales de matriz anidados no coincide. También se produce un error si se declara explícitamente la variable de matriz tienen un número diferente de dimensiones que los literales de matriz.

Se puede hacer para las matrices unidimensionales, puede confiar en la inferencia de tipos al crear una matriz multidimensional con literales de matriz anidados. El tipo inferido es el tipo dominante para todos los valores de todos los literales de matriz para el nivel de anidamiento de todos. En el ejemplo siguiente se crea una matriz bidimensional de tipo `Double[,]` de valores que son del tipo `Integer` y `Double`.

[!code-vb[nested-type-inference](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]

Para obtener ejemplos adicionales, vea [Cómo: Inicializar una Variable de matriz en Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md).

## <a name="iterating-through-an-array"></a>Recorrer en iteración una matriz

Cuando recorren en iteración una matriz, tener acceso a cada elemento de la matriz desde el índice más bajo al más alto o de mayor a menor. Por lo general, use el [para... Instrucción Next](../../../language-reference/statements/for-next-statement.md) o [para cada... Instrucción Next](../../../language-reference/statements/for-each-next-statement.md) para recorrer en iteración los elementos de una matriz. Si no conoce los límites superiores de la matriz, puede llamar a la <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> método para obtener el valor más alto del índice. Aunque el valor de índice mínimo es casi siempre es 0, puede llamar a la <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> método para obtener el valor más bajo del índice.

El ejemplo siguiente se recorre en iteración una matriz unidimensional mediante el uso de la [ `For...Next` ](../../../language-reference/statements/for-next-statement.md) instrucción.

[!code-vb[iterate-one-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]

El ejemplo siguiente se recorre en iteración una matriz multidimensional utilizando un [ `For...Next` ](../../../language-reference/statements/for-next-statement.md) instrucción. El método <xref:System.Array.GetUpperBound%2A> tiene un parámetro que especifica la dimensión. `GetUpperBound(0)` Devuelve el índice más alto de la primera dimensión y `GetUpperBound(1)` devuelve el índice más alto de la segunda dimensión.

[!code-vb[iterate-two-dimensional-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]

En el ejemplo siguiente se usa un [For Each... Instrucción Next](../../../language-reference/statements/for-each-next-statement.md)para recorrer en iteración una matriz unidimensional y una matriz bidimensional.

[!code-vb[iterate-for-each-next](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]

## <a name="array-size"></a>Tamaño de la matriz

El tamaño de una matriz es el producto de las longitudes de todas sus dimensiones. Representa el número total de elementos contenidos actualmente en la matriz.  Por ejemplo, en el ejemplo siguiente se declara una matriz de 2 dimensiones con cuatro elementos en cada dimensión. Como se muestra el resultado del ejemplo, el tamaño de la matriz es 16 (o (3 + 1) * (3 + 1).

[!code-vb[array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]

> [!NOTE]
> Esta discusión de tamaño de la matriz no es aplicable a las matrices escalonadas. Para obtener información sobre las matrices escalonadas y determinar el tamaño de una matriz escalonada, consulte el [matrices escalonadas](#jagged-arrays) sección.

Puede encontrar el tamaño de una matriz mediante la propiedad <xref:System.Array.Length%2A?displayProperty=nameWithType>. Puede encontrar la longitud de cada dimensión de una matriz multidimensional utilizando el <xref:System.Array.GetLength%2A?displayProperty=nameWithType> método.

Puede cambiar el tamaño de una variable de matriz asignando un nuevo objeto de matriz a él o mediante el [ `ReDim` instrucción](../../../language-reference/statements/redim-statement.md) instrucción. En el ejemplo siguiente se usa el `ReDim` instrucción para cambiar una matriz de 100 elementos a una matriz de elementos de 51.

[!code-vb[resize-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]

Hay varios aspectos que se deben tener en cuenta cuando se trabaja con el tamaño de una matriz.

|||
|---|---|
|Longitud de la dimensión|El índice de cada dimensión es de base 0, lo que significa que va desde 0 a su límite superior. Por lo tanto, la longitud de una dimensión determinada es una unidad mayor que el límite máximo declarado de esa dimensión.|
|Límites de longitud|La longitud de cada dimensión de una matriz se limita al valor máximo de la `Integer` tipo de datos, que es <xref:System.Int32.MaxValue?displayProperty=nameWithType> o (2 ^ 31) - 1. Sin embargo, el tamaño total de una matriz también está limitado por la memoria disponible en el sistema. Si se intenta inicializar una matriz que supera la cantidad de memoria disponible, el runtime produce una <xref:System.OutOfMemoryException>.|
|Tamaño y tamaño de elemento|El tamaño de la matriz es independiente del tipo de datos de sus elementos. El tamaño siempre representa el número total de elementos, no el número de bytes que se usan en la memoria.|
|Consumo de memoria|No es seguro dar nada por supuesto en lo que respecta al modo de almacenar una matriz en la memoria. El almacenamiento varía en función de las plataformas de diferentes anchos de datos, por lo que la misma matriz puede utilizar más memoria en un sistema de 64 bits que en un sistema de 32 bits. Según la configuración del sistema cuando inicializa una matriz, Common Language Runtime (CLR) puede asignar el almacenamiento para empaquetar los elementos tan juntos como sea posible o para alinearlos todos en los límites naturales del hardware. Asimismo, una matriz requiere una sobrecarga de almacenamiento para obtener su información de control y esta sobrecarga aumenta con cada dimensión agregada.|

## <a name="the-array-type"></a>El tipo de matriz

Cada matriz tiene un tipo de datos, que difiere del tipo de datos de sus elementos. No existe ningún tipo de datos para todas las matrices. En su lugar, el tipo de datos de una matriz lo determina el número de dimensiones, o *rango*, de la matriz y el tipo de datos de los elementos de la matriz. Escriba solo cuando tienen el mismo rango y sus elementos tienen los mismos datos escriba, son dos variables de matriz de los mismos datos. Las longitudes de las dimensiones de matriz no influyen en el tipo de datos de matriz.

Cada matriz hereda la clase <xref:System.Array?displayProperty=nameWithType> y puede declarar una variable del tipo `Array`, pero no puede crear una matriz del tipo `Array`. Por ejemplo, aunque el código siguiente declara la `arr` variable es de tipo `Array` y llama a la <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> método para crear una instancia de la matriz, el tipo de la matriz demuestra para ser Object [].

[!code-vb[array-class](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)]

Además, la [Instrucción ReDim](../../../language-reference/statements/redim-statement.md) no puede funcionar en una variable declarada de tipo `Array`. Por estos motivos y seguridad de tipos, es aconsejable declarar cada matriz como un tipo específico.

Puede averiguar el tipo de datos de una matriz o de sus elementos de varias maneras.

- Puede llamar a la <xref:System.Object.GetType%2A> método en la variable para obtener un <xref:System.Type> objeto que representa el tipo de tiempo de ejecución de la variable. El objeto <xref:System.Type> contiene amplia información en sus propiedades y métodos.
- Puede pasar la variable a la <xref:Microsoft.VisualBasic.Information.TypeName%2A> función para obtener un `String` con el nombre del tipo de tiempo de ejecución.

En el ejemplo siguiente se llama tanto el `GetType` método y el `TypeName` función para determinar el tipo de matriz. El tipo de matriz es `Byte(,)`. Tenga en cuenta que el <xref:System.Type.BaseType%2A?displayProperty=nameWithType> propiedad también indica que el tipo base de la matriz de bytes es el <xref:System.Array> clase.

[!code-vb[array-type](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]

## <a name="arrays-as-return-values-and-parameters"></a>Matrices como valores devueltos y parámetros

Para devolver una matriz desde un procedimiento `Function`, especifique el tipo de datos de matriz y el número de dimensiones como tipo de valor devuelto de la [Instrucción Function](../../../language-reference/statements/function-statement.md). Dentro de la función, declare una variable de matriz local con el mismo tipo de datos y número de dimensiones. En la [Instrucción Return](../../../language-reference/statements/return-statement.md), incluya la variable de matriz local sin paréntesis.

Para especificar una matriz como parámetro para un procedimiento `Sub` o `Function` , defina el parámetro como una matriz con un tipo de datos especificado y el número de dimensiones. En la llamada al procedimiento, pase una variable de matriz con el mismo tipo de datos y el número de dimensiones.

En el ejemplo siguiente, la `GetNumbers` función devuelve un `Integer()`, una matriz unidimensional de tipo `Integer`. El procedimiento `ShowNumbers` acepta un argumento `Integer()` .

[!code-vb[return-value-and-params](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]

En el ejemplo siguiente, la `GetNumbersMultiDim` función devuelve un `Integer(,)`, una matriz bidimensional de tipo `Integer`.  El procedimiento `ShowNumbersMultiDim` acepta un argumento `Integer(,)` .

[!code-vb[multidimensional-return-value](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]

## <a name="jagged-arrays"></a>Matrices escalonadas

A veces la estructura de datos de la aplicación es bidimensional pero no rectangular. Por ejemplo, podría utilizar una matriz para almacenar datos acerca de la temperatura máxima de cada día del mes. La primera dimensión de la matriz representa el mes, pero la segunda dimensión representa el número de días y el número de días del mes no es uniforme. Un *matriz escalonada*, que también se denomina un *matriz de matrices*, está diseñado para estos escenarios. Una matriz escalonada es una matriz cuyos elementos también son matrices. Una matriz escalonada y cada elemento de una matriz escalonada pueden tener una o más dimensiones.

El ejemplo siguiente usa una matriz de meses, cada elemento del que es una matriz de días. El ejemplo utiliza una matriz escalonada porque distintos meses tienen un número diferente de días.  El ejemplo muestra cómo crear una matriz escalonada, asignar valores a él y recuperar y mostrar sus valores.

[!code-vb[jagged-arrays](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]

El ejemplo anterior asigna valores a la matriz escalonada según un elemento por elemento mediante el uso de un `For...Next` bucle. También puede asignar valores a los elementos de una matriz escalonada mediante literales de matriz anidados. Sin embargo, anidada al intentar utilizar literales de matriz (por ejemplo, `Dim valuesjagged = {{1, 2}, {2, 3, 4}}`) genera el error del compilador [BC30568](../../../,,/../misc/bc30568.md). Para corregir el error, encierre los literales de matriz internos entre paréntesis. Los paréntesis fuerzan la expresión literal de matriz que se debe evaluar y los valores resultantes se utilizan con el exterior literal de matriz, como se muestra en el ejemplo siguiente.

[!code-vb[jagged-array-initialization](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)]

Una matriz escalonada es una matriz unidimensional cuyos elementos contienen las matrices. Por lo tanto, el <xref:System.Array.Length%2A?displayProperty=nameWithType> propiedad y el `Array.GetLength(0)` método devuelve el número de elementos en la matriz unidimensional, y `Array.GetLength(1)` produce una <xref:System.IndexOutOfRangeException> porque una matriz escalonada no es multidimensional. Determinar el número de elementos de cada submatriz recuperando el valor de cada submatriz <xref:System.Array.Length%2A?displayProperty=nameWithType> propiedad. El ejemplo siguiente muestra cómo determinar el número de elementos de una matriz escalonada.

[!code-vb[jagged-array-size](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)]

## <a name="zero-length-arrays"></a>Matrices de longitud cero

Visual Basic marca la diferencia entre una matriz sin inicializar (una matriz cuyo valor es `Nothing`) y un *matriz de longitud cero* o matriz vacía (una matriz sin elementos). Una matriz sin inicializar es aquel que no ha sido dimensionada o tenía asignado ningún valor. Por ejemplo:

```vb
Dim arr() As String
```

Una matriz de longitud cero se declara con una dimensión de -1. Por ejemplo:

```vb
Dim arrZ(-1) As String
```

Puede que tenga que crear una matriz de longitud cero en las circunstancias siguientes:

- Sin arriesgar una <xref:System.NullReferenceException> excepción, el código debe tener acceso a los miembros de la <xref:System.Array> clase, como <xref:System.Array.Length%2A> o <xref:System.Array.Rank%2A>, o llamar a una función de Visual Basic, como <xref:Microsoft.VisualBasic.Information.UBound%2A>.

- Desea simplificar el código al no tener que comprobar `Nothing` como un caso especial.

- El código interactúa con una interfaz de programación de aplicaciones (API) que requiere pasar una matriz de longitud cero a uno o más procedimientos o que devuelve una matriz de longitud cero desde uno o más procedimientos.

## <a name="splitting-an-array"></a>División de una matriz

En algunos casos, necesita dividir una sola matriz varias matrices. Esto implica que identifica el punto o puntos en el que se va a dividir la matriz y, a continuación, escupir la matriz en dos o más matrices independientes.

> [!NOTE]
> En esta sección describen la dividir una cadena única en una matriz de cadenas según algún delimitador. Para obtener información sobre la división de una cadena, vea el <xref:System.String.Split%2A?displayProperty=nameWithType> método.

Los criterios para dividir una matriz más comunes son:

- Número de elementos de la matriz. Por ejemplo, es posible que desee dividir un conjunto de más de un número especificado de elementos en un número de partes iguales aproximadamente. Para ello, puede usar el valor devuelto por la <xref:System.Array.Length%2A?displayProperty=nameWithType> o <xref:System.Array.GetLength%2A?displayProperty=nameWithType> método.

- El valor de un elemento, que actúa como un delimitador que indica dónde se debe dividir la matriz. Puede buscar un valor específico mediante una llamada a la <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> y <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> métodos.

Una vez que haya determinado el índice o índices en el que se debe dividir la matriz, a continuación, puede crear las matrices individuales mediante una llamada a la <xref:System.Array.Copy%2A?displayProperty=nameWithType> método.

El ejemplo siguiente divide una matriz en dos matrices de aproximadamente el mismo tamaño. (Si el número total de elementos de la matriz es impar, la primera matriz tiene más de un elemento que el segundo).

[!code-vb[splitting-an-array-by-length](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)]

El ejemplo siguiente divide una matriz de cadenas en dos matrices en función de la presencia de un elemento cuyo valor es "zzz", que actúa como el delimitador de matriz. Las nuevas matrices no incluyen el elemento que contiene el delimitador.

[!code-vb[splitting-an-array-by-delimiter](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)]

## <a name="joining-arrays"></a>Unirse a matrices

También puede combinar un número de matrices en una sola matriz más grande. Para ello, utilice también el <xref:System.Array.Copy%2A?displayProperty=nameWithType> método.

> [!NOTE]
> En esta sección describen la unirse a una matriz de cadenas en una sola cadena. Para obtener información sobre la unión a una matriz de cadenas, vea el <xref:System.String.Join%2A?displayProperty=nameWithType> método.

Antes de copiar los elementos de cada matriz en la nueva matriz, primero debe asegurarse de que se ha inicializado la matriz para que sea suficientemente grande como para dar cabida a la nueva matriz. Hay dos maneras de hacerlo:

- Use la [ `ReDim Preserve` ](../../../language-reference/statements/redim-statement.md) instrucción expandir dinámicamente la matriz antes de agregar nuevos elementos a él. Ésta es la técnica más sencilla, pero puede provocar una degradación del rendimiento y consumo de memoria excesivo cuando va a copiar matrices de gran tamaño.
- Calcular el número total de elementos que necesita para la nueva matriz de gran tamaño, a continuación, agregarle los elementos de cada matriz de origen.

El ejemplo siguiente usa el segundo enfoque para agregar cuatro matrices con diez elementos a una sola matriz.

[!code-vb[joining-an-array](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)]

Puesto que en este caso, las matrices de origen son todos los pequeñas, podemos expandir dinámicamente también la matriz de medida que se agreguen los elementos de cada matriz nuevo a él. En el siguiente ejemplo se realiza esto.

[!code-vb[joining-an-array-dynamically](~/samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)]

## <a name="collections-as-an-alternative-to-arrays"></a>Colecciones como alternativa a las matrices

Las matrices son muy útiles para crear y trabajar con un número fijo de objetos fuertemente tipados. Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos. A diferencia de las matrices, que requiere que cambie explícitamente el tamaño de una matriz con el [ `ReDim` instrucción](../../../language-reference/statements/redim-statement.md), colecciones de crecer y reducirse dinámicamente a medida que las necesidades de un cambio en la aplicación.

Cuando usas `ReDim` para dimensiones de matriz, Visual Basic crea una nueva matriz y libera la anterior. Esto requiere tiempo de ejecución. Por lo tanto, si el número de elementos que trabaja cambia con frecuencia, o si no puede predecir el número máximo de elementos que necesita, normalmente obtendrá un mejor rendimiento mediante el uso de una colección.

Para algunas colecciones, puede asignar una clave a cualquier objeto que incluya en la colección para, de este modo, recuperar rápidamente el objeto con la clave.

Si la colección contiene elementos de un solo tipo de datos, puede usar una de las clases del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> . Una colección genérica cumple la seguridad de tipos para que ningún otro tipo de datos se pueda agregar a ella.

Para más información sobre las colecciones, vea [Colecciones](../../concepts/collections.md).

## <a name="related-topics"></a>Temas relacionados

|Término|de esquema JSON|
|----------|----------------|
|[Array Dimensions in Visual Basic](../../language-features/arrays/array-dimensions.md)|Explica el rango y las dimensiones de las matrices.|
|[Cómo: Inicializar una Variable de matriz en Visual Basic](../../language-features/arrays/how-to-initialize-an-array-variable.md)|Describe cómo se llenan las matrices con valores iniciales.|
|[Cómo: Ordenar una matriz en Visual Basic](../../language-features/arrays/how-to-sort-an-array.md)|Muestra cómo ordenar alfabéticamente los elementos de una matriz.|
|[Cómo: Asignar una matriz a otra](../../language-features/arrays/how-to-assign-one-array-to-another-array.md)|Describe las reglas y los pasos para asignar una matriz a otra variable de matriz.|
|[Solución de problemas de matrices](../../language-features/arrays/troubleshooting-arrays.md)|Describe algunos problemas comunes que surgen al trabajar con matrices.|

## <a name="see-also"></a>Vea también

- <xref:System.Array?displayProperty=nameWithType>
- [Dim (instrucción)](../../../language-reference/statements/dim-statement.md)
- [ReDim (instrucción)](../../../language-reference/statements/redim-statement.md)
