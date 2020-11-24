---
title: Delegados y expresiones lambda
description: Obtenga información sobre cómo los delegados, que definen un tipo que especifica una firma de método determinada, se pueden llamar directamente o pasar a otro método y llamar.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 9be4fcdc29eac433dc7416578acbc664ac2e431c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821689"
---
# <a name="delegates-and-lambdas"></a>Delegados y expresiones lambda

Los delegados definen un tipo que especifica una firma de método concreta. Se puede asignar un método (estático o de instancia) que satisfaga esta firma a una variable de ese tipo y luego llamarlo directamente (con los argumentos adecuados) o pasarlo como argumento a otro método y después llamarlo. El siguiente ejemplo muestra el uso de delegados.

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* En la línea `public delegate string Reverse(string s);` se crea un tipo delegado de una firma determinada, en este caso un método que toma un parámetro de cadena y luego devuelve un parámetro de cadena.
* El método `static string ReverseString(string s)`, que tiene exactamente la misma firma que el tipo delegado definido, implementa el delegado.
* En la línea `Reverse rev = ReverseString;` se muestra que se puede asignar un método a una variable del tipo de delegado correspondiente.
* En la línea `Console.WriteLine(rev("a string"));` se muestra cómo se usa una variable de un tipo de delegado para invocar al delegado.

Para simplificar el proceso de desarrollo, .NET incluye un conjunto de tipos delegados que los programadores pueden volver a usar para no tener que crear nuevos tipos. Estos tipos son `Func<>`, `Action<>` y `Predicate<>`, y se pueden usar sin necesidad de definir nuevos tipos de delegado. Hay algunas diferencias entre los tres tipos que tienen que ver con la forma en que se van a usar:

* `Action<>` se usa cuando es necesario realizar una acción mediante los argumentos del delegado. El método que encapsula no devuelve ningún valor.
* `Func<>` se usa normalmente cuando se tiene una transformación a mano; es decir, cuando se necesita transformar los argumentos del delegado en un resultado diferente. Las proyecciones son un buen ejemplo. El método que encapsula devuelve un valor especificado.
* `Predicate<>` se usa cuando es necesario determinar si el argumento cumple la condición del delegado. También se puede escribir como `Func<T, bool>`, lo que significa que el método devuelve un valor booleano.

Ahora podemos tomar el ejemplo anterior y volver a escribirlo mediante el delegado `Func<>` en lugar de un tipo personalizado. El programa seguirá ejecutándose de la misma forma.

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

En este ejemplo sencillo, tener un método definido fuera del método `Main` parece un poco superfluo. .NET Framework 2.0 ha introducido el concepto de *delegados anónimos*, que permiten crear delegados "insertados" sin necesidad de especificar ningún otro tipo o método.

En el ejemplo siguiente, un delegado anónimo filtra una lista solo por los números pares y, después, los imprime en la consola.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

Como puede ver, el cuerpo del delegado es simplemente un conjunto de expresiones, como cualquier otro delegado. Pero en lugar de ser una definición independiente, se ha introducido _ad hoc_ en la llamada al método <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.

Pero incluso con este enfoque, sigue habiendo mucho código del que es posible deshacerse. Aquí es donde entran en juego las *expresiones lambda*. Las expresiones lambda, o las "lambda", para abreviar, se presentaron en C# 3.0 como uno de los bloques de compilación fundamentales de Language Integrated Query (LINQ). Constituyen una sintaxis más cómoda para el uso de delegados. Declaran una firma y un cuerpo de método, pero no tienen una identidad formal propia, a menos que se asignen a un delegado. A diferencia de los delegados, se pueden asignar directamente como lado izquierdo del registro de eventos, o bien en distintas cláusulas y métodos de LINQ.

Puesto que una expresión lambda es solo otra forma de especificar un delegado, debería ser posible volver a escribir el ejemplo anterior para usar una expresión lambda en lugar de un delegado anónimo.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

En el ejemplo anterior, la expresión lambda que se usa es `i => i % 2 == 0`. De nuevo, constituyen una sintaxis más cómoda para el uso de delegados. Lo que sucede en segundo plano es similar a lo que ocurre con el delegado anónimo.

De nuevo, las expresiones lambda son solo delegados, lo que significa que se pueden usar como controlador de eventos sin problemas, como se muestra en el siguiente fragmento de código.

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

En este contexto, el operador `+=` se usa para suscribirse a un [evento](../csharp/language-reference/keywords/event.md). Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="further-reading-and-resources"></a>Más información y recursos

* [Delegados](../csharp/programming-guide/delegates/index.md)
* [Funciones anónimas](../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [Expresiones lambda](../csharp/language-reference/operators/lambda-expressions.md)
