---
title: 'Números en C#: tutorial de introducción a C#'
description: Aprenda sobre C# mediante la exploración de tipos numéricos, sus usos, propiedades y métodos.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 3dc2a5afc6321da45351525a632f586cb84bf7fe
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794617"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="53ca0-103">Manipular números enteros y de punto flotante en C\#</span><span class="sxs-lookup"><span data-stu-id="53ca0-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="53ca0-104">En este tutorial se explican los tipos numéricos en C# de manera interactiva.</span><span class="sxs-lookup"><span data-stu-id="53ca0-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="53ca0-105">Escribirá pequeñas cantidades de código y luego compilará y ejecutará ese código.</span><span class="sxs-lookup"><span data-stu-id="53ca0-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="53ca0-106">El tutorial contiene una serie de lecciones que ofrecen información detallada sobre los números y las operaciones matemáticas en C#.</span><span class="sxs-lookup"><span data-stu-id="53ca0-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="53ca0-107">En ellas se enseñan los aspectos básicos del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="53ca0-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="53ca0-108">En este tutorial se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="53ca0-109">El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="53ca0-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="53ca0-110">En [Become familiar with the development tools](local-environment.md) (Familiarizarse con las herramientas de desarrollo) puede obtener información general sobre los comandos que usará, donde hay vínculos que amplían la información.</span><span class="sxs-lookup"><span data-stu-id="53ca0-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="53ca0-111">Análisis de las operaciones matemáticas con enteros</span><span class="sxs-lookup"><span data-stu-id="53ca0-111">Explore integer math</span></span>

<span data-ttu-id="53ca0-112">Cree un directorio denominado *numbers-quickstart*.</span><span class="sxs-lookup"><span data-stu-id="53ca0-112">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="53ca0-113">Conviértalo en el directorio actual y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="53ca0-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="53ca0-114">Abra *Program.cs* en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ca0-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="53ca0-115">Ejecute este código escribiendo `dotnet run` en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="53ca0-115">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="53ca0-116">Ha visto una de las operaciones matemáticas fundamentales con enteros.</span><span class="sxs-lookup"><span data-stu-id="53ca0-116">You've seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="53ca0-117">El tipo `int` representa un **entero**, que puede ser cero o un número entero positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-117">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="53ca0-118">Use el símbolo `+` para la suma.</span><span class="sxs-lookup"><span data-stu-id="53ca0-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="53ca0-119">Otros operadores matemáticos comunes con enteros son:</span><span class="sxs-lookup"><span data-stu-id="53ca0-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="53ca0-120">`-` para resta</span><span class="sxs-lookup"><span data-stu-id="53ca0-120">`-` for subtraction</span></span>
- <span data-ttu-id="53ca0-121">`*` para multiplicación</span><span class="sxs-lookup"><span data-stu-id="53ca0-121">`*` for multiplication</span></span>
- <span data-ttu-id="53ca0-122">`/` para división</span><span class="sxs-lookup"><span data-stu-id="53ca0-122">`/` for division</span></span>

<span data-ttu-id="53ca0-123">Comience por explorar esas operaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="53ca0-123">Start by exploring those different operations.</span></span> <span data-ttu-id="53ca0-124">Agregue estas líneas después de la línea que escribe el valor de `c`:</span><span class="sxs-lookup"><span data-stu-id="53ca0-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="53ca0-125">Ejecute este código escribiendo `dotnet run` en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="53ca0-125">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="53ca0-126">Si quiere, también puede probar a escribir varias operaciones matemáticas en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="53ca0-126">You can also experiment by writing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="53ca0-127">Pruebe `c = a + b - 12 * 17;` por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="53ca0-128">Se permite la combinación de variables y números constantes.</span><span class="sxs-lookup"><span data-stu-id="53ca0-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="53ca0-129">Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código.</span><span class="sxs-lookup"><span data-stu-id="53ca0-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="53ca0-130">El **compilador** buscará dichos errores y los notificará.</span><span class="sxs-lookup"><span data-stu-id="53ca0-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="53ca0-131">Si la salida contiene mensajes de error, revise detenidamente el código de ejemplo y el código de la ventana para saber qué debe corregir.</span><span class="sxs-lookup"><span data-stu-id="53ca0-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="53ca0-132">Este ejercicio le ayudará a aprender la estructura del código de C#.</span><span class="sxs-lookup"><span data-stu-id="53ca0-132">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="53ca0-133">Ha terminado el primer paso.</span><span class="sxs-lookup"><span data-stu-id="53ca0-133">You've finished the first step.</span></span> <span data-ttu-id="53ca0-134">Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="53ca0-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="53ca0-135">Con este paso, resulta más fácil empezar con un nuevo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="53ca0-136">Cambie el nombre del método `Main` por `WorkingWithIntegers` y escriba un método `Main` nuevo que llame a `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="53ca0-137">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ca0-137">When you finish, your code should look like this:</span></span>

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

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
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

## <a name="explore-order-of-operations"></a><span data-ttu-id="53ca0-138">Análisis sobre el orden de las operaciones</span><span class="sxs-lookup"><span data-stu-id="53ca0-138">Explore order of operations</span></span>

<span data-ttu-id="53ca0-139">Convierta en comentario la llamada a `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="53ca0-140">De este modo la salida estará menos saturada a medida que trabaje en esta sección:</span><span class="sxs-lookup"><span data-stu-id="53ca0-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="53ca0-141">El `//` inicia un **comentario** en C#.</span><span class="sxs-lookup"><span data-stu-id="53ca0-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="53ca0-142">Los comentarios son cualquier texto que desea mantener en el código fuente pero que no se ejecuta como código.</span><span class="sxs-lookup"><span data-stu-id="53ca0-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="53ca0-143">El compilador no genera ningún código ejecutable a partir de comentarios.</span><span class="sxs-lookup"><span data-stu-id="53ca0-143">The compiler doesn't generate any executable code from comments.</span></span>

<span data-ttu-id="53ca0-144">El lenguaje C# define la prioridad de las diferentes operaciones matemáticas con reglas compatibles con las reglas aprendidas en las operaciones matemáticas.</span><span class="sxs-lookup"><span data-stu-id="53ca0-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="53ca0-145">La multiplicación y división tienen prioridad sobre la suma y resta.</span><span class="sxs-lookup"><span data-stu-id="53ca0-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="53ca0-146">Explórelo mediante la adición del código siguiente a su método `Main` y la ejecución de `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="53ca0-146">Explore that by adding the following code to your `Main` method, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="53ca0-147">La salida muestra que la multiplicación se realiza antes que la suma.</span><span class="sxs-lookup"><span data-stu-id="53ca0-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="53ca0-148">Puede forzar la ejecución de un orden diferente de las operaciones si la operación o las operaciones que realizó primero se incluyen entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="53ca0-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="53ca0-149">Agregue las líneas siguientes y ejecute de nuevo:</span><span class="sxs-lookup"><span data-stu-id="53ca0-149">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="53ca0-150">Combine muchas operaciones distintas para indagar más.</span><span class="sxs-lookup"><span data-stu-id="53ca0-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="53ca0-151">Agregue algo parecido a las líneas siguientes en la parte inferior del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="53ca0-152">Pruebe `dotnet run` de nuevo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="53ca0-153">Puede que haya observado un comportamiento interesante de los enteros.</span><span class="sxs-lookup"><span data-stu-id="53ca0-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="53ca0-154">La división de enteros siempre genera un entero como resultado, incluso cuando se espera que el resultado incluya un decimal o una parte de una fracción.</span><span class="sxs-lookup"><span data-stu-id="53ca0-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="53ca0-155">Si no ha observado este comportamiento, pruebe el código siguiente al final de su método `Main`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="53ca0-156">Escriba `dotnet run` de nuevo para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="53ca0-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="53ca0-157">Antes de continuar, vamos a tomar todo el código que ha escrito en esta sección y a colocarlo en un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="53ca0-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="53ca0-158">Llame a ese nuevo método `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="53ca0-159">Debe escribir algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="53ca0-159">You should write something like this:</span></span>

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

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
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

            d = (a + b) * c;
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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="53ca0-160">Información sobre los límites y la precisión de los enteros</span><span class="sxs-lookup"><span data-stu-id="53ca0-160">Explore integer precision and limits</span></span>

<span data-ttu-id="53ca0-161">En el último ejemplo se ha mostrado que la división de enteros trunca el resultado.</span><span class="sxs-lookup"><span data-stu-id="53ca0-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="53ca0-162">Puede obtener el **resto** con el operador de **módulo**, el carácter `%`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="53ca0-163">Pruebe el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="53ca0-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="53ca0-164">El tipo de entero de C# difiere de los enteros matemáticos en un aspecto: el tipo `int` tiene límites mínimo y máximo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="53ca0-165">Agregue este código a su método `Main` para ver esos límites:</span><span class="sxs-lookup"><span data-stu-id="53ca0-165">Add this code to your `Main` method to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="53ca0-166">Si un cálculo genera un valor que supera los límites, se producirá una condición de **subdesbordamiento** o **desbordamiento**.</span><span class="sxs-lookup"><span data-stu-id="53ca0-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="53ca0-167">La respuesta parece ajustarse de un límite al otro.</span><span class="sxs-lookup"><span data-stu-id="53ca0-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="53ca0-168">Agregue estas dos líneas a su método `Main` para ver un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="53ca0-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="53ca0-169">Tenga en cuenta que la respuesta está muy próxima al entero mínimo (negativo).</span><span class="sxs-lookup"><span data-stu-id="53ca0-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="53ca0-170">Es lo mismo que `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-170">It's the same as `min + 2`.</span></span>
<span data-ttu-id="53ca0-171">La operación de suma **desbordó** los valores permitidos para los enteros.</span><span class="sxs-lookup"><span data-stu-id="53ca0-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="53ca0-172">La respuesta es un número negativo muy grande porque un desbordamiento "se ajusta" desde el valor de entero más alto posible al más bajo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="53ca0-173">Hay otros tipos numéricos con distintos límites y precisiones que podría usar si el tipo `int` no satisface sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="53ca0-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="53ca0-174">Vamos a explorar ahora esos otros tipos.</span><span class="sxs-lookup"><span data-stu-id="53ca0-174">Let's explore those other types next.</span></span>

<span data-ttu-id="53ca0-175">Una vez más, vamos a mover el código que escribió en esta sección a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="53ca0-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="53ca0-176">Denomínelo `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-176">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="53ca0-177">Operaciones con el tipo double</span><span class="sxs-lookup"><span data-stu-id="53ca0-177">Work with the double type</span></span>

<span data-ttu-id="53ca0-178">El tipo numérico `double` representa números de punto flotante de doble precisión.</span><span class="sxs-lookup"><span data-stu-id="53ca0-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="53ca0-179">Puede que no esté familiarizado con estos términos.</span><span class="sxs-lookup"><span data-stu-id="53ca0-179">Those terms may be new to you.</span></span> <span data-ttu-id="53ca0-180">Un número de **punto flotante** resulta útil para representar números no enteros cuya magnitud puede ser muy grande o pequeña.</span><span class="sxs-lookup"><span data-stu-id="53ca0-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="53ca0-181">La **precisión doble** es un término relativo que describe el número de dígitos binarios que se usan para almacenar el valor.</span><span class="sxs-lookup"><span data-stu-id="53ca0-181">**Double-precision** is a relative term that describes the number of binary digits used to store the value.</span></span> <span data-ttu-id="53ca0-182">Los números de **precisión doble** tienen el doble del número de dígitos binarios que la **precisión sencilla**.</span><span class="sxs-lookup"><span data-stu-id="53ca0-182">**Double precision** numbers have twice the number of binary digits as **single-precision**.</span></span> <span data-ttu-id="53ca0-183">En los equipos modernos, es más habitual usar números con precisión doble que con precisión sencilla.</span><span class="sxs-lookup"><span data-stu-id="53ca0-183">On modern computers, it's more common to use double precision than single precision numbers.</span></span> <span data-ttu-id="53ca0-184">Los números de **precisión sencilla** se declaran mediante la palabra clave `float`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-184">**Single precision** numbers are declared using the `float` keyword.</span></span>
<span data-ttu-id="53ca0-185">Comencemos a explorar.</span><span class="sxs-lookup"><span data-stu-id="53ca0-185">Let's explore.</span></span> <span data-ttu-id="53ca0-186">Agregue el siguiente código y observe el resultado:</span><span class="sxs-lookup"><span data-stu-id="53ca0-186">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="53ca0-187">Tenga en cuenta que la respuesta incluye la parte decimal del cociente.</span><span class="sxs-lookup"><span data-stu-id="53ca0-187">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="53ca0-188">Pruebe una expresión algo más complicada con tipos double:</span><span class="sxs-lookup"><span data-stu-id="53ca0-188">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="53ca0-189">El intervalo de un valor double es mucho más amplio que en el caso de los valores enteros.</span><span class="sxs-lookup"><span data-stu-id="53ca0-189">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="53ca0-190">Pruebe el código siguiente debajo del que ha escrito hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="53ca0-190">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="53ca0-191">Estos valores se imprimen en notación científica.</span><span class="sxs-lookup"><span data-stu-id="53ca0-191">These values are printed out in scientific notation.</span></span> <span data-ttu-id="53ca0-192">El número a la izquierda de `E` es la mantisa.</span><span class="sxs-lookup"><span data-stu-id="53ca0-192">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="53ca0-193">El número a la derecha es el exponente, como una potencia de diez.</span><span class="sxs-lookup"><span data-stu-id="53ca0-193">The number to the right is the exponent, as a power of 10.</span></span>

<span data-ttu-id="53ca0-194">Al igual que sucede con los números decimales en las operaciones matemáticas, los tipos double en C# pueden presentar errores de redondeo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-194">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="53ca0-195">Pruebe este código:</span><span class="sxs-lookup"><span data-stu-id="53ca0-195">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="53ca0-196">Sabe que repetir `0.3` no es exactamente lo mismo que `1/3`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-196">You know that `0.3` repeating isn't exactly the same as `1/3`.</span></span>

<span data-ttu-id="53ca0-197">***Desafío***</span><span class="sxs-lookup"><span data-stu-id="53ca0-197">***Challenge***</span></span>

<span data-ttu-id="53ca0-198">Pruebe otros cálculos con números grandes, números pequeños, multiplicaciones y divisiones con el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-198">Try other calculations with large numbers, small numbers, multiplication, and division using the `double` type.</span></span> <span data-ttu-id="53ca0-199">Intente realizar cálculos más complicados.</span><span class="sxs-lookup"><span data-stu-id="53ca0-199">Try more complicated calculations.</span></span>

<span data-ttu-id="53ca0-200">Una vez que haya invertido un tiempo en ello, tome el código que ha escrito y colóquelo en un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="53ca0-200">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="53ca0-201">Ponga a ese nuevo método el nombre `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-201">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-decimal-types"></a><span data-ttu-id="53ca0-202">Trabajo con tipos decimales</span><span class="sxs-lookup"><span data-stu-id="53ca0-202">Work with decimal types</span></span>

<span data-ttu-id="53ca0-203">Hasta el momento ha visto los tipos numéricos básicos en C#: los tipos integer y double.</span><span class="sxs-lookup"><span data-stu-id="53ca0-203">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="53ca0-204">Pero hay otro tipo más que debe conocer: `decimal`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-204">There's one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="53ca0-205">El tipo `decimal` tiene un intervalo más pequeño, pero mayor precisión que `double`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-205">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="53ca0-206">Observemos lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ca0-206">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="53ca0-207">Tenga en cuenta que el intervalo es más pequeño que con el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-207">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="53ca0-208">Puede observar una precisión mayor con el tipo decimal si prueba el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="53ca0-208">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="53ca0-209">El sufijo `M` en los números es la forma de indicar que una constante debe usar el tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-209">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span> <span data-ttu-id="53ca0-210">De no ser así, el compilador asume el tipo de `double`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-210">Otherwise, the compiler assumes the `double` type.</span></span>

> [!NOTE]
> <span data-ttu-id="53ca0-211">La letra `M` se eligió como la letra más distintiva visualmente entre las palabras clave `double` y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-211">The letter `M` was chosen as the most visually distinct letter between the `double` and `decimal` keywords.</span></span>

<span data-ttu-id="53ca0-212">Observe que la expresión matemática con el tipo decimal tiene más dígitos a la derecha del punto decimal.</span><span class="sxs-lookup"><span data-stu-id="53ca0-212">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="53ca0-213">***Desafío***</span><span class="sxs-lookup"><span data-stu-id="53ca0-213">***Challenge***</span></span>

<span data-ttu-id="53ca0-214">Ahora que ya conoce los diferentes tipos numéricos, escriba código para calcular el área de un círculo cuyo radio sea de 2,50 centímetros.</span><span class="sxs-lookup"><span data-stu-id="53ca0-214">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="53ca0-215">Recuerde que el área de un circulo es igual al valor de su radio elevado al cuadrado multiplicado por Pi.</span><span class="sxs-lookup"><span data-stu-id="53ca0-215">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="53ca0-216">Sugerencia: .NET contiene una constante de Pi, <xref:System.Math.PI?displayProperty=nameWithType>, que puede usar para ese valor.</span><span class="sxs-lookup"><span data-stu-id="53ca0-216">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> <span data-ttu-id="53ca0-217"><xref:System.Math.PI?displayProperty=nameWithType>, al igual que todas las constantes declaradas en el espacio de nombres `System.Math`, es un valor `double`.</span><span class="sxs-lookup"><span data-stu-id="53ca0-217"><xref:System.Math.PI?displayProperty=nameWithType>, like all constants declared in the `System.Math` namespace, is a `double` value.</span></span> <span data-ttu-id="53ca0-218">Por ese motivo, debe usar `double` en lugar de valores `decimal` para este desafío.</span><span class="sxs-lookup"><span data-stu-id="53ca0-218">For that reason, you should use `double` instead of `decimal` values for this challenge.</span></span>

<span data-ttu-id="53ca0-219">Debe obtener una respuesta entre 19 y 20.</span><span class="sxs-lookup"><span data-stu-id="53ca0-219">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="53ca0-220">Puede comprobar la respuesta si [consulta el ejemplo de código terminado en GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span><span class="sxs-lookup"><span data-stu-id="53ca0-220">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span></span>

<span data-ttu-id="53ca0-221">Si lo desea, pruebe con otras fórmulas.</span><span class="sxs-lookup"><span data-stu-id="53ca0-221">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="53ca0-222">Ha completado el inicio rápido "Números en C#".</span><span class="sxs-lookup"><span data-stu-id="53ca0-222">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="53ca0-223">Puede continuar con la guía de inicio rápido [Ramas y bucles](branches-and-loops-local.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="53ca0-223">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="53ca0-224">En estos temas encontrará más información sobre los números en C#:</span><span class="sxs-lookup"><span data-stu-id="53ca0-224">You can learn more about numbers in C# in the following articles:</span></span>

- [<span data-ttu-id="53ca0-225">Tipos numéricos integrales</span><span class="sxs-lookup"><span data-stu-id="53ca0-225">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="53ca0-226">Tipos numéricos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="53ca0-226">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="53ca0-227">Conversiones numéricas integradas</span><span class="sxs-lookup"><span data-stu-id="53ca0-227">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)
