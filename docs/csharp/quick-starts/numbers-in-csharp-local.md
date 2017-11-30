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
# <a name="numbers-in-c-quick-start"></a><span data-ttu-id="98eb4-103">Números de C# de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="98eb4-103">Numbers in C# quick start</span></span> #

<span data-ttu-id="98eb4-104">Esta guía de inicio rápido explican los tipos numéricos en C# interactivamente.</span><span class="sxs-lookup"><span data-stu-id="98eb4-104">This quick start teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="98eb4-105">Deberá escribir pequeñas cantidades de código y vuelva a compilar y ejecutar ese código.</span><span class="sxs-lookup"><span data-stu-id="98eb4-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="98eb4-106">El inicio rápido contiene una serie de lecciones que explorar números y las operaciones matemáticas en C#.</span><span class="sxs-lookup"><span data-stu-id="98eb4-106">The quick start contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="98eb4-107">En ellas se enseñan los aspectos básicos del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="98eb4-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="98eb4-108">Este inicio rápido en el que se espera que debe disponer de una máquina que se puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="98eb4-109">El tema de .NET [empezar a trabajar en 10 minutos](https://www.microsoft.com/net/core) tiene instrucciones sobre cómo configurar el entorno de desarrollo local en Linux, Mac o PC.</span><span class="sxs-lookup"><span data-stu-id="98eb4-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="98eb4-110">Análisis de las operaciones matemáticas con enteros</span><span class="sxs-lookup"><span data-stu-id="98eb4-110">Explore integer math</span></span>

<span data-ttu-id="98eb4-111">Cree un directorio denominado **inicio rápido de números**.</span><span class="sxs-lookup"><span data-stu-id="98eb4-111">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="98eb4-112">Conviértalo en el directorio actual y ejecute `dotnet new console -n NumbersInCSharp -o .`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-112">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="98eb4-113">Abra **Program.cs** en su editor favorito y reemplace la línea `Console.Writeline("Hello World!");` con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98eb4-113">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="98eb4-114">Ejecutar este código, escriba `dotnet run` en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="98eb4-114">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="98eb4-115">Ya ha visto una de las operaciones matemáticas fundamentales con enteros.</span><span class="sxs-lookup"><span data-stu-id="98eb4-115">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="98eb4-116">El tipo `int` representa un **entero**, que puede ser un número entero positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-116">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="98eb4-117">Use el símbolo `+` para la suma.</span><span class="sxs-lookup"><span data-stu-id="98eb4-117">You use the `+` symbol for addition.</span></span> <span data-ttu-id="98eb4-118">Otros operadores matemáticos comunes con enteros son:</span><span class="sxs-lookup"><span data-stu-id="98eb4-118">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="98eb4-119">`-` para resta</span><span class="sxs-lookup"><span data-stu-id="98eb4-119">`-` for subtraction</span></span>
- <span data-ttu-id="98eb4-120">`*` para multiplicación</span><span class="sxs-lookup"><span data-stu-id="98eb4-120">`*` for multiplication</span></span>
- <span data-ttu-id="98eb4-121">`/` para división</span><span class="sxs-lookup"><span data-stu-id="98eb4-121">`/` for division</span></span>

<span data-ttu-id="98eb4-122">Comience por explorar esas operaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="98eb4-122">Start by exploring those different operations.</span></span> <span data-ttu-id="98eb4-123">Agregue estas líneas después de la línea que escribe el valor de `c`:</span><span class="sxs-lookup"><span data-stu-id="98eb4-123">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="98eb4-124">Ejecutar este código, escriba `dotnet run` en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="98eb4-124">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="98eb4-125">Si lo desea, también puede experimentar con la realización de varias operaciones matemáticas en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="98eb4-125">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="98eb4-126">Intente `c = a + b - 12 * 17;` por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-126">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="98eb4-127">Se permite mezclar las variables y constantes números.</span><span class="sxs-lookup"><span data-stu-id="98eb4-127">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="98eb4-128">Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código.</span><span class="sxs-lookup"><span data-stu-id="98eb4-128">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="98eb4-129">El **compilador** buscará dichos errores y los notificará.</span><span class="sxs-lookup"><span data-stu-id="98eb4-129">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="98eb4-130">Cuando la salida contiene mensajes de error, fíjese en el código de ejemplo y el código en la ventana para ver qué se debe corregir.</span><span class="sxs-lookup"><span data-stu-id="98eb4-130">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="98eb4-131">Este ejercicio le ayudará a aprender la estructura del código de C#.</span><span class="sxs-lookup"><span data-stu-id="98eb4-131">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="98eb4-132">Ha terminado el primer paso.</span><span class="sxs-lookup"><span data-stu-id="98eb4-132">You've finished the first step.</span></span> <span data-ttu-id="98eb4-133">Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="98eb4-133">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="98eb4-134">Con este paso, resulta más fácil empezar con un nuevo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-134">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="98eb4-135">Cambie el nombre del método `Main` por `WorkingWithIntegers` y escriba un método `Main` nuevo que llame a `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-135">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="98eb4-136">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="98eb4-136">When you have finished, your code should look like this:</span></span>

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

## <a name="explore-order-of-operations"></a><span data-ttu-id="98eb4-137">Análisis sobre el orden de las operaciones</span><span class="sxs-lookup"><span data-stu-id="98eb4-137">Explore order of operations</span></span>

<span data-ttu-id="98eb4-138">Marcar como comentario la llamada a `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-138">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="98eb4-139">Realizará la salida que menos saturado mientras trabaja en esta sección:</span><span class="sxs-lookup"><span data-stu-id="98eb4-139">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="98eb4-140">El `//` inicia un **comentario** en C#.</span><span class="sxs-lookup"><span data-stu-id="98eb4-140">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="98eb4-141">Los comentarios son cualquier texto que desea mantener en el código fuente, pero no se ejecutan como código.</span><span class="sxs-lookup"><span data-stu-id="98eb4-141">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="98eb4-142">El compilador no genera ningún código ejecutable de comentarios.</span><span class="sxs-lookup"><span data-stu-id="98eb4-142">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="98eb4-143">El lenguaje C# define la prioridad de las diferentes operaciones matemáticas con reglas compatibles con las reglas aprendidas en las operaciones matemáticas.</span><span class="sxs-lookup"><span data-stu-id="98eb4-143">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="98eb4-144">La multiplicación y división tienen prioridad sobre la suma y resta.</span><span class="sxs-lookup"><span data-stu-id="98eb4-144">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="98eb4-145">Explorar que agregando el código siguiente a su `Main` método y execuing `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="98eb4-145">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="98eb4-146">La salida muestra que la multiplicación se realiza antes que la suma.</span><span class="sxs-lookup"><span data-stu-id="98eb4-146">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="98eb4-147">Las operaciones que desee llevar a cabo en primer lugar o puede forzar un orden diferente de operación mediante la adición de paréntesis alrededor de la operación.</span><span class="sxs-lookup"><span data-stu-id="98eb4-147">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="98eb4-148">Agregue las líneas siguientes y vuelva a ejecutar:</span><span class="sxs-lookup"><span data-stu-id="98eb4-148">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="98eb4-149">Combine muchas operaciones distintas para indagar más.</span><span class="sxs-lookup"><span data-stu-id="98eb4-149">Explore more by combining many different operations.</span></span> <span data-ttu-id="98eb4-150">Agregar algo parecido a las líneas siguientes en la parte inferior de la `Main` método.</span><span class="sxs-lookup"><span data-stu-id="98eb4-150">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="98eb4-151">Intente `dotnet run` nuevo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-151">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="98eb4-152">Puede que haya observado un comportamiento interesante de los enteros.</span><span class="sxs-lookup"><span data-stu-id="98eb4-152">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="98eb4-153">División de enteros siempre genera un resultado entero, incluso cuando se podría esperar el resultado para incluir una parte decimal o fraccionaria.</span><span class="sxs-lookup"><span data-stu-id="98eb4-153">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="98eb4-154">Si aún no lo ha visto este comportamiento, pruebe el código siguiente al final de su `Main` método:</span><span class="sxs-lookup"><span data-stu-id="98eb4-154">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="98eb4-155">Tipo `dotnet run` nuevo para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="98eb4-155">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="98eb4-156">Antes de continuar, echemos todo el código que ha escrito en esta sección y colocarla en un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="98eb4-156">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="98eb4-157">Llame a ese nuevo método `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-157">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="98eb4-158">Debe acabar con algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="98eb4-158">You should end up with something like this:</span></span>

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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="98eb4-159">Información sobre los límites y la precisión de los enteros</span><span class="sxs-lookup"><span data-stu-id="98eb4-159">Explore integer precision and limits</span></span>
<span data-ttu-id="98eb4-160">En el último ejemplo se ha mostrado que la división de enteros trunca el resultado.</span><span class="sxs-lookup"><span data-stu-id="98eb4-160">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="98eb4-161">Puede obtener el **resto** mediante el uso de la **módulo** (operador), el `%` caracteres.</span><span class="sxs-lookup"><span data-stu-id="98eb4-161">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="98eb4-162">Pruebe el código siguiente en su `Main` método:</span><span class="sxs-lookup"><span data-stu-id="98eb4-162">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="98eb4-163">El tipo de entero de C# difiere de los enteros matemáticos en un aspecto: el tipo `int` tiene límites mínimo y máximo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-163">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="98eb4-164">Agregue este código a su `Main` método para ver esos límites:</span><span class="sxs-lookup"><span data-stu-id="98eb4-164">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="98eb4-165">Si un cálculo genera un valor que supera los límites, se producirá una condición de **subdesbordamiento** o **desbordamiento**.</span><span class="sxs-lookup"><span data-stu-id="98eb4-165">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="98eb4-166">La respuesta parece ajustarse de un límite al otro.</span><span class="sxs-lookup"><span data-stu-id="98eb4-166">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="98eb4-167">Agregue estas dos líneas para su `Main` método para ver un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98eb4-167">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="98eb4-168">Tenga en cuenta que la respuesta está muy próxima al entero mínimo (negativo).</span><span class="sxs-lookup"><span data-stu-id="98eb4-168">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="98eb4-169">Es lo mismo que `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-169">It's the same as `min + 2`.</span></span> <span data-ttu-id="98eb4-170">La operación de suma **desbordó** los valores permitidos para los enteros.</span><span class="sxs-lookup"><span data-stu-id="98eb4-170">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="98eb4-171">La respuesta es un número negativo muy grande porque un desbordamiento "se ajusta" desde el valor de entero más alto posible al más bajo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-171">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="98eb4-172">Hay otros tipos numéricos con distintos límites y precisiones que podría usar si el tipo `int` no satisface sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="98eb4-172">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="98eb4-173">Veámoslo a continuación.</span><span class="sxs-lookup"><span data-stu-id="98eb4-173">Let's explore those next.</span></span>

<span data-ttu-id="98eb4-174">Una vez más, vamos a mover el código que escribió en esta sección en un método independiente.</span><span class="sxs-lookup"><span data-stu-id="98eb4-174">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="98eb4-175">Denomínelo `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-175">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="98eb4-176">Operaciones con el tipo double</span><span class="sxs-lookup"><span data-stu-id="98eb4-176">Work with the double type</span></span>

<span data-ttu-id="98eb4-177">El tipo numérico `double` representa números de punto flotante de doble precisión.</span><span class="sxs-lookup"><span data-stu-id="98eb4-177">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="98eb4-178">Puede que no esté familiarizado con estos términos.</span><span class="sxs-lookup"><span data-stu-id="98eb4-178">Those terms may be new to you.</span></span> <span data-ttu-id="98eb4-179">A **punto flotante** número resulta útil para representar números no entero que pueden ser muy grandes o pequeños en magnitud.</span><span class="sxs-lookup"><span data-stu-id="98eb4-179">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="98eb4-180">**Doble precisión** significa que estos números se almacenan con mayor precisión que en el caso de la **precisión sencilla**.</span><span class="sxs-lookup"><span data-stu-id="98eb4-180">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="98eb4-181">En los equipos modernos, es más habitual utilizar números con doble precisión que con precisión sencilla.</span><span class="sxs-lookup"><span data-stu-id="98eb4-181">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="98eb4-182">Comencemos a explorar.</span><span class="sxs-lookup"><span data-stu-id="98eb4-182">Let's explore.</span></span> <span data-ttu-id="98eb4-183">Agregue el siguiente código y ver el resultado:</span><span class="sxs-lookup"><span data-stu-id="98eb4-183">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="98eb4-184">Tenga en cuenta que la respuesta incluye la parte decimal del cociente.</span><span class="sxs-lookup"><span data-stu-id="98eb4-184">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="98eb4-185">Pruebe una expresión algo más complicada con tipos double:</span><span class="sxs-lookup"><span data-stu-id="98eb4-185">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="98eb4-186">El intervalo de un valor double es mucho más amplio que en el caso de los valores enteros.</span><span class="sxs-lookup"><span data-stu-id="98eb4-186">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="98eb4-187">Pruebe el código siguiente debajo de lo que ha escrito hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="98eb4-187">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="98eb4-188">Estos valores se imprimen en notación científica.</span><span class="sxs-lookup"><span data-stu-id="98eb4-188">These values are printed out in scientific notation.</span></span> <span data-ttu-id="98eb4-189">El número a la izquierda de la `E` es la mantisa.</span><span class="sxs-lookup"><span data-stu-id="98eb4-189">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="98eb4-190">El número a la derecha es el exponente, como una potencia de diez.</span><span class="sxs-lookup"><span data-stu-id="98eb4-190">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="98eb4-191">Al igual que sucede con los números decimales en las operaciones matemáticas, los tipos double en C# pueden presentar errores de redondeo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-191">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="98eb4-192">Pruebe este código:</span><span class="sxs-lookup"><span data-stu-id="98eb4-192">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="98eb4-193">Sabe que repetir `0.3` no es exactamente lo mismo que `1/3`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-193">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="98eb4-194">***Desafío***</span><span class="sxs-lookup"><span data-stu-id="98eb4-194">***Challenge***</span></span>

<span data-ttu-id="98eb4-195">Pruebe otros cálculos con números grandes, números pequeños, multiplicaciones y divisiones con el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-195">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="98eb4-196">Intente realizar cálculos más complicados.</span><span class="sxs-lookup"><span data-stu-id="98eb4-196">Try more complicated calculations.</span></span>

<span data-ttu-id="98eb4-197">Una vez que ha invertido un tiempo con el desafío, tomar el código que ha escrito y lo coloca en un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="98eb4-197">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="98eb4-198">Nombre ese nuevo método `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-198">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="98eb4-199">Operaciones con tipos de punto fijo</span><span class="sxs-lookup"><span data-stu-id="98eb4-199">Work with fixed point types</span></span>

<span data-ttu-id="98eb4-200">Hasta el momento ha visto los tipos numéricos básicos en C#: los tipos integer y double.</span><span class="sxs-lookup"><span data-stu-id="98eb4-200">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="98eb4-201">Sin embargo, hay otro tipo más que debe aprender: el tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-201">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="98eb4-202">El `decimal` tipo tiene un intervalo más pequeño pero mayor precisión que `double`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-202">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="98eb4-203">El término **punto fijo** significa que el punto decimal o el punto binario no se mueven.</span><span class="sxs-lookup"><span data-stu-id="98eb4-203">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="98eb4-204">Observemos lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98eb4-204">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="98eb4-205">Tenga en cuenta que el intervalo es más pequeño que con el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-205">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="98eb4-206">Puede observar una precisión mayor con el tipo decimal si prueba el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="98eb4-206">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="98eb4-207">El sufijo `M` en los números es la forma de indicar que una constante debe usar el tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="98eb4-207">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="98eb4-208">Observe que la expresión matemática con el tipo decimal tiene más dígitos a la derecha del punto decimal.</span><span class="sxs-lookup"><span data-stu-id="98eb4-208">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="98eb4-209">***Desafío***</span><span class="sxs-lookup"><span data-stu-id="98eb4-209">***Challenge***</span></span>

<span data-ttu-id="98eb4-210">Ahora que ya conoce los diferentes tipos numéricos, escriba código para calcular el área de un círculo cuyo radio sea de 6,35 cm.</span><span class="sxs-lookup"><span data-stu-id="98eb4-210">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 inches.</span></span> <span data-ttu-id="98eb4-211">Recuerde que el área de un circulo es igual al valor de su radio elevado al cuadrado multiplicado por Pi.</span><span class="sxs-lookup"><span data-stu-id="98eb4-211">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="98eb4-212">Una sugerencia: C# contiene una constante de PI, <xref:System.Math.PI?displayProperty=nameWithType> que puede usar para ese valor.</span><span class="sxs-lookup"><span data-stu-id="98eb4-212">One hint: C# contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="98eb4-213">Puede comprobar la respuesta por [examinando el código de ejemplo terminado en GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span><span class="sxs-lookup"><span data-stu-id="98eb4-213">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="98eb4-214">Si lo desea, intente algunas otras fórmulas.</span><span class="sxs-lookup"><span data-stu-id="98eb4-214">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="98eb4-215">Ha completado el inicio rápido "números en C#".</span><span class="sxs-lookup"><span data-stu-id="98eb4-215">You've completed the "Numbers in C#" quick start.</span></span> <span data-ttu-id="98eb4-216">Puede continuar con la [bifurcaciones y bucles](branches-and-loops-local.md) inicio rápido en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="98eb4-216">You can continue with the [Branches and loops](branches-and-loops-local.md) quick start in your own development environment.</span></span>

<span data-ttu-id="98eb4-217">Puede obtener más información sobre los números en C# en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="98eb4-217">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="98eb4-218">[Tabla de tipos enteros](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="98eb4-218">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="98eb4-219">[Tabla de tipos de punto flotante](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="98eb4-219">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="98eb4-220">[Tabla de tipos integrados](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="98eb4-220">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="98eb4-221">[Tabla de conversiones numéricas implícitas](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="98eb4-221">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="98eb4-222">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="98eb4-222">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

