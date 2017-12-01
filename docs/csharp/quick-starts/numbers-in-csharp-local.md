---
title: "Guía de inicio rápido - números en C#, C#"
description: "Aprender C# examinando sus propiedades y métodos tipos numéricos."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a>Números de C# de inicio rápido #

Esta guía de inicio rápido explican los tipos numéricos en C# interactivamente. Deberá escribir pequeñas cantidades de código y vuelva a compilar y ejecutar ese código. El inicio rápido contiene una serie de lecciones que explorar números y las operaciones matemáticas en C#. En ellas se enseñan los aspectos básicos del lenguaje C#.

Este inicio rápido en el que se espera que debe disponer de una máquina que se puede usar para el desarrollo. El tema de .NET [empezar a trabajar en 10 minutos](https://www.microsoft.com/net/core) tiene instrucciones sobre cómo configurar el entorno de desarrollo local en Linux, Mac o PC.

## <a name="explore-integer-math"></a>Análisis de las operaciones matemáticas con enteros

Cree un directorio denominado **inicio rápido de números**. Conviértalo en el directorio actual y ejecute `dotnet new console -n NumbersInCSharp -o .`.

Abra **Program.cs** en su editor favorito y reemplace la línea `Console.Writeline("Hello World!");` con lo siguiente:

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

Ejecutar este código, escriba `dotnet run` en la ventana de comandos. 

Ya ha visto una de las operaciones matemáticas fundamentales con enteros. El tipo `int` representa un **entero**, que puede ser un número entero positivo o negativo. Use el símbolo `+` para la suma. Otros operadores matemáticos comunes con enteros son:

- `-` para resta
- `*` para multiplicación
- `/` para división

Comience por explorar esas operaciones diferentes. Agregue estas líneas después de la línea que escribe el valor de `c`:

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

Ejecutar este código, escriba `dotnet run` en la ventana de comandos. 
    
Si lo desea, también puede experimentar con la realización de varias operaciones matemáticas en la misma línea. Intente `c = a + b - 12 * 17;` por ejemplo. Se permite mezclar las variables y constantes números.

> [!TIP]
> Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código. El **compilador** buscará dichos errores y los notificará. Cuando la salida contiene mensajes de error, fíjese en el código de ejemplo y el código en la ventana para ver qué se debe corregir.
> Este ejercicio le ayudará a aprender la estructura del código de C#.     

Ha terminado el primer paso. Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente. Con este paso, resulta más fácil empezar con un nuevo ejemplo. Cambie el nombre del método `Main` por `WorkingWithIntegers` y escriba un método `Main` nuevo que llame a `WorkingWithIntegers`. Cuando termine, el código debe tener un aspecto similar al siguiente:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a>Análisis sobre el orden de las operaciones

Marcar como comentario la llamada a `WorkingWithIntegers()`. Realizará la salida que menos saturado mientras trabaja en esta sección:

```csharp
//WorkingWithIntegers();
```

El `//` inicia un **comentario** en C#. Los comentarios son cualquier texto que desea mantener en el código fuente, pero no se ejecutan como código. El compilador no genera ningún código ejecutable de comentarios.

El lenguaje C# define la prioridad de las diferentes operaciones matemáticas con reglas compatibles con las reglas aprendidas en las operaciones matemáticas.
La multiplicación y división tienen prioridad sobre la suma y resta.
Explorar que agregando el código siguiente a su `Main` método y execuing `dotnet run`:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

La salida muestra que la multiplicación se realiza antes que la suma.

Las operaciones que desee llevar a cabo en primer lugar o puede forzar un orden diferente de operación mediante la adición de paréntesis alrededor de la operación. Agregue las líneas siguientes y vuelva a ejecutar:

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

Combine muchas operaciones distintas para indagar más. Agregar algo parecido a las líneas siguientes en la parte inferior de la `Main` método. Intente `dotnet run` nuevo.

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

Puede que haya observado un comportamiento interesante de los enteros. División de enteros siempre genera un resultado entero, incluso cuando se podría esperar el resultado para incluir una parte decimal o fraccionaria.

Si aún no lo ha visto este comportamiento, pruebe el código siguiente al final de su `Main` método:

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

Tipo `dotnet run` nuevo para ver los resultados.

Antes de continuar, echemos todo el código que ha escrito en esta sección y colocarla en un nuevo método. Llame a ese nuevo método `OrderPrecedence`.
Debe acabar con algo parecido a esto:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {   
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a  + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a>Información sobre los límites y la precisión de los enteros
En el último ejemplo se ha mostrado que la división de enteros trunca el resultado.
Puede obtener el **resto** mediante el uso de la **módulo** (operador), el `%` caracteres. Pruebe el código siguiente en su `Main` método:

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

El tipo de entero de C# difiere de los enteros matemáticos en un aspecto: el tipo `int` tiene límites mínimo y máximo. Agregue este código a su `Main` método para ver esos límites:
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

Si un cálculo genera un valor que supera los límites, se producirá una condición de **subdesbordamiento** o **desbordamiento**. La respuesta parece ajustarse de un límite al otro. Agregue estas dos líneas para su `Main` método para ver un ejemplo:

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
Tenga en cuenta que la respuesta está muy próxima al entero mínimo (negativo). Es lo mismo que `min + 2`. La operación de suma **desbordó** los valores permitidos para los enteros.
La respuesta es un número negativo muy grande porque un desbordamiento "se ajusta" desde el valor de entero más alto posible al más bajo.

Hay otros tipos numéricos con distintos límites y precisiones que podría usar si el tipo `int` no satisface sus necesidades. Veámoslo a continuación.

Una vez más, vamos a mover el código que escribió en esta sección en un método independiente. Denomínelo `TestLimits`. 

## <a name="work-with-the-double-type"></a>Operaciones con el tipo double

El tipo numérico `double` representa números de punto flotante de doble precisión. Puede que no esté familiarizado con estos términos. A **punto flotante** número resulta útil para representar números no entero que pueden ser muy grandes o pequeños en magnitud. **Doble precisión** significa que estos números se almacenan con mayor precisión que en el caso de la **precisión sencilla**. En los equipos modernos, es más habitual utilizar números con doble precisión que con precisión sencilla.
Comencemos a explorar. Agregue el siguiente código y ver el resultado:

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

Tenga en cuenta que la respuesta incluye la parte decimal del cociente. Pruebe una expresión algo más complicada con tipos double:

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

El intervalo de un valor double es mucho más amplio que en el caso de los valores enteros. Pruebe el código siguiente debajo de lo que ha escrito hasta ahora:

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

Estos valores se imprimen en notación científica. El número a la izquierda de la `E` es la mantisa. El número a la derecha es el exponente, como una potencia de diez. 

Al igual que sucede con los números decimales en las operaciones matemáticas, los tipos double en C# pueden presentar errores de redondeo. Pruebe este código:

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

Sabe que repetir `0.3` no es exactamente lo mismo que `1/3`.

***Desafío***

Pruebe otros cálculos con números grandes, números pequeños, multiplicaciones y divisiones con el tipo `double`.  Intente realizar cálculos más complicados.

Una vez que ha invertido un tiempo con el desafío, tomar el código que ha escrito y lo coloca en un nuevo método. Nombre ese nuevo método `WorkWithDoubles`.

## <a name="work-with-fixed-point-types"></a>Operaciones con tipos de punto fijo

Hasta el momento ha visto los tipos numéricos básicos en C#: los tipos integer y double.  Sin embargo, hay otro tipo más que debe aprender: el tipo `decimal`. El `decimal` tipo tiene un intervalo más pequeño pero mayor precisión que `double`. El término **punto fijo** significa que el punto decimal o el punto binario no se mueven. Observemos lo siguiente:

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

Tenga en cuenta que el intervalo es más pequeño que con el tipo `double`. Puede observar una precisión mayor con el tipo decimal si prueba el siguiente código:

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

El sufijo `M` en los números es la forma de indicar que una constante debe usar el tipo `decimal`.

Observe que la expresión matemática con el tipo decimal tiene más dígitos a la derecha del punto decimal. 

***Desafío***

Ahora que ya conoce los diferentes tipos numéricos, escriba código para calcular el área de un círculo cuyo radio sea de 6,35 cm. Recuerde que el área de un circulo es igual al valor de su radio elevado al cuadrado multiplicado por Pi. Una sugerencia: C# contiene una constante de PI, <xref:System.Math.PI?displayProperty=nameWithType> que puede usar para ese valor. 

Puede comprobar la respuesta por [examinando el código de ejemplo terminado en GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)

Si lo desea, intente algunas otras fórmulas. 

Ha completado el inicio rápido "números en C#". Puede continuar con la [bifurcaciones y bucles](branches-and-loops-local.md) inicio rápido en su propio entorno de desarrollo.

Puede obtener más información sobre los números en C# en los temas siguientes:

[Tabla de tipos enteros](../language-reference/keywords/integral-types-table.md)   
[Tabla de tipos de punto flotante](../language-reference/keywords/floating-point-types-table.md)   
[Tabla de tipos integrados](../language-reference/keywords/built-in-types-table.md)   
[Tabla de conversiones numéricas implícitas](../language-reference/keywords/implicit-numeric-conversions-table.md)   
[Tabla de conversiones numéricas explícitas](../language-reference/keywords/explicit-numeric-conversions-table.md)

