---
title: "Inicio rápido - bifurcaciones y lops - Guía de C#"
description: "En este inicio rápido acerca de bifurcaciones y bucles, escribir código C# para explorar la sintaxis del lenguaje que admita bifurcaciones condicionales y bucles para ejecutar instrucciones de forma repetida."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a>Bifurcaciones y bucles

Este tutorial le enseña a escribir código que examina las variables y cambia la ruta de acceso de ejecución en función de esas variables. Escribir código C# y ver los resultados de compilación y ejecutarlo. El inicio rápido contiene una serie de lecciones que explorar bifurcación y construcciones de bucles en C#. En ellas se enseñan los aspectos básicos del lenguaje C#.

Este inicio rápido en el que se espera que debe disponer de una máquina que se puede usar para el desarrollo. El tema de .NET [empezar a trabajar en 10 minutos](https://www.microsoft.com/net/core) tiene instrucciones sobre cómo configurar el entorno de desarrollo local en Linux, Mac o PC.

## <a name="make-decisions-using-the-if-statement"></a>Tomar decisiones con la `if` instrucción

Cree un directorio denominado **inicio rápido de bifurcaciones**. Conviértalo en el directorio actual y ejecute `dotnet new console -n BranchesAndLoops -o .`. Este comando crea una nueva aplicación de consola .NET Core en el directorio actual. 

Abra **Program.cs** en su editor favorito y reemplace la línea `Console.Writeline("Hello World!");` con el código siguiente:

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

Pruebe este código escribiendo `dotnet run` en la ventana de la consola. Debería ver el mensaje "la respuesta es mayor que 10". imprime en la consola.

Modifique la declaración de `b` para que el resultado de la suma sea menor que diez: 

```csharp
int b = 3;
```

Tipo `dotnet run` nuevo. Como la respuesta es menor que diez, no se imprime nada. La **condición** que está probando es false. No tiene ningún código para ejecutar porque solo ha escrito una de las bifurcaciones posibles para una instrucción `if`: la bifurcación true.

> [!TIP]
> Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código. El compilador buscará y notificar los errores. Examine con atención el la salida de error y el código que ha generado el error. El error compler normalmente puede ayudarle a encontrar el problema. 

Este primer ejemplo muestra la eficacia de `if` y tipos booleanos. A *booleano* es una variable que puede tener uno de dos valores: `true` o `false`. C# define un tipo especial, `bool` para las variables booleanas. La instrucción `if` comprueba el valor de `bool`. Cuando el valor es `true`, se ejecuta la instrucción que sigue a `if`. De lo contrario, se omite. 

Este proceso de comprobación de condiciones y ejecución de instrucciones en función de esas condiciones es muy eficaz.


## <a name="make-if-and-else-work-together"></a>Operaciones conjuntas con if y else

Para ejecutar un código distinto en las bifurcaciones true y false, cree una bifurcación `else` para que se ejecute cuando la condición sea false. Pruebe esto. Agregue las dos últimas líneas en el código siguiente a su `Main` método (ya debe tener los primeros cuatro):

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

La instrucción que sigue a la palabra clave `else` se ejecuta solo si la condición de prueba es `false`. Combinar `if` y `else` con un valor booleano condiciones proporciona toda la potencia que necesita para administrar tanto un `true` y un `false` condición.

> [!IMPORTANT]
> La sangría debajo de las instrucciones `if` y `else` se utiliza para los lectores humanos.
> El lenguaje C# no considera significativos los espacios en blanco ni las sangrías. La instrucción que sigue a la palabra clave `if` o `else` se ejecutará en función de la condición. Todos los ejemplos de esta guía de inicio rápido siguen una práctica común para aplicar sangría a líneas basándose en el flujo de control de las instrucciones.

Dado que la sangría no es significativa, debe usar `{` y `}` para indicar si desea que más de una instrucción forme parte del bloque que se ejecuta de forma condicional. Los programadores de C# suelen usar esas llaves en todas las cláusulas `if` y `else`. En el ejemplo siguiente es el mismo que el que acaba de crear. Modifique el código anterior para que coincida con el código siguiente:

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> A través del resto de esta guía de inicio rápido, todas las muestras de código incluyen las llaves, siga aceptado prácticas.

Puede probar condiciones más complicadas. Agregue el código siguiente en su `Main` método después del código que haya escrito hasta ahora:

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

`&&` representa "y". Significa que ambas condiciones deben cumplirse para ejecutar la instrucción en la bifurcación true.  En estos ejemplos también se muestra que puede tener varias instrucciones en cada bifurcación condicional, siempre que las encierre entre `{` y `}`.

También puede usar `||` para representar "o". Agregue el código siguiente después de lo que ha escrito hasta ahora:

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

Ha terminado el primer paso. Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente. Con este paso, resulta más fácil empezar con un nuevo ejemplo. Cambie el nombre del método `Main` por `ExploreIf` y escriba un método `Main` nuevo que llame a `ExploreIf`. Cuando termine, el código debe tener un aspecto similar al siguiente:

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

Marcar como comentario la llamada a `ExploreIf()`. Realizará la salida que menos saturado mientras trabaja en esta sección:

```csharp
//ExploreIf();
```

El `//` inicia un **comentario** en C#. Los comentarios son cualquier texto que desea mantener en el código fuente, pero no se ejecutan como código. El compilador no genera ningún código ejecutable de comentarios.

## <a name="use-loops-to-repeat-operations"></a>Uso de bucles para repetir las operaciones

En esta sección usan **bucles** repetir las instrucciones. Pruebe este código en su `Main` método:

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

El `while` instrucción comprueba una condición y ejecuta la instrucción o bloque de instrucciones después de la `while`. Repetidamente comprueba la condición y ejecutar las instrucciones hasta que la condición es false.

En este ejemplo aparece otro operador nuevo. El código `++` que aparece después de la variable `counter` es el operador de **incremento**. Suma 1 al valor de `counter` y almacena ese valor en el `counter` variable.

> [!IMPORTANT]
> Asegúrese de que el `while` cambios de condición en false de bucle como para ejecutar el código. En caso contrario, se crea un **bucle infinito** donde nunca finaliza el programa. Que no está demostrada en este ejemplo, ya que tendrá que hacer que el programa para dejar de utilizar **CTRL-C** u otros medios.

El bucle `while` prueba la condición antes de ejecutar el código que sigue a `while`. El bucle `do` ... `while` primero ejecuta el código y después comprueba la condición. Al no mientras el bucle se muestra en el código siguiente:

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

Esto `do` bucle y las versiones anteriores `while` bucle generan el mismo resultado.

## <a name="work-with-the-for-loop"></a>Operaciones con el bucle for

El **para** bucle es más frecuente en C#. Pruebe este código en el método Main():

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

Funciona de la misma forma que los bucles `while` y `do` que ya ha usado. La instrucción `for` consta de tres partes que controlan su funcionamiento. 

La primera parte es el **inicializador de for**: `for index = 0;` declara que `index` es la variable de bucle y establece su valor inicial en `0`.

La parte central es la **condición de for**: `index < 10` declara que este bucle `for` debe continuar ejecutándose mientras que el valor del contador sea menor que diez.

La última parte es el **iterador de for**: `index++` especifica cómo modificar la variable de bucle después de ejecutar el bloque que sigue a la instrucción `for`. En este caso, especifica que `index` debe incrementarse en uno cada vez que el bloque se ejecuta.

Experimente con estas partes por su cuenta. Pruebe todos los pasos siguientes:

- Cambie el inicializador para que se inicie en un valor distinto.
- Cambie la condición para que se detenga en un valor diferente.

Cuando haya terminado, escriba algo de código para practicar con lo que ha aprendido.

## <a name="combine-branches-and-loops"></a>Combinar bifurcaciones y bucles

Ahora que ya ha obtenido la información sobre el bucle `if` y las construcciones de bucles con el lenguaje C#, trate de escribir código de C# para obtener la suma de todos los enteros de uno a veinte que se puedan dividir entre tres.  Tenga en cuenta las siguientes sugerencias:

- El operador `%` proporciona el resto de una operación de división.
- El `if` instrucción aporta la condición para ver si un número debe ser parte de la suma.
- El bucle `for` puede facilitar la repetición de una serie de pasos para todos los números comprendidos entre el uno y el veinte.

Pruébelo usted mismo. Después, revise cómo lo ha hecho. Puede ver una respuesta posible por [ver el código completo en GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).

Ha completado el inicio rápido "bifurcaciones y bucles".

Puede continuar con la [matrices y colecciones](arrays-and-collections.md) inicio rápido en su propio entorno de desarrollo.

Puede obtener más información sobre estos conceptos en los temas siguientes:

[Instrucciones If y else](../language-reference/keywords/if-else.md)   
[Instrucción while](../language-reference/keywords/while.md)   
[Instrucción do](../language-reference/keywords/do.md)   
[Instrucción for](../language-reference/keywords/for.md)   
