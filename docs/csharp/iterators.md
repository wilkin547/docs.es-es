---
title: Iterators
description: Obtenga información sobre cómo usar iteradores de C# integrados y cómo crear sus propios métodos de iterador personalizados.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 5cf36f45-f91a-4fca-a0b7-87f233e108e9
ms.openlocfilehash: ee72331cb85ba1a03d48e2f58526ad432c7fe6d4
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656103"
---
# <a name="iterators"></a>Iterators

Prácticamente todos los programas que escriba tendrán alguna necesidad de recorrer en iteración una colección. Va a escribir código que examine cada elemento de una colección.

También va a crear métodos de iterador, que son los métodos que genera un iterador (un objeto que atraviesa un contenedor, especialmente listas) para los elementos de esa clase. Se pueden usar para:

+ Realizar una acción en cada elemento de una colección.
+ Enumerar una colección personalizada.
+ Extender [LINQ](linq/index.md) u otras bibliotecas.
+ Crear una canalización de datos en la que los datos fluyan de forma eficaz mediante métodos de iterador.

El lenguaje C# proporciona características para ambos escenarios. Este artículo proporciona información general sobre esas características.

Este tutorial consta de varios pasos. Después de cada paso, puede ejecutar la aplicación y ver el progreso. También puede [ver o descargar el ejemplo completo](https://github.com/dotnet/samples/blob/master/csharp/iterators) para este tema. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../samples-and-tutorials/index.md#view-and-download-samples).

## <a name="iterating-with-foreach"></a>Iteración con foreach

Enumerar una colección es sencillo: la palabra clave `foreach` enumera una colección, ejecutando la instrucción incrustada una vez para cada elemento de la colección:

```csharp
foreach (var item in collection)
{
   Console.WriteLine(item.ToString());
}
```

Así de simple. Para recorrer en iteración todo el contenido de una colección, la instrucción `foreach` es todo lo que necesita. Pero la instrucción `foreach` no es mágica. Depende de dos interfaces genéricas definidas en la biblioteca de .NET Core para generar el código necesario para recorrer en iteración una colección: `IEnumerable<T>` e `IEnumerator<T>`. Este mecanismo se explica con más detalle a continuación.

Ambas interfaces tienen también homólogas no genéricas: `IEnumerable` e `IEnumerator`. Para el código moderno se prefieren las versiones [genéricas](programming-guide/generics/index.md).

## <a name="enumeration-sources-with-iterator-methods"></a>Orígenes de enumeración con métodos de iterador

Otra magnífica característica del lenguaje C# permite generar métodos que crean un origen para una enumeración. Se conocen como *métodos de iterador*. Un método de iterador define cómo generar los objetos de una secuencia cuando se solicita. Para definir un método de iterador se usan las palabras clave contextuales `yield return`.

Podría escribir este método para generar la secuencia de enteros de 0 a 9:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    yield return 0;
    yield return 1;
    yield return 2;
    yield return 3;
    yield return 4;
    yield return 5;
    yield return 6;
    yield return 7;
    yield return 8;
    yield return 9;
}
```

El código anterior muestra instrucciones distintivas `yield return` para resaltar el hecho de que se pueden usar varias instrucciones discretas `yield return` en un método de iterador.
Puede usar (y hágalo a menudo) otras construcciones de lenguaje para simplificar el código de un método de iterador. La definición del método siguiente genera la misma secuencia de números:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;
}
```

No tiene que elegir entre una y otra. Puede tener tantas instrucciones `yield return` como sea necesario para satisfacer las necesidades del método:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    index = 100;
    while (index < 110)
        yield return index++;
}
```

Esa es la sintaxis básica. Veamos un ejemplo del mundo real en el que se escribe un método de iterador. Imagine que se encuentra en un proyecto de IoT y los sensores del dispositivo generan un flujo de datos muy grande. Para hacerse una idea de los datos, podría escribir un método que tomara muestras de cada enésimo elemento de datos. Este pequeño método de iterador lo hace:

```csharp
public static IEnumerable<T> Sample(this IEnumerable<T> sourceSequence, int interval)
{
    int index = 0;
    foreach (T item in sourceSequence)
    {
        if (index++ % interval == 0)
            yield return item;
    }
}
```

Hay una restricción importante en los métodos de iterador: no puede tener una instrucción `return` y una instrucción `yield return` en el mismo método. Lo siguiente no se compilará:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    // generates a compile time error:
    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    return items;
}
```

Normalmente esta restricción no supone un problema. Tiene la opción de usar `yield return` en todo el método o de separar el método original en varios métodos, unos con `return` y otros con `yield return`.

Puede modificar el último método ligeramente para usar `yield return` en todas partes:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    foreach (var item in items)
        yield return item;
}
```

A veces, la respuesta correcta es dividir un método de iterador en dos métodos distintos. Uno que use `return` y un segundo que use `yield return`. Imagine una situación en la que quiera devolver una colección vacía, o los 5 primeros números impares, basándose en un argumento booleano. Eso se podría escribir como estos dos métodos:

```csharp
public IEnumerable<int> GetSingleDigitOddNumbers(bool getCollection)
{
    if (getCollection == false)
        return new int[0];
    else
        return IteratorMethod();
}

private IEnumerable<int> IteratorMethod()
{
    int index = 0;
    while (index < 10)
    {
        if (index % 2 == 1)
            yield return index;
        index++;
    }
}
```

Observe los métodos anteriores. El primero usa la instrucción estándar `return` para devolver una colección vacía o el iterador creado por el segundo método. El segundo método usa la instrucción `yield return` para crear la secuencia solicitada.

## <a name="deeper-dive-into-foreach"></a>Profundización en `foreach`

La instrucción `foreach` se expande en un elemento estándar que usa las interfaces `IEnumerable<T>` e `IEnumerator<T>` para recorrer en iteración todos los elementos de una colección. También minimiza los errores cometidos por los desarrolladores al no administrar correctamente los recursos.

El compilador traduce el bucle `foreach` que se muestra en el primer ejemplo en algo similar a esta construcción:

```csharp
IEnumerator<int> enumerator = collection.GetEnumerator();
while (enumerator.MoveNext())
{
    var item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

La construcción anterior representa el código generado por el compilador de C# a partir de la versión 5 y superiores. Antes de la versión 5, la variable `item` tenía un ámbito diferente:

```csharp
// C# versions 1 through 4:
IEnumerator<int> enumerator = collection.GetEnumerator();
int item = default(int);
while (enumerator.MoveNext())
{
    item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

Se modificó porque el comportamiento anterior podía provocar errores leves y difíciles de diagnosticar en las expresiones lambda. Para más información sobre las expresiones lambda, consulte [Expresiones lambda](language-reference/operators/lambda-expressions.md).

El código exacto generado por el compilador es algo más complicado y controla las situaciones en las que el objeto devuelto por `GetEnumerator()` implementa la interfaz `IDisposable`. La expansión completa genera código más parecido al siguiente:

```csharp
{
    var enumerator = collection.GetEnumerator();
    try
    {
        while (enumerator.MoveNext())
        {
            var item = enumerator.Current;
            Console.WriteLine(item.ToString());
        }
    } finally
    {
        // dispose of enumerator.
    }
}
```

La manera en que el enumerador se elimina depende de las características del tipo de `enumerator`. En el caso general, la cláusula `finally` se expande en:

```csharp
finally
{
   (enumerator as IDisposable)?.Dispose();
}
```

Pero si el tipo de `enumerator` es un tipo sellado y no hay conversión implícita del tipo de `enumerator` a `IDisposable`, la cláusula `finally` se expande en un bloque vacío:

```csharp
finally
{
}
```

Si hay una conversión implícita del tipo de `enumerator` a `IDisposable`, y `enumerator` es un tipo de valor que no acepta valores Null, la cláusula `finally` se expande en:

```csharp
finally
{
   ((IDisposable)enumerator).Dispose();
}
```

Afortunadamente, no es necesario recordar todos estos detalles. La instrucción `foreach` controla todos esos matices. El compilador generará el código correcto para cualquiera de estas construcciones.
