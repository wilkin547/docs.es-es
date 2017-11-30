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
# <a name="branches-and-loops"></a><span data-ttu-id="be36b-103">Bifurcaciones y bucles</span><span class="sxs-lookup"><span data-stu-id="be36b-103">Branches and loops</span></span>

<span data-ttu-id="be36b-104">Este tutorial le enseña a escribir código que examina las variables y cambia la ruta de acceso de ejecución en función de esas variables.</span><span class="sxs-lookup"><span data-stu-id="be36b-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="be36b-105">Escribir código C# y ver los resultados de compilación y ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="be36b-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="be36b-106">El inicio rápido contiene una serie de lecciones que explorar bifurcación y construcciones de bucles en C#.</span><span class="sxs-lookup"><span data-stu-id="be36b-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="be36b-107">En ellas se enseñan los aspectos básicos del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="be36b-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="be36b-108">Este inicio rápido en el que se espera que debe disponer de una máquina que se puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="be36b-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="be36b-109">El tema de .NET [empezar a trabajar en 10 minutos](https://www.microsoft.com/net/core) tiene instrucciones sobre cómo configurar el entorno de desarrollo local en Linux, Mac o PC.</span><span class="sxs-lookup"><span data-stu-id="be36b-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="be36b-110">Tomar decisiones con la `if` instrucción</span><span class="sxs-lookup"><span data-stu-id="be36b-110">Make decisions using the `if` statement</span></span>

<span data-ttu-id="be36b-111">Cree un directorio denominado **inicio rápido de bifurcaciones**.</span><span class="sxs-lookup"><span data-stu-id="be36b-111">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="be36b-112">Conviértalo en el directorio actual y ejecute `dotnet new console -n BranchesAndLoops -o .`.</span><span class="sxs-lookup"><span data-stu-id="be36b-112">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="be36b-113">Este comando crea una nueva aplicación de consola .NET Core en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="be36b-113">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="be36b-114">Abra **Program.cs** en su editor favorito y reemplace la línea `Console.Writeline("Hello World!");` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="be36b-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="be36b-115">Pruebe este código escribiendo `dotnet run` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="be36b-115">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="be36b-116">Debería ver el mensaje "la respuesta es mayor que 10".</span><span class="sxs-lookup"><span data-stu-id="be36b-116">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="be36b-117">imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="be36b-117">printed to your console.</span></span>

<span data-ttu-id="be36b-118">Modifique la declaración de `b` para que el resultado de la suma sea menor que diez:</span><span class="sxs-lookup"><span data-stu-id="be36b-118">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="be36b-119">Tipo `dotnet run` nuevo.</span><span class="sxs-lookup"><span data-stu-id="be36b-119">Type `dotnet run` again.</span></span> <span data-ttu-id="be36b-120">Como la respuesta es menor que diez, no se imprime nada.</span><span class="sxs-lookup"><span data-stu-id="be36b-120">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="be36b-121">La **condición** que está probando es false.</span><span class="sxs-lookup"><span data-stu-id="be36b-121">The **condition** you're testing is false.</span></span> <span data-ttu-id="be36b-122">No tiene ningún código para ejecutar porque solo ha escrito una de las bifurcaciones posibles para una instrucción `if`: la bifurcación true.</span><span class="sxs-lookup"><span data-stu-id="be36b-122">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="be36b-123">Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código.</span><span class="sxs-lookup"><span data-stu-id="be36b-123">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="be36b-124">El compilador buscará y notificar los errores.</span><span class="sxs-lookup"><span data-stu-id="be36b-124">The compiler will find and report the errors.</span></span> <span data-ttu-id="be36b-125">Examine con atención el la salida de error y el código que ha generado el error.</span><span class="sxs-lookup"><span data-stu-id="be36b-125">Look closely the the error output and the code that generated the error.</span></span> <span data-ttu-id="be36b-126">El error compler normalmente puede ayudarle a encontrar el problema.</span><span class="sxs-lookup"><span data-stu-id="be36b-126">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="be36b-127">Este primer ejemplo muestra la eficacia de `if` y tipos booleanos.</span><span class="sxs-lookup"><span data-stu-id="be36b-127">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="be36b-128">A *booleano* es una variable que puede tener uno de dos valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="be36b-128">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="be36b-129">C# define un tipo especial, `bool` para las variables booleanas.</span><span class="sxs-lookup"><span data-stu-id="be36b-129">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="be36b-130">La instrucción `if` comprueba el valor de `bool`.</span><span class="sxs-lookup"><span data-stu-id="be36b-130">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="be36b-131">Cuando el valor es `true`, se ejecuta la instrucción que sigue a `if`.</span><span class="sxs-lookup"><span data-stu-id="be36b-131">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="be36b-132">De lo contrario, se omite.</span><span class="sxs-lookup"><span data-stu-id="be36b-132">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="be36b-133">Este proceso de comprobación de condiciones y ejecución de instrucciones en función de esas condiciones es muy eficaz.</span><span class="sxs-lookup"><span data-stu-id="be36b-133">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="be36b-134">Operaciones conjuntas con if y else</span><span class="sxs-lookup"><span data-stu-id="be36b-134">Make if and else work together</span></span>

<span data-ttu-id="be36b-135">Para ejecutar un código distinto en las bifurcaciones true y false, cree una bifurcación `else` para que se ejecute cuando la condición sea false.</span><span class="sxs-lookup"><span data-stu-id="be36b-135">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="be36b-136">Pruebe esto.</span><span class="sxs-lookup"><span data-stu-id="be36b-136">Try this.</span></span> <span data-ttu-id="be36b-137">Agregue las dos últimas líneas en el código siguiente a su `Main` método (ya debe tener los primeros cuatro):</span><span class="sxs-lookup"><span data-stu-id="be36b-137">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="be36b-138">La instrucción que sigue a la palabra clave `else` se ejecuta solo si la condición de prueba es `false`.</span><span class="sxs-lookup"><span data-stu-id="be36b-138">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="be36b-139">Combinar `if` y `else` con un valor booleano condiciones proporciona toda la potencia que necesita para administrar tanto un `true` y un `false` condición.</span><span class="sxs-lookup"><span data-stu-id="be36b-139">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be36b-140">La sangría debajo de las instrucciones `if` y `else` se utiliza para los lectores humanos.</span><span class="sxs-lookup"><span data-stu-id="be36b-140">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="be36b-141">El lenguaje C# no considera significativos los espacios en blanco ni las sangrías.</span><span class="sxs-lookup"><span data-stu-id="be36b-141">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="be36b-142">La instrucción que sigue a la palabra clave `if` o `else` se ejecutará en función de la condición.</span><span class="sxs-lookup"><span data-stu-id="be36b-142">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="be36b-143">Todos los ejemplos de esta guía de inicio rápido siguen una práctica común para aplicar sangría a líneas basándose en el flujo de control de las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="be36b-143">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="be36b-144">Dado que la sangría no es significativa, debe usar `{` y `}` para indicar si desea que más de una instrucción forme parte del bloque que se ejecuta de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="be36b-144">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="be36b-145">Los programadores de C# suelen usar esas llaves en todas las cláusulas `if` y `else`.</span><span class="sxs-lookup"><span data-stu-id="be36b-145">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="be36b-146">En el ejemplo siguiente es el mismo que el que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="be36b-146">The following example is the same as the one you just created.</span></span> <span data-ttu-id="be36b-147">Modifique el código anterior para que coincida con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="be36b-147">Modify your code above to match the following code:</span></span>

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
> <span data-ttu-id="be36b-148">A través del resto de esta guía de inicio rápido, todas las muestras de código incluyen las llaves, siga aceptado prácticas.</span><span class="sxs-lookup"><span data-stu-id="be36b-148">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="be36b-149">Puede probar condiciones más complicadas.</span><span class="sxs-lookup"><span data-stu-id="be36b-149">You can test more complicated conditions.</span></span> <span data-ttu-id="be36b-150">Agregue el código siguiente en su `Main` método después del código que haya escrito hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="be36b-150">Add the following code in your `Main` method after the code you've written so far:</span></span>

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

<span data-ttu-id="be36b-151">`&&` representa "y".</span><span class="sxs-lookup"><span data-stu-id="be36b-151">The `&&` represents "and".</span></span> <span data-ttu-id="be36b-152">Significa que ambas condiciones deben cumplirse para ejecutar la instrucción en la bifurcación true.</span><span class="sxs-lookup"><span data-stu-id="be36b-152">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="be36b-153">En estos ejemplos también se muestra que puede tener varias instrucciones en cada bifurcación condicional, siempre que las encierre entre `{` y `}`.</span><span class="sxs-lookup"><span data-stu-id="be36b-153">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="be36b-154">También puede usar `||` para representar "o".</span><span class="sxs-lookup"><span data-stu-id="be36b-154">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="be36b-155">Agregue el código siguiente después de lo que ha escrito hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="be36b-155">Add the following code after what you've written so far:</span></span>

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

<span data-ttu-id="be36b-156">Ha terminado el primer paso.</span><span class="sxs-lookup"><span data-stu-id="be36b-156">You've finished the first step.</span></span> <span data-ttu-id="be36b-157">Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="be36b-157">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="be36b-158">Con este paso, resulta más fácil empezar con un nuevo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="be36b-158">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="be36b-159">Cambie el nombre del método `Main` por `ExploreIf` y escriba un método `Main` nuevo que llame a `ExploreIf`.</span><span class="sxs-lookup"><span data-stu-id="be36b-159">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="be36b-160">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="be36b-160">When you have finished, your code should look like this:</span></span>

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

<span data-ttu-id="be36b-161">Marcar como comentario la llamada a `ExploreIf()`.</span><span class="sxs-lookup"><span data-stu-id="be36b-161">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="be36b-162">Realizará la salida que menos saturado mientras trabaja en esta sección:</span><span class="sxs-lookup"><span data-stu-id="be36b-162">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="be36b-163">El `//` inicia un **comentario** en C#.</span><span class="sxs-lookup"><span data-stu-id="be36b-163">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="be36b-164">Los comentarios son cualquier texto que desea mantener en el código fuente, pero no se ejecutan como código.</span><span class="sxs-lookup"><span data-stu-id="be36b-164">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="be36b-165">El compilador no genera ningún código ejecutable de comentarios.</span><span class="sxs-lookup"><span data-stu-id="be36b-165">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="be36b-166">Uso de bucles para repetir las operaciones</span><span class="sxs-lookup"><span data-stu-id="be36b-166">Use loops to repeat operations</span></span>

<span data-ttu-id="be36b-167">En esta sección usan **bucles** repetir las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="be36b-167">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="be36b-168">Pruebe este código en su `Main` método:</span><span class="sxs-lookup"><span data-stu-id="be36b-168">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="be36b-169">El `while` instrucción comprueba una condición y ejecuta la instrucción o bloque de instrucciones después de la `while`.</span><span class="sxs-lookup"><span data-stu-id="be36b-169">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="be36b-170">Repetidamente comprueba la condición y ejecutar las instrucciones hasta que la condición es false.</span><span class="sxs-lookup"><span data-stu-id="be36b-170">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="be36b-171">En este ejemplo aparece otro operador nuevo.</span><span class="sxs-lookup"><span data-stu-id="be36b-171">There's one other new operator in this example.</span></span> <span data-ttu-id="be36b-172">El código `++` que aparece después de la variable `counter` es el operador de **incremento**.</span><span class="sxs-lookup"><span data-stu-id="be36b-172">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="be36b-173">Suma 1 al valor de `counter` y almacena ese valor en el `counter` variable.</span><span class="sxs-lookup"><span data-stu-id="be36b-173">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be36b-174">Asegúrese de que el `while` cambios de condición en false de bucle como para ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="be36b-174">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="be36b-175">En caso contrario, se crea un **bucle infinito** donde nunca finaliza el programa.</span><span class="sxs-lookup"><span data-stu-id="be36b-175">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="be36b-176">Que no está demostrada en este ejemplo, ya que tendrá que hacer que el programa para dejar de utilizar **CTRL-C** u otros medios.</span><span class="sxs-lookup"><span data-stu-id="be36b-176">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="be36b-177">El bucle `while` prueba la condición antes de ejecutar el código que sigue a `while`.</span><span class="sxs-lookup"><span data-stu-id="be36b-177">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="be36b-178">El bucle `do` ... `while` primero ejecuta el código y después comprueba la condición.</span><span class="sxs-lookup"><span data-stu-id="be36b-178">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="be36b-179">Al no mientras el bucle se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="be36b-179">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="be36b-180">Esto `do` bucle y las versiones anteriores `while` bucle generan el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="be36b-180">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="be36b-181">Operaciones con el bucle for</span><span class="sxs-lookup"><span data-stu-id="be36b-181">Work with the for loop</span></span>

<span data-ttu-id="be36b-182">El **para** bucle es más frecuente en C#.</span><span class="sxs-lookup"><span data-stu-id="be36b-182">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="be36b-183">Pruebe este código en el método Main():</span><span class="sxs-lookup"><span data-stu-id="be36b-183">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="be36b-184">Funciona de la misma forma que los bucles `while` y `do` que ya ha usado.</span><span class="sxs-lookup"><span data-stu-id="be36b-184">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="be36b-185">La instrucción `for` consta de tres partes que controlan su funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="be36b-185">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="be36b-186">La primera parte es el **inicializador de for**: `for index = 0;` declara que `index` es la variable de bucle y establece su valor inicial en `0`.</span><span class="sxs-lookup"><span data-stu-id="be36b-186">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="be36b-187">La parte central es la **condición de for**: `index < 10` declara que este bucle `for` debe continuar ejecutándose mientras que el valor del contador sea menor que diez.</span><span class="sxs-lookup"><span data-stu-id="be36b-187">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="be36b-188">La última parte es el **iterador de for**: `index++` especifica cómo modificar la variable de bucle después de ejecutar el bloque que sigue a la instrucción `for`.</span><span class="sxs-lookup"><span data-stu-id="be36b-188">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="be36b-189">En este caso, especifica que `index` debe incrementarse en uno cada vez que el bloque se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="be36b-189">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="be36b-190">Experimente con estas partes por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="be36b-190">Experiment with these yourself.</span></span> <span data-ttu-id="be36b-191">Pruebe todos los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="be36b-191">Try each of the following:</span></span>

- <span data-ttu-id="be36b-192">Cambie el inicializador para que se inicie en un valor distinto.</span><span class="sxs-lookup"><span data-stu-id="be36b-192">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="be36b-193">Cambie la condición para que se detenga en un valor diferente.</span><span class="sxs-lookup"><span data-stu-id="be36b-193">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="be36b-194">Cuando haya terminado, escriba algo de código para practicar con lo que ha aprendido.</span><span class="sxs-lookup"><span data-stu-id="be36b-194">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="be36b-195">Combinar bifurcaciones y bucles</span><span class="sxs-lookup"><span data-stu-id="be36b-195">Combine branches and loops</span></span>

<span data-ttu-id="be36b-196">Ahora que ya ha obtenido la información sobre el bucle `if` y las construcciones de bucles con el lenguaje C#, trate de escribir código de C# para obtener la suma de todos los enteros de uno a veinte que se puedan dividir entre tres.</span><span class="sxs-lookup"><span data-stu-id="be36b-196">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="be36b-197">Tenga en cuenta las siguientes sugerencias:</span><span class="sxs-lookup"><span data-stu-id="be36b-197">Here are a few hints:</span></span>

- <span data-ttu-id="be36b-198">El operador `%` proporciona el resto de una operación de división.</span><span class="sxs-lookup"><span data-stu-id="be36b-198">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="be36b-199">El `if` instrucción aporta la condición para ver si un número debe ser parte de la suma.</span><span class="sxs-lookup"><span data-stu-id="be36b-199">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="be36b-200">El bucle `for` puede facilitar la repetición de una serie de pasos para todos los números comprendidos entre el uno y el veinte.</span><span class="sxs-lookup"><span data-stu-id="be36b-200">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="be36b-201">Pruébelo usted mismo.</span><span class="sxs-lookup"><span data-stu-id="be36b-201">Try it yourself.</span></span> <span data-ttu-id="be36b-202">Después, revise cómo lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="be36b-202">Then check how you did.</span></span> <span data-ttu-id="be36b-203">Puede ver una respuesta posible por [ver el código completo en GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span><span class="sxs-lookup"><span data-stu-id="be36b-203">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="be36b-204">Ha completado el inicio rápido "bifurcaciones y bucles".</span><span class="sxs-lookup"><span data-stu-id="be36b-204">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="be36b-205">Puede continuar con la [matrices y colecciones](arrays-and-collections.md) inicio rápido en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="be36b-205">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="be36b-206">Puede obtener más información sobre estos conceptos en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="be36b-206">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="be36b-207">[Instrucciones If y else](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="be36b-207">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="be36b-208">[Instrucción while](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="be36b-208">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="be36b-209">[Instrucción do](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="be36b-209">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="be36b-210">Instrucción for</span><span class="sxs-lookup"><span data-stu-id="be36b-210">For statement</span></span>](../language-reference/keywords/for.md)   
