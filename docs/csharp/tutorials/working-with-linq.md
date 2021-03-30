---
title: Trabajar con LINQ
description: En este tutorial se enseña cómo generar secuencias con LINQ, escribir métodos para su uso en consultas LINQ y distinguir entre la evaluación diligente y diferida.
ms.date: 10/29/2018
ms.technology: csharp-linq
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: e6c241e90865335707f8d050f4bf8772f945355d
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874503"
---
# <a name="work-with-language-integrated-query-linq"></a>Uso de Language-Integrated Query (LINQ)

## <a name="introduction"></a>Introducción

En este tutorial aprenderá varias características de .NET Core y el lenguaje C#. Aprenderá a:

- Generar secuencias con LINQ.
- Escribir métodos que puedan usarse fácilmente en las consultas LINQ.
- Distinguir entre evaluación diligente y diferida.

Aprenderá estas técnicas mediante la creación de una aplicación que muestra uno de los conocimientos básicos de cualquier mago: el [orden aleatorio faro](https://en.wikipedia.org/wiki/Faro_shuffle). En resumen, el orden aleatorio faro es una técnica basada en dividir la baraja exactamente por la mitad; a continuación, el orden aleatorio intercala cada carta de cada mitad de la baraja hasta volver a crear la original.

Los magos usan esta técnica porque cada carta está en una ubicación conocida después de cada orden aleatorio, y el orden sigue un patrón de repetición.

Para el propósito sobre el que trata este artículo, resulta divertido ocuparnos de la manipulación de secuencias de datos. La aplicación que se va a crear compilará una baraja de cartas y después realizará una secuencia de órdenes aleatorios, que escribirá cada vez la secuencia completa. También podrá comparar el orden actualizado con el original.

Este tutorial consta de varios pasos. Después de cada paso, puede ejecutar la aplicación y ver el progreso. También puede ver el [ejemplo completo](https://github.com/dotnet/samples/blob/main/csharp/getting-started/console-linq) en el repositorio dotnet/samples de GitHub. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página [Descarga de .NET Core](https://dotnet.microsoft.com/download). Puede ejecutar esta aplicación en Windows, Ubuntu Linux, OS X o en un contenedor de Docker. Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.

## <a name="create-the-application"></a>Crear la aplicación

El primer paso es crear una nueva aplicación. Abra un símbolo del sistema y cree un nuevo directorio para la aplicación. Conviértalo en el directorio actual. Escriba el comando `dotnet new console` en el símbolo del sistema. Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo".

Si nunca ha usado C# antes, en [este tutorial](console-teleprompter.md) se explica la estructura de un programa con C#. Puede leerlo y después volver aquí para obtener más información sobre LINQ.

## <a name="create-the-data-set"></a>Creación del conjunto de datos

Antes de empezar, asegúrese de que las líneas siguientes se encuentran al principio del archivo `Program.cs` generado por `dotnet new console`:

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

Si estas tres líneas (instrucciones `using`) no se encuentran al principio del archivo, nuestro programa no se compilará.

Ahora que tiene todas las referencias que necesitará, tenga en cuenta lo que constituye una baraja de cartas. Habitualmente, una baraja de cartas tiene cuatro palos y cada palo tiene trece valores. Normalmente, podría plantearse crear una clase `Card` directamente del archivo bat y rellenar manualmente una colección de objetos `Card`. Con LINQ, puede ser más conciso que de costumbre al tratar con la creación de una baraja de cartas. En lugar de crear una clase `Card`, puede crear dos secuencias para representar los palos y rangos, respectivamente. Podrá crear un par sencillo de [*métodos iterator*](../iterators.md#enumeration-sources-with-iterator-methods) que generará las clasificaciones y palos como objetos <xref:System.Collections.Generic.IEnumerable%601> de cadenas:

```csharp
// Program.cs
// The Main() method

static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

Colóquelos debajo del método `Main` en el archivo `Program.cs`. Estos dos métodos utilizan la sintaxis `yield return` para generar una secuencia mientras se ejecutan. El compilador crea un objeto que implementa <xref:System.Collections.Generic.IEnumerable%601> y genera la secuencia de cadenas conforme se solicitan.

Ahora, puede usar estos métodos iterator para crear la baraja de cartas. Insertará la consulta LINQ en nuestro método `Main`. Aquí tiene una imagen:

```csharp
// Program.cs
static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    // Display each card that we've generated and placed in startingDeck in the console
    foreach (var card in startingDeck)
    {
        Console.WriteLine(card);
    }
}
```

Las cláusulas múltiples `from` generan una salida <xref:System.Linq.Enumerable.SelectMany%2A>, que crea una única secuencia a partir de la combinación de cada elemento de la primera secuencia con cada elemento de la segunda secuencia. El orden es importante para nuestros propósitos. El primer elemento de la primera secuencia de origen (palos) se combina con todos los elementos de la segunda secuencia (clasificaciones). Esto genera las trece cartas del primer palo. Dicho proceso se repite con cada elemento de la primera secuencia (palos). El resultado final es una baraja de cartas ordenadas por palos, seguidos de valores.

Es importante tener en cuenta que si decide escribir las instrucciones LINQ en la sintaxis de consulta usada anteriormente o utilizar la sintaxis de método en su lugar, siempre es posible pasar de una forma de sintaxis a la otra. La consulta anterior escrita en la sintaxis de consulta puede escribirse en la sintaxis de método como:

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

El compilador convierte las instrucciones LINQ escritas en la sintaxis de consulta a la sintaxis de llamada de método equivalente. Por consiguiente, independientemente de la sintaxis que prefiera, las dos versiones de la consulta producen el mismo resultado. Elija la sintaxis más adecuada a su situación: por ejemplo, si trabaja en un equipo en el que algunos de sus miembros tienen dificultades con la sintaxis de método, procure usar la sintaxis de consulta.

Continúe y ejecute el ejemplo que se ha creado en este punto. Mostrará todas las 52 cartas de la baraja. Puede ser muy útil ejecutar este ejemplo en un depurador para observar cómo se ejecutan los métodos `Suits()` y `Ranks()`. Puede ver claramente que cada cadena de cada secuencia se genera solo según sea necesario.

![Una ventana de la consola que muestra la aplicación escribiendo 52 tarjetas.](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulate-the-order"></a>Manipulación del orden

Seguidamente, céntrese en cómo va a establecer el orden aleatorio de las cartas de la baraja. El primer paso en cualquier orden aleatorio consiste en dividir la baraja en dos. Los métodos <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> que forman parte de las LINQ API le ofrecen esa característica: Colóquelos debajo del bucle `foreach`:

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    // 52 cards in a deck, so 52 / 2 = 26
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
}
```

Pero no existe ningún método de orden aleatorio en la biblioteca estándar que pueda aprovechar, por lo que tendrá que escribir el suyo propio. El método de orden aleatorio que cree mostrará varias técnicas que se utilizan con programas basados en LINQ, por lo que cada parte de este proceso se explica en pasos.

Para agregar alguna funcionalidad a la forma de interactuar con el elemento <xref:System.Collections.Generic.IEnumerable%601> que obtendrá de las consultas LINQ, tendrá que escribir algunos tipos especiales de métodos llamados [métodos de extensión](../programming-guide/classes-and-structs/extension-methods.md). En resumen, un método de extensión es un *método estático* con una finalidad específica que agrega nueva funcionalidad a un tipo existente sin tener que modificar el tipo original al que quiere agregar la funcionalidad.

Proporcione un nuevo espacio a sus métodos de extensión agregando un nuevo archivo de clase *estática* al programa denominado `Extensions.cs` y comience a compilar el primer método de extensión:

```csharp
// Extensions.cs
using System;
using System.Collections.Generic;
using System.Linq;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>(this IEnumerable<T> first, IEnumerable<T> second)
        {
            // Your implementation will go here soon enough
        }
    }
}
```

Mire la firma del método por un momento, concretamente los parámetros:

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

Puede ver la incorporación del modificador `this` del primer argumento al método. Esto significa que se llama al método como si fuese un método de miembro del tipo del primer argumento. Esta declaración de método también sigue una expresión estándar donde los tipos de entrada y salida son `IEnumerable<T>`. Dicha práctica permite que los métodos LINQ se encadenen entre sí para realizar consultas más complejas.

Naturalmente, dado que dividió la baraja en mitades, tendrá que unir esas mitades. En el código, esto significa que enumerará las dos secuencias adquiridas a través de <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> a la vez, *`interleaving`* los elementos y crear una sola secuencia: su baraja de cartas recién ordenada aleatoriamente. Escribir un método LINQ que funciona con dos secuencias requiere que comprenda cómo funciona <xref:System.Collections.Generic.IEnumerable%601>.

La interfaz <xref:System.Collections.Generic.IEnumerable%601> tiene un método: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>. El objeto devuelto por <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> tiene un método para desplazarse al siguiente elemento, así como una propiedad que recupera el elemento actual de la secuencia. Utilizará estos dos miembros para enumerar la colección y devolver los elementos. Este método de intercalación será un método iterador, por lo que en lugar de crear una colección y devolverla, usará la sintaxis `yield return` anterior.

A continuación se muestra la implementación de ese método:

[!CODE-csharp[InterleaveSequenceWith](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

Ahora que ha escrito este método, vuelva al método `Main` y ordene la baraja aleatoriamente una vez:

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a>Comparaciones

¿Cuántos órdenes aleatorios se necesitan para devolver la baraja a su orden original? Para averiguarlo, debe escribir un método que determine si dos secuencias son iguales. Cuando ya disponga del método, debe colocar el código que ordena la baraja aleatoriamente en un bucle y comprobarlo para ver cuándo la baraja vuelve a tener su orden original.

Debe ser sencillo escribir un método para determinar si las dos secuencias son iguales. Presenta una estructura similar al método que se escribió para ordenar la baraja aleatoriamente. Solo que esta vez, en lugar de aplicar `yield return` a cada elemento, se compararán los elementos coincidentes de cada secuencia. Después de que se haya enumerado la secuencia completa, si cada elemento coincide, las secuencias son las mismas:

[!CODE-csharp[SequenceEquals](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

Esto muestra una segunda expresión LINQ: los métodos de terminal. Adoptan una secuencia como entrada (o, en este caso, dos secuencias) y devuelven un único valor escalar. Cuando se utilizan métodos de terminal, siempre son el método final en una cadena de métodos para una consulta LINQ, de ahí el nombre "terminal".

Puede ver esto en acción cuando lo usa para determinar cuándo la baraja vuelve a tener su orden original. Coloque el código de orden aleatorio dentro de un bucle y deténgalo cuando la secuencia vuelva a su orden original, mediante la aplicación del método `SequenceEquals()`. Puede observar que siempre se tratará del método final de cualquier consulta, porque devuelve un único valor en lugar de una secuencia:

```csharp
// Program.cs
static void Main(string[] args)
{
    // Query for building the deck

    // Shuffling using InterleaveSequenceWith<T>();

    var times = 0;
    // We can re-use the shuffle variable from earlier, or you can make a new one
    shuffle = startingDeck;
    do
    {
        shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

        foreach (var card in shuffle)
        {
            Console.WriteLine(card);
        }
        Console.WriteLine();
        times++;

    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

Ejecute el código que tenga hasta el momento y tome nota de cómo la baraja se reorganiza en cada orden aleatorio. Después de ocho órdenes aleatorios (iteraciones del bucle do-while), la baraja vuelve a la configuración original en que se encontraba cuando la creó a partir la consulta LINQ inicial.

## <a name="optimizations"></a>Optimizaciones

El ejemplo creado hasta el momento se ejecuta *en orden no aleatorio*, donde las cartas superiores e inferiores son las mismas en cada ejecución. Vamos a realizar un cambio: utilizaremos una ejecución *en orden aleatorio* en su lugar, donde las 52 cartas cambian de posición. Si se trata de un orden aleatorio, intercale la baraja de tal forma que la primera carta de la mitad inferior sea la primera carta de la baraja. Esto significa que la última carta de la mitad superior será la carta inferior. Se trata de un cambio simple en una única línea de código. Actualice la consulta de orden aleatorio actual cambiando las posiciones de <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A>. Se cambiará al orden de las mitades superior e inferior de la baraja:

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

Vuelva a ejecutar el programa y verá que, para que la baraja se reordene, se necesitan 52 iteraciones. También empezará a observar algunas degradaciones graves de rendimiento a medida que el programa continúa en ejecución.

Esto se debe a varias razones. Puede que se trate de una de las principales causas de este descenso de rendimiento: un uso ineficaz de la [*evaluación diferida*](../../standard/linq/deferred-execution-lazy-evaluation.md).

En pocas palabras, la evaluación diferida indica que no se realiza la evaluación de una instrucción hasta que su valor es necesario. Las consultas LINQ son instrucciones se evalúan de forma diferida. Las secuencias se generan solo a medida que se solicitan los elementos. Normalmente, es una ventaja importante de LINQ. Sin embargo, en un uso como el que hace este programa, se produce un aumento exponencial del tiempo de ejecución.

Recuerde que la baraja original se generó con una consulta LINQ. Cada orden aleatorio se genera mediante la realización de tres consultas LINQ sobre la baraja anterior. Todas se realizan de forma diferida. Eso también significa que se vuelven a llevar a cabo cada vez que se solicita la secuencia. Cuando llegue a la iteración número 52, habrá regenerado la baraja original demasiadas veces. Se va a escribir un registro para mostrar este comportamiento. A continuación, podrá corregirlo.

En su archivo `Extensions.cs`, escriba o copie el siguiente método. Este método de extensión crea otro archivo denominado `debug.log` en el directorio del proyecto y registra la consulta que se ejecuta actualmente en el archivo de registro. Este método de extensión se puede anexar a una consulta para marcar que se ha ejecutado.

[!CODE-csharp[LogQuery](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

Verá un subrayado en zigzag rojo bajo `File`, lo que indica que no existe. No se compilará, ya que el compilador no sabe qué es `File`. Para solucionar este problema, asegúrese de agregar la siguiente línea de código bajo la primera línea de `Extensions.cs`:

```csharp
using System.IO;
```

Esto debería resolver el problema y el error en rojo debería desaparecer.

A continuación, instrumente la definición de cada consulta con un mensaje de registro:

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        // Out shuffle
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        // In shuffle
        shuffle = shuffle.Skip(26).LogQuery("Bottom Half")
                .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
                .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

Observe que no se genera un registro cada vez que accede a una consulta. El registro solo se genera cuando crea la consulta original. El programa todavía tarda mucho tiempo en ejecutarse, pero ahora puede ver por qué. Si se le agota la paciencia al ejecutar el orden aleatorio interno con los registros activados, vuelva al orden aleatorio externo. Aún puede ver los efectos de la evaluación diferida. En una ejecución, ejecuta 2592 consultas, incluida toda la generación de palos y valores.

Aquí puede mejorar el rendimiento del código para reducir el número de ejecuciones que realiza. Una corrección sencilla que puede hacer es almacenar en *caché* los resultados de la consulta LINQ original que construye la baraja de cartas. Actualmente, ejecuta las consultas una y otra vez siempre que el bucle do-while pasa por una iteración, lo que vuelve a construir la baraja de cartas y cambia continuamente el orden aleatorio. Para almacenar en caché la baraja de cartas, puede aprovechar los métodos LINQ <xref:System.Linq.Enumerable.ToArray%2A> y <xref:System.Linq.Enumerable.ToList%2A>; cuando los anexe a las consultas, realizarán las mismas acciones que les ha indicado que hagan, pero ahora almacenarán los resultados en una matriz o una lista, según el método al que elija llamar. Anexe el método <xref:System.Linq.Enumerable.ToArray%2A> de LINQ a las dos consultas y ejecute de nuevo el programa:

[!CODE-csharp[Main](../../../samples/snippets/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

Ahora el orden aleatorio externo se reduce a 30 consultas. Vuelva a ejecutarlo con el orden aleatorio interno y verá mejoras similares: ahora ejecuta 162 consultas.

Este ejemplo está **diseñado** para resaltar los casos de uso en que la evaluación diferida puede generar dificultades de rendimiento. Si bien es importante ver dónde la evaluación diferida puede afectar al rendimiento del código, es igualmente importante entender que no todas las consultas deben ejecutarse de manera diligente. El resultado de rendimiento en el que incurre sin usar <xref:System.Linq.Enumerable.ToArray%2A> se debe a que cada nueva disposición de la baraja de cartas se crea a partir de la disposición anterior. La evaluación diferida supone que cada nueva configuración de la baraja se realiza a partir de la baraja original, incluso con la ejecución del código que crea el elemento `startingDeck`. Esto conlleva una gran cantidad de trabajo adicional.

En la práctica, algunos algoritmos se ejecutan bien con la evaluación diligente y otros, con la evaluación diferida. Para el uso diario, la evaluación diferida suele ser una mejor opción cuando el origen de datos es un proceso independiente, como un motor de base de datos. Para las bases de datos, la evaluación diferida permite realizar consultas más complejas que ejecuten un solo recorrido de ida y vuelta al procesamiento de la base de datos y vuelvan al resto del código. LINQ es flexible tanto si decide usar la evaluación diligente como la diferida, así que calibre sus procesos y elija el tipo de evaluación que le ofrece el mejor rendimiento.

## <a name="conclusion"></a>Conclusión

En este proyecto ha tratado lo siguiente:

- Uso de consultas LINQ para agregar datos a una secuencia significativa
- Escritura de métodos de extensión para agregar nuestra propia funcionalidad personalizada a las consultas LINQ
- Localización de áreas en nuestro código donde nuestras consultas LINQ pueden tener problemas de rendimiento como la degradación de la velocidad
- Evaluación diligente y diferida en lo que respecta a las consultas LINQ y las implicaciones que podrían tener en el rendimiento de la consulta

Aparte de LINQ, ha aprendido algo sobre una técnica que los magos utilizan para hacer trucos de cartas. Los magos usan el orden aleatorio Faro porque les permite controlar dónde está cada carta en la baraja. Ahora que lo conoce, no se lo estropee a los demás.

Para más información sobre LINQ, vea:

- [Language-Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md)
- [Introducción a LINQ](../programming-guide/concepts/linq/index.md)
- [Operaciones básicas de consulta LINQ (C#)](../programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Transformaciones de datos con LINQ (C#)](../programming-guide/concepts/linq/data-transformations-with-linq.md)
- [Sintaxis de consultas y sintaxis de métodos en LINQ (C#)](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
- [Características de C# compatibles con LINQ](../programming-guide/concepts/linq/features-that-support-linq.md)
