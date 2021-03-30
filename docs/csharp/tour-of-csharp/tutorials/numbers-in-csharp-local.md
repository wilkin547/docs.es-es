---
title: 'Números en C#: tutorial de introducción a C#'
description: Aprenda sobre C# mediante la exploración de tipos numéricos, sus usos, propiedades y métodos.
ms.date: 02/05/2021
ms.openlocfilehash: d6546fc8ac2609066a4f9b829749a4091fce7ce6
ms.sourcegitcommit: 5ce37699c2a51ed173171813be68ef7577b1aba5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104881112"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="093d7-103">Manipular números enteros y de punto flotante en C\#</span><span class="sxs-lookup"><span data-stu-id="093d7-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="093d7-104">En este tutorial se explican los tipos numéricos en C# de manera interactiva.</span><span class="sxs-lookup"><span data-stu-id="093d7-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="093d7-105">Escribirá pequeñas cantidades de código y luego compilará y ejecutará ese código.</span><span class="sxs-lookup"><span data-stu-id="093d7-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="093d7-106">El tutorial contiene una serie de lecciones que ofrecen información detallada sobre los números y las operaciones matemáticas en C#.</span><span class="sxs-lookup"><span data-stu-id="093d7-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="093d7-107">En ellas se enseñan los aspectos básicos del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="093d7-107">These lessons teach you the fundamentals of the C# language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="093d7-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="093d7-108">Prerequisites</span></span>

<span data-ttu-id="093d7-109">En el tutorial se espera que tenga una máquina configurada para el desarrollo local.</span><span class="sxs-lookup"><span data-stu-id="093d7-109">The tutorial expects that you have a machine set up for local development.</span></span> <span data-ttu-id="093d7-110">En Windows, Linux o macOS, puede usar la CLI de .NET para crear, compilar y ejecutar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="093d7-110">On Windows, Linux, or macOS, you can use the .NET CLI to create, build, and run applications.</span></span> <span data-ttu-id="093d7-111">En Mac o Windows, también puede usar Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="093d7-111">On Mac or Windows, you can use Visual Studio 2019.</span></span> <span data-ttu-id="093d7-112">Para obtener instrucciones de configuración, consulte cómo [configurar el entorno local](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="093d7-112">For setup instructions, see [Set up your local environment](local-environment.md).</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="093d7-113">Análisis de las operaciones matemáticas con enteros</span><span class="sxs-lookup"><span data-stu-id="093d7-113">Explore integer math</span></span>

<span data-ttu-id="093d7-114">Cree un directorio denominado *numbers-quickstart*.</span><span class="sxs-lookup"><span data-stu-id="093d7-114">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="093d7-115">Conviértalo en el directorio actual y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="093d7-115">Make it the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="093d7-116">Abra *Program.cs* en su editor favorito y reemplace el contenido del archivo por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="093d7-116">Open *Program.cs* in your favorite editor, and replace the contents of the file with the following code:</span></span>

```csharp
using System;

int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="093d7-117">Ejecute este código escribiendo `dotnet run` en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="093d7-117">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="093d7-118">Ha visto una de las operaciones matemáticas fundamentales con enteros.</span><span class="sxs-lookup"><span data-stu-id="093d7-118">You've seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="093d7-119">El tipo `int` representa un **entero**, que puede ser cero o un número entero positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="093d7-119">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="093d7-120">Use el símbolo `+` para la suma.</span><span class="sxs-lookup"><span data-stu-id="093d7-120">You use the `+` symbol for addition.</span></span> <span data-ttu-id="093d7-121">Otros operadores matemáticos comunes con enteros son:</span><span class="sxs-lookup"><span data-stu-id="093d7-121">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="093d7-122">`-` para resta</span><span class="sxs-lookup"><span data-stu-id="093d7-122">`-` for subtraction</span></span>
- <span data-ttu-id="093d7-123">`*` para multiplicación</span><span class="sxs-lookup"><span data-stu-id="093d7-123">`*` for multiplication</span></span>
- <span data-ttu-id="093d7-124">`/` para división</span><span class="sxs-lookup"><span data-stu-id="093d7-124">`/` for division</span></span>

<span data-ttu-id="093d7-125">Comience por explorar esas operaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="093d7-125">Start by exploring those different operations.</span></span> <span data-ttu-id="093d7-126">Agregue estas líneas después de la línea que escribe el valor de `c`:</span><span class="sxs-lookup"><span data-stu-id="093d7-126">Add these lines after the line that writes the value of `c`:</span></span>

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

<span data-ttu-id="093d7-127">Ejecute este código escribiendo `dotnet run` en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="093d7-127">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="093d7-128">Si quiere, también puede probar a escribir varias operaciones matemáticas en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="093d7-128">You can also experiment by writing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="093d7-129">Pruebe `c = a + b - 12 * 17;` por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="093d7-129">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="093d7-130">Se permite la combinación de variables y números constantes.</span><span class="sxs-lookup"><span data-stu-id="093d7-130">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="093d7-131">Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código.</span><span class="sxs-lookup"><span data-stu-id="093d7-131">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="093d7-132">El **compilador** buscará dichos errores y los notificará.</span><span class="sxs-lookup"><span data-stu-id="093d7-132">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="093d7-133">Si la salida contiene mensajes de error, revise detenidamente el código de ejemplo y el código de la ventana para saber qué debe corregir.</span><span class="sxs-lookup"><span data-stu-id="093d7-133">When the contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span> <span data-ttu-id="093d7-134">Este ejercicio le ayudará a aprender la estructura del código de C#.</span><span class="sxs-lookup"><span data-stu-id="093d7-134">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="093d7-135">Ha terminado el primer paso.</span><span class="sxs-lookup"><span data-stu-id="093d7-135">You've finished the first step.</span></span> <span data-ttu-id="093d7-136">Antes comenzar con la siguiente sección, se va a mover el código actual a un *método* independiente.</span><span class="sxs-lookup"><span data-stu-id="093d7-136">Before you start the next section, let's move the current code into a separate *method*.</span></span> <span data-ttu-id="093d7-137">Un método es una serie de instrucciones agrupadas a la que se ha puesto un nombre.</span><span class="sxs-lookup"><span data-stu-id="093d7-137">A method is a series of statements grouped together and given a name.</span></span> <span data-ttu-id="093d7-138">Llame a un método escribiendo el nombre del método seguido de `()`.</span><span class="sxs-lookup"><span data-stu-id="093d7-138">You call a method by writing the method's name followed by `()`.</span></span> <span data-ttu-id="093d7-139">La organización del código en métodos facilita empezar a trabajar con un ejemplo nuevo.</span><span class="sxs-lookup"><span data-stu-id="093d7-139">Organizing your code into methods makes it easier to start working with a new example.</span></span> <span data-ttu-id="093d7-140">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="093d7-140">When you finish, your code should look like this:</span></span>

```csharp
using System;

WorkWithIntegers();

void WorkWithIntegers()
{
    int a = 18;
    int b = 6;
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
```

<span data-ttu-id="093d7-141">La línea `WorkWithIntegers();` invoca el método.</span><span class="sxs-lookup"><span data-stu-id="093d7-141">The line `WorkWithIntegers();` invokes the method.</span></span> <span data-ttu-id="093d7-142">El código siguiente declara el método y lo define.</span><span class="sxs-lookup"><span data-stu-id="093d7-142">The following code declares the method and defines it.</span></span>

## <a name="explore-order-of-operations"></a><span data-ttu-id="093d7-143">Análisis sobre el orden de las operaciones</span><span class="sxs-lookup"><span data-stu-id="093d7-143">Explore order of operations</span></span>

<span data-ttu-id="093d7-144">Convierta en comentario la llamada a `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="093d7-144">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="093d7-145">De este modo la salida estará menos saturada a medida que trabaje en esta sección:</span><span class="sxs-lookup"><span data-stu-id="093d7-145">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkWithIntegers();
```

<span data-ttu-id="093d7-146">El `//` inicia un **comentario** en C#.</span><span class="sxs-lookup"><span data-stu-id="093d7-146">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="093d7-147">Los comentarios son cualquier texto que desea mantener en el código fuente pero que no se ejecuta como código.</span><span class="sxs-lookup"><span data-stu-id="093d7-147">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="093d7-148">El compilador no genera ningún código ejecutable a partir de comentarios.</span><span class="sxs-lookup"><span data-stu-id="093d7-148">The compiler doesn't generate any executable code from comments.</span></span> <span data-ttu-id="093d7-149">Dado que `WorkWithIntegers()` es un método, solo tiene que comentar una línea.</span><span class="sxs-lookup"><span data-stu-id="093d7-149">Because `WorkWithIntegers()` is a method, you need to only comment out one line.</span></span>

<span data-ttu-id="093d7-150">El lenguaje C# define la prioridad de las diferentes operaciones matemáticas con reglas compatibles con las reglas aprendidas en las operaciones matemáticas.</span><span class="sxs-lookup"><span data-stu-id="093d7-150">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span> <span data-ttu-id="093d7-151">La multiplicación y división tienen prioridad sobre la suma y resta.</span><span class="sxs-lookup"><span data-stu-id="093d7-151">Multiplication and division take precedence over addition and subtraction.</span></span> <span data-ttu-id="093d7-152">Explórelo mediante la adición del código siguiente tras la llamada a `dotnet run` y la ejecución de `WorkWithIntegers()`:</span><span class="sxs-lookup"><span data-stu-id="093d7-152">Explore that by adding the following code after the call to `WorkWithIntegers()`, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="093d7-153">La salida muestra que la multiplicación se realiza antes que la suma.</span><span class="sxs-lookup"><span data-stu-id="093d7-153">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="093d7-154">Puede forzar la ejecución de un orden diferente de las operaciones si la operación o las operaciones que realizó primero se incluyen entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="093d7-154">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="093d7-155">Agregue las líneas siguientes y ejecute de nuevo:</span><span class="sxs-lookup"><span data-stu-id="093d7-155">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="093d7-156">Combine muchas operaciones distintas para indagar más.</span><span class="sxs-lookup"><span data-stu-id="093d7-156">Explore more by combining many different operations.</span></span> <span data-ttu-id="093d7-157">Agregue algo similar a las líneas siguientes.</span><span class="sxs-lookup"><span data-stu-id="093d7-157">Add something like the following lines.</span></span> <span data-ttu-id="093d7-158">Pruebe `dotnet run` de nuevo.</span><span class="sxs-lookup"><span data-stu-id="093d7-158">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="093d7-159">Puede que haya observado un comportamiento interesante de los enteros.</span><span class="sxs-lookup"><span data-stu-id="093d7-159">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="093d7-160">La división de enteros siempre genera un entero como resultado, incluso cuando se espera que el resultado incluya un decimal o una parte de una fracción.</span><span class="sxs-lookup"><span data-stu-id="093d7-160">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="093d7-161">Si no ha observado este comportamiento, pruebe este código:</span><span class="sxs-lookup"><span data-stu-id="093d7-161">If you haven't seen this behavior, try the following code:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="093d7-162">Escriba `dotnet run` de nuevo para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="093d7-162">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="093d7-163">Antes de continuar, vamos a tomar todo el código que ha escrito en esta sección y a colocarlo en un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="093d7-163">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="093d7-164">Llame a ese nuevo método `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="093d7-164">Call that new method `OrderPrecedence`.</span></span> <span data-ttu-id="093d7-165">El código debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="093d7-165">Your code should look something like this:</span></span>

```csharp
using System;

// WorkWithIntegers();
OrderPrecedence();

void WorkWithIntegers()
{
    int a = 18;
    int b = 6;
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

void OrderPrecedence()
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
    int h = (e + f) / g;
    Console.WriteLine(h);
}
```

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="093d7-166">Información sobre los límites y la precisión de los enteros</span><span class="sxs-lookup"><span data-stu-id="093d7-166">Explore integer precision and limits</span></span>

<span data-ttu-id="093d7-167">En el último ejemplo se ha mostrado que la división de enteros trunca el resultado.</span><span class="sxs-lookup"><span data-stu-id="093d7-167">That last sample showed you that integer division truncates the result.</span></span> <span data-ttu-id="093d7-168">Puede obtener el **resto** con el operador de **módulo**, el carácter `%`.</span><span class="sxs-lookup"><span data-stu-id="093d7-168">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="093d7-169">Pruebe el código siguiente tras la llamada de método a `OrderPrecedence()`:</span><span class="sxs-lookup"><span data-stu-id="093d7-169">Try the following code after the method call to `OrderPrecedence()`:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="093d7-170">El tipo de entero de C# difiere de los enteros matemáticos en un aspecto: el tipo `int` tiene límites mínimo y máximo.</span><span class="sxs-lookup"><span data-stu-id="093d7-170">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="093d7-171">Agregue este código para ver esos límites:</span><span class="sxs-lookup"><span data-stu-id="093d7-171">Add this code to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="093d7-172">Si un cálculo genera un valor que supera los límites, se producirá una condición de **subdesbordamiento** o **desbordamiento**.</span><span class="sxs-lookup"><span data-stu-id="093d7-172">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="093d7-173">La respuesta parece ajustarse de un límite al otro.</span><span class="sxs-lookup"><span data-stu-id="093d7-173">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="093d7-174">Agregue estas dos líneas para ver un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="093d7-174">Add these two lines to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="093d7-175">Tenga en cuenta que la respuesta está muy próxima al entero mínimo (negativo).</span><span class="sxs-lookup"><span data-stu-id="093d7-175">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="093d7-176">Es lo mismo que `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="093d7-176">It's the same as `min + 2`.</span></span> <span data-ttu-id="093d7-177">La operación de suma **desbordó** los valores permitidos para los enteros.</span><span class="sxs-lookup"><span data-stu-id="093d7-177">The addition operation **overflowed** the allowed values for integers.</span></span> <span data-ttu-id="093d7-178">La respuesta es un número negativo muy grande porque un desbordamiento "se ajusta" desde el valor de entero más alto posible al más bajo.</span><span class="sxs-lookup"><span data-stu-id="093d7-178">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="093d7-179">Hay otros tipos numéricos con distintos límites y precisiones que podría usar si el tipo `int` no satisface sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="093d7-179">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="093d7-180">Vamos a explorar ahora esos otros tipos.</span><span class="sxs-lookup"><span data-stu-id="093d7-180">Let's explore those other types next.</span></span> <span data-ttu-id="093d7-181">Antes de comenzar la siguiente sección, mueva el código que escribió en esta sección a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="093d7-181">Before you start the next section, move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="093d7-182">Denomínelo `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="093d7-182">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="093d7-183">Operaciones con el tipo double</span><span class="sxs-lookup"><span data-stu-id="093d7-183">Work with the double type</span></span>

<span data-ttu-id="093d7-184">El tipo numérico `double` representa números de punto flotante de doble precisión.</span><span class="sxs-lookup"><span data-stu-id="093d7-184">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="093d7-185">Puede que no esté familiarizado con estos términos.</span><span class="sxs-lookup"><span data-stu-id="093d7-185">Those terms may be new to you.</span></span> <span data-ttu-id="093d7-186">Un número de **punto flotante** resulta útil para representar números no enteros cuya magnitud puede ser muy grande o pequeña.</span><span class="sxs-lookup"><span data-stu-id="093d7-186">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="093d7-187">La **precisión doble** es un término relativo que describe el número de dígitos binarios que se usan para almacenar el valor.</span><span class="sxs-lookup"><span data-stu-id="093d7-187">**Double-precision** is a relative term that describes the number of binary digits used to store the value.</span></span> <span data-ttu-id="093d7-188">Los números de **precisión doble** tienen el doble del número de dígitos binarios que la **precisión sencilla**.</span><span class="sxs-lookup"><span data-stu-id="093d7-188">**Double precision** numbers have twice the number of binary digits as **single-precision**.</span></span> <span data-ttu-id="093d7-189">En los equipos modernos, es más habitual usar números con precisión doble que con precisión sencilla.</span><span class="sxs-lookup"><span data-stu-id="093d7-189">On modern computers, it's more common to use double precision than single precision numbers.</span></span> <span data-ttu-id="093d7-190">Los números de **precisión sencilla** se declaran mediante la palabra clave `float`.</span><span class="sxs-lookup"><span data-stu-id="093d7-190">**Single precision** numbers are declared using the `float` keyword.</span></span> <span data-ttu-id="093d7-191">Comencemos a explorar.</span><span class="sxs-lookup"><span data-stu-id="093d7-191">Let's explore.</span></span> <span data-ttu-id="093d7-192">Agregue el siguiente código y observe el resultado:</span><span class="sxs-lookup"><span data-stu-id="093d7-192">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="093d7-193">Tenga en cuenta que la respuesta incluye la parte decimal del cociente.</span><span class="sxs-lookup"><span data-stu-id="093d7-193">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="093d7-194">Pruebe una expresión algo más complicada con tipos double:</span><span class="sxs-lookup"><span data-stu-id="093d7-194">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="093d7-195">El intervalo de un valor double es mucho más amplio que en el caso de los valores enteros.</span><span class="sxs-lookup"><span data-stu-id="093d7-195">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="093d7-196">Pruebe el código siguiente debajo del que ha escrito hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="093d7-196">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="093d7-197">Estos valores se imprimen en notación científica.</span><span class="sxs-lookup"><span data-stu-id="093d7-197">These values are printed in scientific notation.</span></span> <span data-ttu-id="093d7-198">El número a la izquierda de `E` es la mantisa.</span><span class="sxs-lookup"><span data-stu-id="093d7-198">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="093d7-199">El número a la derecha es el exponente, como una potencia de diez.</span><span class="sxs-lookup"><span data-stu-id="093d7-199">The number to the right is the exponent, as a power of 10.</span></span> <span data-ttu-id="093d7-200">Al igual que sucede con los números decimales en las operaciones matemáticas, los tipos double en C# pueden presentar errores de redondeo.</span><span class="sxs-lookup"><span data-stu-id="093d7-200">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="093d7-201">Pruebe este código:</span><span class="sxs-lookup"><span data-stu-id="093d7-201">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="093d7-202">Sabe que repetir `0.3` no es exactamente lo mismo que `1/3`.</span><span class="sxs-lookup"><span data-stu-id="093d7-202">You know that `0.3` repeating isn't exactly the same as `1/3`.</span></span>

<span data-ttu-id="093d7-203">***Desafío***</span><span class="sxs-lookup"><span data-stu-id="093d7-203">***Challenge***</span></span>

<span data-ttu-id="093d7-204">Pruebe otros cálculos con números grandes, números pequeños, multiplicaciones y divisiones con el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="093d7-204">Try other calculations with large numbers, small numbers, multiplication, and division using the `double` type.</span></span> <span data-ttu-id="093d7-205">Intente realizar cálculos más complicados.</span><span class="sxs-lookup"><span data-stu-id="093d7-205">Try more complicated calculations.</span></span> <span data-ttu-id="093d7-206">Una vez que haya invertido un tiempo en ello, tome el código que ha escrito y colóquelo en un nuevo método.</span><span class="sxs-lookup"><span data-stu-id="093d7-206">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="093d7-207">Ponga a ese nuevo método el nombre `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="093d7-207">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-decimal-types"></a><span data-ttu-id="093d7-208">Trabajo con tipos decimales</span><span class="sxs-lookup"><span data-stu-id="093d7-208">Work with decimal types</span></span>

<span data-ttu-id="093d7-209">Hasta el momento ha visto los tipos numéricos básicos en C#: los tipos integer y double.</span><span class="sxs-lookup"><span data-stu-id="093d7-209">You've seen the basic numeric types in C#: integers and doubles.</span></span> <span data-ttu-id="093d7-210">Pero hay otro tipo más que debe conocer: `decimal`.</span><span class="sxs-lookup"><span data-stu-id="093d7-210">There's one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="093d7-211">El tipo `decimal` tiene un intervalo más pequeño, pero mayor precisión que `double`.</span><span class="sxs-lookup"><span data-stu-id="093d7-211">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="093d7-212">Observemos lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="093d7-212">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="093d7-213">Tenga en cuenta que el intervalo es más pequeño que con el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="093d7-213">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="093d7-214">Puede observar una precisión mayor con el tipo decimal si prueba el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="093d7-214">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="093d7-215">El sufijo `M` en los números es la forma de indicar que una constante debe usar el tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="093d7-215">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span> <span data-ttu-id="093d7-216">De no ser así, el compilador asume el tipo de `double`.</span><span class="sxs-lookup"><span data-stu-id="093d7-216">Otherwise, the compiler assumes the `double` type.</span></span>

> [!NOTE]
> <span data-ttu-id="093d7-217">La letra `M` se eligió como la letra más distintiva visualmente entre las palabras clave `double` y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="093d7-217">The letter `M` was chosen as the most visually distinct letter between the `double` and `decimal` keywords.</span></span>

<span data-ttu-id="093d7-218">Observe que la expresión matemática con el tipo decimal tiene más dígitos a la derecha del punto decimal.</span><span class="sxs-lookup"><span data-stu-id="093d7-218">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="093d7-219">***Desafío***</span><span class="sxs-lookup"><span data-stu-id="093d7-219">***Challenge***</span></span>

<span data-ttu-id="093d7-220">Ahora que ya conoce los diferentes tipos numéricos, escriba código para calcular el área de un círculo cuyo radio sea de 2,50 centímetros.</span><span class="sxs-lookup"><span data-stu-id="093d7-220">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="093d7-221">Recuerde que el área de un circulo es igual al valor de su radio elevado al cuadrado multiplicado por Pi.</span><span class="sxs-lookup"><span data-stu-id="093d7-221">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="093d7-222">Sugerencia: .NET contiene una constante de Pi, <xref:System.Math.PI?displayProperty=nameWithType>, que puede usar para ese valor.</span><span class="sxs-lookup"><span data-stu-id="093d7-222">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> <span data-ttu-id="093d7-223"><xref:System.Math.PI?displayProperty=nameWithType>, al igual que todas las constantes declaradas en el espacio de nombres `System.Math`, es un valor `double`.</span><span class="sxs-lookup"><span data-stu-id="093d7-223"><xref:System.Math.PI?displayProperty=nameWithType>, like all constants declared in the `System.Math` namespace, is a `double` value.</span></span> <span data-ttu-id="093d7-224">Por ese motivo, debe usar `double` en lugar de valores `decimal` para este desafío.</span><span class="sxs-lookup"><span data-stu-id="093d7-224">For that reason, you should use `double` instead of `decimal` values for this challenge.</span></span>

<span data-ttu-id="093d7-225">Debe obtener una respuesta entre 19 y 20.</span><span class="sxs-lookup"><span data-stu-id="093d7-225">You should get an answer between 19 and 20.</span></span> <span data-ttu-id="093d7-226">Puede comprobar la respuesta si [consulta el ejemplo de código terminado en GitHub](https://github.com/dotnet/samples/tree/main/csharp/numbers-quickstart/Program.cs#L9-L11).</span><span class="sxs-lookup"><span data-stu-id="093d7-226">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/main/csharp/numbers-quickstart/Program.cs#L9-L11).</span></span>

<span data-ttu-id="093d7-227">Si lo desea, pruebe con otras fórmulas.</span><span class="sxs-lookup"><span data-stu-id="093d7-227">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="093d7-228">Ha completado el inicio rápido "Números en C#".</span><span class="sxs-lookup"><span data-stu-id="093d7-228">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="093d7-229">Puede continuar con la guía de inicio rápido [Ramas y bucles](branches-and-loops-local.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="093d7-229">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="093d7-230">En estos temas encontrará más información sobre los números en C#:</span><span class="sxs-lookup"><span data-stu-id="093d7-230">You can learn more about numbers in C# in the following articles:</span></span>

- [<span data-ttu-id="093d7-231">Tipos numéricos integrales</span><span class="sxs-lookup"><span data-stu-id="093d7-231">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="093d7-232">Tipos numéricos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="093d7-232">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="093d7-233">Conversiones numéricas integradas</span><span class="sxs-lookup"><span data-stu-id="093d7-233">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)
