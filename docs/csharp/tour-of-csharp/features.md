---
title: 'Recorrido por C#: áreas principales del lenguaje'
description: ¿Nuevo en C#? Conozca los conceptos básicos del lenguaje. Este artículo contiene una encuesta sobre las principales características del lenguaje.
ms.date: 08/06/2020
ms.openlocfilehash: 943701b544dd3495fa2286e804e2566da146cb45
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216660"
---
# <a name="major-language-areas"></a>Áreas principales del lenguaje

## <a name="arrays-collections-and-linq"></a>Matrices, colecciones y LINQ

C# y .NET proporcionan muchos tipos de colecciones diferentes. Las matrices tienen una sintaxis definida por el lenguaje. Los tipos de colecciones genéricos se enumeran en el espacio de nombres <xref:System.Collections.Generic?displayProperty=fullName>. Las colecciones especializadas incluyen <xref:System.Span%601?displayProperty=nameWithType> para acceder a la memoria continua en el marco de pila, así como <xref:System.Memory%601?displayProperty=nameWithType> para acceder a la memoria continua en el montón administrado. Todas las colecciones, incluidas las matrices, <xref:System.Span%601> y <xref:System.Memory%601>, comparten un principio unificador para la iteración. Puede usar la interfaz <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Este principio unificador implica que cualquiera de los tipos de colecciones se puede usar con consultas LINQ u otros algoritmos. Los métodos se escriben mediante <xref:System.Collections.Generic.IEnumerable%601>, y esos algoritmos funcionan con cualquier colección.

### <a name="arrays"></a>Matrices

Una matriz [***array** _](../programming-guide/arrays/index.md) es una estructura de datos que contiene un número de variables a las que se accede mediante índices calculados. Las variables contenidas en una matriz, denominadas también _*_elementos_*_ de la matriz, son todas del mismo tipo. Este tipo se denomina _*_tipo de elemento_*_ de la matriz.

Los tipos de matriz son tipos de referencia, y la declaración de una variable de matriz simplemente establece un espacio reservado para una referencia a una instancia de matriz. Las instancias de matriz reales se crean dinámicamente en tiempo de ejecución mediante el operador `new`. La operación `new` especifica la _*_longitud_*_ de la nueva instancia de matriz, que luego se fija para la vigencia de la instancia. Los índices de los elementos de una matriz van de `0` a `Length - 1`. El operador `new` inicializa automáticamente los elementos de una matriz a su valor predeterminado, que, por ejemplo, es cero para todos los tipos numéricos y `null` para todos los tipos de referencias.

En el ejemplo siguiente se crea una matriz de elementos `int`, se inicializa y se imprime su contenido.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArraysSample":::

Este ejemplo se crea y se pone en funcionamiento en una _*_matriz unidimensional_*_. C# también admite _*_matrices multidimensionales_*_. El número de dimensiones de un tipo de matriz, conocido también como _*_clasificación_*_ del tipo de matriz, es una más el número de comas entre los corchetes del tipo de matriz. En el ejemplo siguiente se asignan una matriz unidimensional, bidimensional y tridimensional, respectivamente.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DeclareArrays":::

La matriz `a1` contiene 10 elementos, la matriz `a2` 50 (10 × 5) elementos y la matriz `a3` 100 (10 × 5 × 2) elementos.
El tipo de elemento de una matriz puede ser cualquiera, incluido un tipo de matriz. Una matriz con elementos de un tipo de matriz a veces se conoce como _*_matriz escalonada_*_ porque las longitudes de las matrices de elementos no tienen que ser iguales. En el ejemplo siguiente se asigna una matriz de matrices de `int`:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArrayOfArrays":::

La primera línea crea una matriz con tres elementos, cada uno de tipo `int[]` y cada uno con un valor inicial de `null`. Las líneas siguientes inicializan entonces los tres elementos con referencias a instancias de matriz individuales de longitud variable.

El operador `new` permite especificar los valores iniciales de los elementos de matriz mediante un _*_inicializador de matriz_*_, que es una lista de las expresiones escritas entre los delimitadores `{` y `}`. En el ejemplo siguiente se asigna e inicializa un tipo `int[]` con tres elementos.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeArray":::

La longitud de la matriz se deduce del número de expresiones entre `{` y `}`. La inicialización de la matriz se puede acortar aún más, de modo que no sea necesario reformular el tipo de matriz.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeShortened":::

Los dos ejemplos anteriores son equivalentes al código siguiente:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeGenerated":::

La instrucción `foreach` se puede utilizar para enumerar los elementos de cualquier colección. El código siguiente numera la matriz del ejemplo anterior:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="EnumerateArray":::

La instrucción `foreach` utiliza la interfaz <xref:System.Collections.Generic.IEnumerable%601>, por lo que puede trabajar con cualquier colección.

## <a name="string-interpolation"></a>Interpolación de cadenas

La [_*_interpolación de cadenas_*_](../language-reference/tokens/interpolated.md) de C# le permite dar formato a las cadenas mediante la definición de expresiones cuyos resultados se colocan en una cadena de formato. Por ejemplo, en el ejemplo siguiente se imprime la temperatura de un día determinado a partir de un conjunto de datos meteorológicos:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="StringInterpolation":::

Una cadena interpolada se declara mediante el token `$`. La interpolación de cadenas evalúa las expresiones entre `{` y `}`, convierte el resultado en un elemento `string` y reemplaza el texto entre corchetes por el resultado de cadena de la expresión. El elemento `:` presente en la primera expresión, `{weatherData.Date:MM-DD-YYYY}`, especifica la _cadena de formato*. En el ejemplo anterior, especifica que la fecha debe imprimirse en formato "MM-DD-AAAA".

## <a name="pattern-matching"></a>Detección de patrones

El lenguaje C# proporciona expresiones de [***coincidencia de patrones** _](../pattern-matching.md) para consultar el estado de un objeto y ejecutar código basado en dicho estado. Puede inspeccionar los tipos y los valores de las propiedades y los campos para determinar qué acción se debe realizar. La expresión `switch` es la expresión primaria para la coincidencia de patrones.

## <a name="delegates-and-lambda-expressions"></a>Delegados y expresiones lambda

Un [_*_tipo de delegado_*_](../delegates-overview.md) representa las referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto. Los delegados permiten tratar métodos como entidades que se puedan asignar a variables y se puedan pasar como parámetros. Los delegados son similares al concepto de punteros de función de otros lenguajes. A diferencia de los punteros de función, los delegados están orientados a objetos y tienen seguridad de tipos.

En el siguiente ejemplo se declara y usa un tipo de delegado denominado `Function`.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DelegateExample":::

Una instancia del tipo de delegado `Function` puede hacer referencia a cualquier método que tome un argumento `double` y devuelva un valor `double`. El método `Apply` aplica un elemento `Function` determinado a los elementos de `double[]` y devuelve `double[]` con los resultados. En el método `Main`, `Apply` se usa para aplicar tres funciones diferentes a un valor `double[]`.

Un delegado puede hacer referencia a un método estático (como `Square` o `Math.Sin` en el ejemplo anterior) o un método de instancia (como `m.Multiply` en el ejemplo anterior). Un delegado que hace referencia a un método de instancia también hace referencia a un objeto determinado y, cuando se invoca el método de instancia a través del delegado, ese objeto se convierte en `this` en la invocación.

Los delegados también se pueden crear mediante funciones anónimas, que son "métodos insertados" que se crean al declararlos. Las funciones anónimas pueden ver las variables locales de los métodos adyacentes. En el ejemplo siguiente no se crea una clase:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseDelegate":::

Un delegado no conoce la clase del método al que hace referencia; de hecho, tampoco tiene importancia. Lo único que importa es que el método al que se hace referencia tenga los mismos parámetros y tipo de valor devuelto que el delegado.

## <a name="async--await"></a>async y await

C# admite programas asincrónicos con dos palabras clave: `async` y `await`. Puede agregar el modificador `async` a una declaración de método para declarar que dicho método es asincrónico. El operador `await` indica al compilador que espere de forma asincrónica a que finalice un resultado. El control se devuelve al autor de la llamada, y el método devuelve una estructura que administra el estado del trabajo asincrónico. Normalmente, la estructura es un elemento <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>, pero puede ser cualquier tipo que admita el patrón awaiter. Estas características permiten escribir código que se lee como su homólogo sincrónico, pero que se ejecuta de forma asincrónica. Por ejemplo, el código siguiente descarga la página principal de [Microsoft Docs](/):

:::code language="csharp" source="./snippets/shared/Features.cs" ID="AsyncExample":::

En este pequeño ejemplo se muestran las características principales de la programación asincrónica:

- La declaración del método incluye el modificador `async`.
- El cuerpo del método espera (`await`) a la devolución del método `GetByteArrayAsync`.
- El tipo especificado en la instrucción `return` coincide con el argumento de tipo de la declaración `Task<T>` para el método. (Un método que devuelva `Task` usará instrucciones `return` sin ningún argumento).

## <a name="attributes"></a>Atributos

Los tipos, los miembros y otras entidades en un programa de C # admiten modificadores que controlan ciertos aspectos de su comportamiento. Por ejemplo, la accesibilidad de un método se controla mediante los modificadores `public`, `protected`, `internal` y `private`. C # generaliza esta funcionalidad de manera que los tipos de información declarativa definidos por el usuario se puedan adjuntar a las entidades del programa y recuperarse en tiempo de ejecución. Los programas especifican esta información declarativa adicional mediante la definición y el uso de [_ *_atributos_**](../programming-guide/concepts/attributes/index.md).

En el ejemplo siguiente se declara un atributo `HelpAttribute` que se puede colocar en entidades de programa para proporcionar vínculos a la documentación asociada.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DefineAttribute":::

Todas las clases de atributos se derivan de la clase base <xref:System.Attribute> proporcionada por la biblioteca .NET. Los atributos se pueden aplicar proporcionando su nombre, junto con cualquier argumento, entre corchetes, justo antes de la declaración asociada. Si el nombre de un atributo termina en `Attribute`, esa parte del nombre se puede omitir cuando se hace referencia al atributo. Por ejemplo, `HelpAttribute` se puede usar de la manera siguiente.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseAttributes":::

En este ejemplo se adjunta un atributo `HelpAttribute` a la clase `Widget`. También se agrega otro atributo `HelpAttribute` al método `Display` en la clase. Los constructores públicos de una clase de atributos controlan la información que se debe proporcionar cuando el atributo se adjunta a una entidad de programa. Se puede proporcionar información adicional haciendo referencia a las propiedades públicas de lectura y escritura de la clase de atributos (como la referencia a la propiedad `Topic` usada anteriormente).

Los metadatos definidos por atributos pueden leerse y manipularse en tiempo de ejecución mediante reflexión. Cuando se solicita un atributo determinado mediante esta técnica, se invoca el constructor de la clase de atributos con la información proporcionada en el origen del programa. Se devuelve la instancia del atributo resultante. Si se proporciona información adicional mediante propiedades, dichas propiedades se establecen en los valores dados antes de devolver la instancia del atributo.

El siguiente ejemplo de código demuestra cómo obtener las `HelpAttribute`instancias asociadas a la clase `Widget` y su método `Display`.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ReadAttributes":::

## <a name="learn-more"></a>Más información

Puede explorar más sobre C# con uno de nuestros [tutoriales](../tutorials/index.md).

>[!div class="step-by-step"]
>[Anterior](program-building-blocks.md)
