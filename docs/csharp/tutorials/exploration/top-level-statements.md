---
title: 'Instrucciones de nivel superior: tutorial de C#'
description: En este tutorial se muestra cómo puede usar instrucciones de nivel superior para experimentar y probar conceptos mientras explora ideas propias.
ms.date: 10/28/2020
ms.openlocfilehash: 210fbd83bf4677061cab303089d0b27f1a4a7d01
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189377"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a>Tutorial: Exploración de ideas mediante instrucciones de nivel superior para compilar código mientras aprende

En este tutorial, aprenderá a:

> [!div class="checklist"]
>
> - Obtener información sobre las reglas que rigen el uso de las instrucciones de nivel superior.
> - Usar instrucciones de nivel superior para explorar algoritmos.
> - Refactorizar exploraciones en componentes reutilizables.

## <a name="prerequisites"></a>Requisitos previos

Tendrá que configurar el equipo para ejecutar .NET 5, que incluye el compilador de C# 9. El compilador de C# 9 está disponible a partir de [Visual Studio 2019, versión 16.9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) o del [SDK de .NET 5.0](https://dot.net/get-dotnet5).

En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.

## <a name="start-exploring"></a>Comienzo de la exploración

Las instrucciones de nivel superior permiten evitar la ceremonia adicional que requiere colocar el punto de entrada del programa en un método estático en una clase. El punto de partida típico de una aplicación de consola nueva es similar al código siguiente:

```csharp
using System;

namespace Application
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

El código anterior es el resultado de ejecutar el comando `dotnet new console` y crear una aplicación de consola. Estas 11 líneas solo contienen una línea de código ejecutable. Puede simplificar ese programa con la nueva característica de instrucciones de nivel superior. Esto le permite quitar todas las líneas de este programa menos dos:

```csharp
using System;

Console.WriteLine("Hello World!");
```

Esta acción simplifica lo que se necesita para comenzar a explorar nuevas ideas. Puede usar las instrucciones de nivel superior para escenarios de scripting o para explorar. Una vez que conozca los aspectos básicos, puede empezar a refactorizar el código y crear métodos, clases u otros ensamblados para los componentes reutilizables que ha compilado. Las instrucciones de nivel superior permiten una experimentación rápida y tutoriales para principiantes. También proporcionan una ruta fluida desde la experimentación hasta la obtención de programas completos.

Las instrucciones de nivel superior se ejecutan en el orden en el que aparecen en el archivo. Las instrucciones de nivel superior solo se pueden usar en un archivo de código fuente de la aplicación. El compilador genera un error si se usan en más de un archivo.

## <a name="build-a-magic-net-answer-machine"></a>Creación de un contestador automático de .NET mágico

En este tutorial, se creará una aplicación de consola que responde a una pregunta de tipo "sí" o "no" con una respuesta aleatoria. Compilará la funcionalidad paso a paso. Puede centrarse en la tarea en lugar de la ceremonia necesaria para la estructura de un programa típico. Después, una vez que esté satisfecho con la funcionalidad, puede refactorizar la aplicación como considere oportuno.

Un buen punto de partida es escribir la pregunta de nuevo en la consola. Puede empezar por escribir el código siguiente:

```csharp
using System;

Console.WriteLine(args);
```

No declare una variable `args`. Para el único archivo de código fuente que contiene las instrucciones de nivel superior, el compilador reconoce `args` para indicar los argumentos de línea de comandos. El tipo de args es `string[]`, como en todos los programas de C#.

Puede ejecutar el comando `dotnet run` siguiente para probar el código:

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

Los argumentos después de `--` en la línea de comandos se pasan al programa. Puede ver el tipo de la variable `args`, ya que es lo que se imprime en la consola:

```console
System.String[]
```

Para escribir la pregunta en la consola, tendrá que enumerar los argumentos y separarlos con un espacio. Reemplace la llamada a `WriteLine` por el código siguiente:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="EchoInput":::

Ahora, al ejecutar el programa, mostrará correctamente la pregunta como una cadena de argumentos.

## <a name="respond-with-a-random-answer"></a>Respuesta con una respuesta aleatoria

Después de repetir la pregunta, puede agregar el código para generar la respuesta aleatoria. Para empezar, agregue una matriz de respuestas posibles:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="Answers":::

Esta matriz tiene 12 respuestas que son afirmativas, 6 inexpresivas y 6 negativas. A continuación, agregue el código siguiente para generar y mostrar una respuesta aleatoria de la matriz:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="GenerateAnswer":::

Puede volver a ejecutar la aplicación para ver los resultados. Debería ver algo parecido a la salida siguiente:

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

Este código responde a las preguntas, pero agreguemos una característica más. Quiere que la aplicación de preguntas simule que se piensa la respuesta. Puede hacerlo si agrega una animación de ASCII y se detiene mientras trabaja.  Agregue el código siguiente después de la línea que reproduce la pregunta:

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

También tendrá que agregar una instrucción `using` a la parte superior del archivo de código fuente:

```csharp
using System.Threading.Tasks;
```

Las instrucciones `using` deben aparecer antes que cualquier otra del archivo. De lo contrario, es un error del compilador. Puede volver a ejecutar el programa y ver la animación. Eso mejora la experiencia. Experimente con la duración del retraso hasta que le guste.

El código anterior crea un conjunto de líneas giratorias separadas por un espacio. Al agregar la palabra clave `await` se le indica al compilador que genere el punto de entrada del programa como un método con el modificador `async` y que devuelva <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>. Este programa no devuelve un valor, por lo que el punto de entrada del programa devuelve `Task`. Si el programa devuelve un valor entero, tendría que agregar una instrucción return al final de las instrucciones de nivel superior. Esa instrucción return especificaría el valor entero que se va a devolver. Si las instrucciones de nivel superior incluyen una expresión `await`, el tipo de valor devuelto se convierte en <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>.

## <a name="refactoring-for-the-future"></a>Refactorización para el futuro

El programa debería ser similar al código siguiente:

```csharp
using System;
using System.Threading.Tasks;

Console.WriteLine();
foreach(var s in args)
{
    Console.Write(s);
    Console.Write(' ');
}
Console.WriteLine();

for (int i = 0; i < 20; i++)
{
    Console.Write("| -");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("/ \\");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("- |");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("\\ /");
    await Task.Delay(50);
    Console.Write("\b\b\b");
}
Console.WriteLine();

string[] answers =
{
    "It is certain.",       "Reply hazy, try again.",     "Don’t count on it.",
    "It is decidedly so.",  "Ask again later.",           "My reply is no.",
    "Without a doubt.",     "Better not tell you now.",   "My sources say no.",
    "Yes – definitely.",    "Cannot predict now.",        "Outlook not so good.",
    "You may rely on it.",  "Concentrate and ask again.", "Very doubtful.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs point to yes.",
};

var index = new Random().Next(answers.Length - 1);
Console.WriteLine(answers[index]);
```

En el código anterior es razonable. Funciona. Pero no es reutilizable. Ahora que ya tiene la aplicación en funcionamiento, es momento de extraer los elementos reutilizables.

Un candidato es el código que muestra la animación en espera. Ese fragmento de código se puede convertir en un método:

Puede empezar por crear una función local en el archivo. Reemplace la animación actual por el código siguiente:

```csharp
await ShowConsoleAnimation();

static async Task ShowConsoleAnimation()
{
    for (int i = 0; i < 20; i++)
    {
        Console.Write("| -");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("/ \\");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("- |");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("\\ /");
        await Task.Delay(50);
        Console.Write("\b\b\b");
    }
    Console.WriteLine();
}
```

En el código anterior se crea una función local dentro del método Main. Todavía no es reutilizable. Por tanto, extraiga ese código en una clase. Cree un archivo con el nombre *utilities.cs* y agregue el código siguiente:

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

Las instrucciones de nivel superior solo pueden estar en un archivo y ese archivo no puede contener espacios de nombres ni tipos.

Por último, puede limpiar el código de animación para quitar duplicaciones:

:::code language="csharp" source="snippets/top-level-statements/Utiliities.cs" ID="Animation":::

Ahora tiene una aplicación completa y ha refactorizado los elementos reutilizables para su uso posterior.

## <a name="summary"></a>Resumen

Las instrucciones de nivel superior facilitan la creación de programas sencillos para explorar nuevos algoritmos. Puede experimentar con algoritmos si prueba otros fragmentos de código. Una vez que haya aprendido lo que funciona, puede refactorizar el código para que sea más fácil de mantener.

Las instrucciones de nivel superior simplifican los programas basados en aplicaciones de consola. Esto incluye Azure Functions, las acciones de GitHub y otras utilidades pequeñas.
