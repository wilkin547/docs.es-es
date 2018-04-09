---
title: Trabajar con LINQ
description: En este tutorial se enseña cómo generar secuencias con LINQ, escribir métodos para su uso en consultas LINQ y distinguir entre la evaluación diligente y diferida.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/28/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: c5720d5391eec327aa2f885fd65579aeb6260488
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="working-with-linq"></a>Trabajar con LINQ

## <a name="introduction"></a>Introducción

Este tutorial le enseña varias características de .NET Core y el lenguaje C#. Aprenderá lo siguiente:

*   Cómo generar secuencias con LINQ
*   Cómo escribir métodos que pueden utilizarse fácilmente en las consultas LINQ.
*   Cómo distinguir entre la evaluación diligente y diferida.

Aprenderá estas técnicas mediante la creación de una aplicación que muestra uno de los conocimientos básicos de cualquier mago: el [orden aleatorio faro](https://en.wikipedia.org/wiki/Faro_shuffle). En resumen, el orden aleatorio faro es una técnica basada en dividir la baraja exactamente por la mitad; a continuación, el orden aleatorio intercala cada carta de cada mitad de la baraja hasta volver a crear la original.

Los magos usan esta técnica porque cada carta está en una ubicación conocida después de cada orden aleatorio, y el orden sigue un patrón de repetición. 

Para el propósito sobre el que trata este artículo, resulta divertido ocuparnos de la manipulación de secuencias de datos. La aplicación que se va a crear compilará una baraja y después realizará una secuencia de órdenes aleatorios, escribiendo cada vez la secuencia completa. También podrá comparar el orden actualizado con el original.

Este tutorial consta de varios pasos. Después de cada paso, puede ejecutar la aplicación y ver el progreso. También puede ver el [ejemplo completo](https://github.com/dotnet/docs/blob/master/samples/csharp/getting-started/console-linq) en el repositorio dotnet/docs de GitHub. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core). Puede ejecutar esta aplicación en Windows, Ubuntu Linux, OS X o en un contenedor de Docker. Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.

## <a name="create-the-application"></a>Crear la aplicación

El primer paso es crear una nueva aplicación. Abra un símbolo del sistema y cree un nuevo directorio para la aplicación. Conviértalo en el directorio actual. Escriba el comando `dotnet new console` en el símbolo del sistema. Esta acción crea los archivos de inicio para una aplicación básica "Hola a todos".

Si nunca ha usado C# antes, en [este tutorial](console-teleprompter.md) se explica la estructura de un programa con C#. Puede leerlo y después volver aquí para obtener más información sobre LINQ. 

## <a name="creating-the-data-set"></a>Creación del conjunto de datos

Comencemos por crear una baraja de cartas. Para ello, debe usar una consulta LINQ que tenga dos orígenes (uno para los cuatro palos y otro para los valores trece). Podrá combinar esos orígenes en una baraja de 52 cartas. Una instrucción `Console.WriteLine` dentro de un bucle `foreach` muestra las cartas.

Aquí está la consulta:

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

Las cláusulas múltiples `from` generan una salida `SelectMany`, que crea una única secuencia a partir de la combinación de cada elemento de la primera secuencia con cada elemento de la segunda secuencia. El orden es importante para nuestros propósitos. El primer elemento de la primera secuencia de origen (palos) se combina con cada elemento de la segunda secuencia (valores). Esto genera las trece cartas del primer palo. Dicho proceso se repite con cada elemento de la primera secuencia (palos). El resultado final es una baraja de cartas ordenadas por palos, seguidos de valores.

A continuación, necesita compilar los métodos Suits() y Ranks(). Comencemos con un conjunto muy sencillo de *métodos iteradores* que generan la secuencia como una enumeración de cadenas:

```csharp
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

Estos dos métodos utilizan la sintaxis `yield return` para generar una secuencia mientras se ejecutan. El compilador crea un objeto que implementa `IEnumerable<T>` y genera la secuencia de cadenas conforme se solicitan.

Continúe y ejecute el ejemplo que se ha creado en este punto. Mostrará todas las 52 cartas de la baraja. Puede ser muy útil ejecutar este ejemplo en un depurador para observar cómo se ejecutan los métodos `Suits()` y `Values()`. Puede ver claramente que cada cadena de cada secuencia se genera solo según sea necesario.

![Ventana de la consola que muestra la aplicación escribiendo 52 cartas](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a>Manipulación del orden

A continuación, se va a crear un método de utilidad que puede llevar a cabo el orden aleatorio. El primer paso consiste en dividir la baraja en dos. Los métodos `Take()` y `Skip()` que forman parte de las API de LINQ ofrecen esa característica:

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

El método de orden aleatorio no existe en la biblioteca estándar, por lo que tendrá que escribir el suyo propio. Este nuevo método muestra varias técnicas que va a utilizar con programas basados en LINQ, cuyas partes se van a explicar en distintos pasos.

La firma del método crea un *método de extensión*:

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

Un método de extensión es un *método estático* para un fin especial. Puede ver la incorporación del modificador `this` del primer argumento al método. Esto significa que se llama al método como si fuese un método de miembro del tipo del primer argumento.

Los métodos de extensión se pueden declarar únicamente dentro de las clases `static`, así que se va a crear una nueva clase estática llamada `extensions` para esta funcionalidad. A medida que avance en este tutorial, va a crear más métodos de extensión, que se colocarán en la misma clase.

Esta declaración de método también sigue una expresión estándar donde los tipos de entrada y salida son `IEnumerable<T>`. Dicha práctica permite que los métodos LINQ se encadenen entre sí para realizar consultas más complejas.

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

Debe enumerar ambas secuencias al mismo tiempo, de tal forma que se intercalarán los elementos y se creará un objeto.  Escribir un método LINQ que funciona con dos secuencias requiere que comprenda cómo funciona `IEnumerable`.

La interfaz `IEnumerable` tiene un método: `GetEnumerator()`. El objeto devuelto por `GetEnumerator()` tiene un método para desplazarse al siguiente elemento, así como una propiedad que recupera el elemento actual de la secuencia. Utilizará estos dos miembros para enumerar la colección y devolver los elementos. Este método de intercalación será un método iterador, por lo que en lugar de crear una colección y devolverla, usará la sintaxis `yield return` anterior. 

A continuación se muestra la implementación de ese método:

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

Ahora que ha escrito este método, vuelva al método `Main` y ordene la baraja aleatoriamente una vez:

```csharp
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

Se va a ver cuántos órdenes aleatorios se necesitan para devolver la baraja a su orden original. Debe escribir un método que determine si dos secuencias son iguales. Cuando ya disponga del método, debe colocar el código que ordena la baraja aleatoriamente en un bucle y comprobarlo para ver cuándo la baraja vuelve a tener su orden original.

Debe ser sencillo escribir un método para determinar si las dos secuencias son iguales. Presenta una estructura similar al método que se escribió para ordenar la baraja aleatoriamente. Solo esta vez, en lugar de devolver el resultado de cada elemento, se compararán los elementos coincidentes de cada secuencia. Después de que se haya enumerado la secuencia completa, si cada elemento coincide, las secuencias son las mismas:

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

Esto muestra una segunda expresión LINQ: métodos de terminales. Adoptan una secuencia como entrada (o, en este caso, dos secuencias) y devuelven un único valor escalar. Estos métodos, cuando se utilizan, son siempre el método final de una consulta. (Por lo tanto, el nombre). 

Puede ver esto en acción cuando lo usa para determinar cuándo la baraja vuelve a tener su orden original. Coloque el código de orden aleatorio dentro de un bucle y deténgalo cuando la secuencia vuelva a su orden original, mediante la aplicación del método `SequenceEquals()`. Puede observar que siempre se tratará del método final de cualquier consulta, porque devuelve un único valor en lugar de una secuencia:

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

Ejecute el ejemplo y observe cómo la baraja se reorganiza en cada orden aleatorio, hasta que vuelva a su configuración original después de 8 iteraciones.

## <a name="optimizations"></a>Optimizaciones

El ejemplo creado hasta el momento se ejecuta *en orden aleatorio*, donde las cartas superiores e inferiores son las mismas en cada ejecución. Se va a realizar un cambio y realice una ejecución *en orden no aleatorio*, donde las 52 cartas cambian de posición. Si se trata de un orden no aleatorio, intercale la baraja de tal forma que la primera carta de la mitad inferior sea la primera carta de la baraja. Esto significa que la última carta de la mitad superior será la carta inferior. Se trata solo de un cambio de línea. Actualice la llamada al orden aleatorio para cambiar el orden de las mitades superior e inferior de la baraja:

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

Vuelva a ejecutar el programa y verá que, para que la baraja se reordene, se necesitan 52 iteraciones. También empezará a observar algunas degradaciones graves de rendimiento a medida que el programa continúa en ejecución.

Esto se debe a varias razones. Vamos a tratar una de las causas principales: un uso ineficaz de la *evaluación diferida*.

Las consultas LINQ se evalúan de forma diferida. Las secuencias se generan solo a medida que se solicitan los elementos. Normalmente, es una ventaja importante de LINQ. Sin embargo, en un uso como el que hace este programa, se produce un aumento exponencial del tiempo de ejecución.

La baraja original se ha generado mediante una consulta LINQ. Cada orden aleatorio se genera mediante la realización de tres consultas LINQ sobre la baraja anterior. Todas se realizan de forma diferida. Eso también significa que se vuelven a llevar a cabo cada vez que se solicita la secuencia. Cuando llegue a la iteración número 52, habrá regenerado la baraja original demasiadas veces. Se va a escribir un registro para mostrar este comportamiento. A continuación, podrá corregirlo.

Se trata de un método de registro que se puede anexar a una consulta para marcar que esta se ha ejecutado.

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

A continuación, instrumente la definición de cada consulta con un mensaje de registro:

```csharp
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
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
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

Observe que no se genera un registro cada vez que accede a una consulta. El registro solo se genera cuando crea la consulta original. El programa todavía tarda mucho tiempo en ejecutarse, pero ahora puede ver por qué. Si se le agota la paciencia al ejecutar el orden aleatorio externo con los registros activados, cambie de nuevo al orden aleatorio interno. Aún puede ver los efectos de la evaluación diferida. En una ejecución, ejecuta 2592 consultas, incluida toda la generación de palos y valores.

Hay una manera fácil de actualizar este programa para evitar todas esas ejecuciones. Existen los métodos LINQ `ToArray()` y `ToList()` que hacen que la consulta se ejecute y almacenan los resultados en una matriz o en una lista, respectivamente. Utilice estos métodos para almacenar en caché los resultados de una consulta, en lugar de volver a ejecutar la consulta de origen.  Anexe las consultas que generan las barajas con una llamada a `ToArray()` y vuelva a ejecutar la consulta:

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

Vuelva a realizar la ejecución, y el orden aleatorio interno baja a 30 consultas. Ejecute de nuevo con el orden aleatorio externo y verá mejoras similares. (Ahora ejecuta 162 consultas).

No interprete este ejemplo incorrectamente al pensar que todas las consultas deben ejecutarse de manera diligente. Este ejemplo está diseñado para resaltar los casos de uso en que la evaluación diferida puede generar dificultades de rendimiento. Eso se debe a que cada nueva disposición de la baraja de cartas se crea a partir de la disposición anterior. La evaluación diferida supone que cada nueva configuración de la baraja se realiza a partir de la baraja original, incluso con la ejecución del código que crea el elemento `startingDeck`. Esto conlleva una gran cantidad de trabajo adicional. 

En la práctica, algunos algoritmos se ejecutan mucho mejor con la evaluación diligente y otros, con la evaluación diferida. (En general, la evaluación diferida es una opción mucho más conveniente cuando el origen de datos es un proceso independiente, como un motor de base de datos. En esos casos, la evaluación diferida permite realizar consultas más complejas para ejecutarlas solo con un recorrido de ida y vuelta en el procesamiento de la base de datos). LINQ permite realizar la evaluación diferida y diligente. Piénselo y elija la mejor opción.

## <a name="preparing-for-new-features"></a>Preparación de las nuevas características

El código que ha escrito para este ejemplo es un ejemplo de creación de un prototipo sencillo que realiza el trabajo. Se trata de una manera excelente de explorar un espacio de problemas y, para muchas características, puede ser la mejor solución permanente. Ha aprovechado *tipos anónimos* para las cartas, y cada carta se representa mediante cadenas.

Los *tipos anónimos* ofrecen numerosas ventajas de productividad. No es necesario definir una clase para representar el almacenamiento. El compilador genera el tipo. El tipo generado por el compilador usa muchos de los procedimientos recomendados para objetos de datos sencillos. Es *inmutable*, lo que significa que no se pueden cambiar ninguna de sus propiedades después de que se haya construido. Los tipos anónimos son internos a un ensamblado, por lo que no se ven como parte de la API pública de ese ensamblado. Los tipos anónimos también contienen una invalidación del método `ToString()` que devuelve una cadena con formato con cada uno de los valores.

Los tipos anónimos también tienen desventajas. No tienen nombres accesibles, por lo que no puede utilizarlos como argumentos o valores devueltos. Observará que los métodos anteriores que usan estos tipos anónimos son métodos genéricos. La invalidación de `ToString()` puede no ser la opción más conveniente a medida que la aplicación incorpora más características. 

El ejemplo también utiliza cadenas para el palo y la clasificación de cada carta. Se trata de un ejemplo de amplio alcance. El sistema de tipos de C# facilita la escritura de un código mejor, aprovechando los tipos `enum` para esos valores.

Empieza con los palos. Este es el momento perfecto para usar `enum`:

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

El método `Suits()` también cambia el tipo y la implementación:

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

A continuación, realice los mismos cambios con la clasificación de las cartas:

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

Y el método que las genera:

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

Para terminar, se va a crear un tipo para representar la carta, en lugar de depender de un tipo anónimo. Los tipos anónimos son excelentes para tipos ligeros locales, pero, en este ejemplo, el juego de naipes es uno de los principales conceptos. Debe ser un tipo concreto.

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

Este tipo utiliza *propiedades autoimplementadas de solo lectura* que se establece en el constructor y, por tanto, no se puede modificar. También usa la nueva característica de [interpolación de cadena](../language-reference/tokens/interpolated.md) que simplifica la salida de la cadena de formato.

Actualice la consulta que genera la baraja original para usar el nuevo tipo:

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

Realice la compilación y vuelva a ejecutarla. La salida está un poco más limpia, y el código es algo más claro y puede extenderse con más facilidad.

## <a name="conclusion"></a>Conclusión

En este ejemplo se han mostrado algunos de los métodos usados en LINQ, como la forma de crear métodos propios que pueden usarse con facilidad con código habilitado para LINQ. También se presentan las diferencias entre la evaluación diligente y diferida, y el efecto que puede tener la decisión en el rendimiento.

Ha obtenido un poco de información sobre una técnica de magia. Los magos usan la mezcla faro porque les permite controlar dónde está cada carta en la baraja. En algunos trucos, el mago pide a un miembro de la audiencia que coloque una carta en la parte superior de la baraja, y la mezcla en orden aleatorio durante algunos minutos, pero puede controlar dónde se encuentra la carta en cuestión. En otras ilusiones, es necesario organizar la baraja de una forma determinada. Un mago debe organizar la baraja antes de realizar el truco. Después, mezclará la baraja en orden aleatorio 5 veces usando un orden aleatorio interno. En el escenario, el mago puede mostrar qué aspecto tiene una baraja aleatoria, ordenarla aleatoriamente 3 veces más y organizar la baraja exactamente como lo desea.
