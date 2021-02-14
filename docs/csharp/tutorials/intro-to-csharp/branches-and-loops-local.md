---
title: 'Ramas y bucles: tutorial de introducción a C#'
description: En este tutorial sobre ramas y bucles, escribirá código de C# para explorar la sintaxis del lenguaje que admite ramas y bucles condicionales para ejecutar instrucciones de forma repetida.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 1c93c96217abf041b14b94aafcdfe85bb7018528
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585711"
---
# <a name="learn-conditional-logic-with-branch-and-loop-statements"></a><span data-ttu-id="f79d2-103">Obtenga información sobre la lógica condicional con instrucciones de rama y bucle</span><span class="sxs-lookup"><span data-stu-id="f79d2-103">Learn conditional logic with branch and loop statements</span></span>

<span data-ttu-id="f79d2-104">En este tutorial se enseña a escribir código que analiza variables y cambia la ruta de acceso de ejecución en función de dichas variables.</span><span class="sxs-lookup"><span data-stu-id="f79d2-104">This tutorial teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="f79d2-105">Escriba código de C# y vea los resultados de la compilación y la ejecución.</span><span class="sxs-lookup"><span data-stu-id="f79d2-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="f79d2-106">El tutorial contiene una serie de lecciones en las que se analizan las construcciones de bifurcaciones y bucles en C#.</span><span class="sxs-lookup"><span data-stu-id="f79d2-106">The tutorial contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="f79d2-107">En ellas se enseñan los aspectos básicos del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="f79d2-107">These lessons teach you the fundamentals of the C# language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f79d2-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f79d2-108">Prerequisites</span></span>

<span data-ttu-id="f79d2-109">En el tutorial se espera que tenga una máquina configurada para el desarrollo local.</span><span class="sxs-lookup"><span data-stu-id="f79d2-109">The tutorial expects that you have a machine set up for local development.</span></span> <span data-ttu-id="f79d2-110">En Windows, Linux o macOS, puede usar la CLI de .NET para crear, compilar y ejecutar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f79d2-110">On Windows, Linux, or macOS, you can use the .NET CLI to create, build, and run applications.</span></span> <span data-ttu-id="f79d2-111">En Windows, también puede usar Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f79d2-111">On Windows, you can use Visual Studio 2019.</span></span> <span data-ttu-id="f79d2-112">Para obtener instrucciones de configuración, consulte cómo [configurar el entorno local](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f79d2-112">For setup instructions, see [Set up your local environment](local-environment.md).</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="f79d2-113">Toma de decisiones con la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-113">Make decisions using the `if` statement</span></span>

<span data-ttu-id="f79d2-114">Cree un directorio denominado *branches-tutorial*.</span><span class="sxs-lookup"><span data-stu-id="f79d2-114">Create a directory named *branches-tutorial*.</span></span> <span data-ttu-id="f79d2-115">Conviértalo en el directorio actual y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f79d2-115">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n BranchesAndLoops -o .
```

<span data-ttu-id="f79d2-116">Este comando crea una nueva aplicación de consola de .NET en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f79d2-116">This command creates a new .NET console application in the current directory.</span></span>

<span data-ttu-id="f79d2-117">Abra *Program.cs* en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f79d2-117">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="f79d2-118">Pruebe este código escribiendo `dotnet run` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f79d2-118">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="f79d2-119">Debería ver el mensaje "The answer is greater than 10" (La respuesta es mayor que 10)</span><span class="sxs-lookup"><span data-stu-id="f79d2-119">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="f79d2-120">impreso en la consola.</span><span class="sxs-lookup"><span data-stu-id="f79d2-120">printed to your console.</span></span>

<span data-ttu-id="f79d2-121">Modifique la declaración de `b` para que el resultado de la suma sea menor que diez:</span><span class="sxs-lookup"><span data-stu-id="f79d2-121">Modify the declaration of `b` so that the sum is less than 10:</span></span>

```csharp
int b = 3;
```

<span data-ttu-id="f79d2-122">Escriba `dotnet run` de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f79d2-122">Type `dotnet run` again.</span></span> <span data-ttu-id="f79d2-123">Como la respuesta es menor que diez, no se imprime nada.</span><span class="sxs-lookup"><span data-stu-id="f79d2-123">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="f79d2-124">La **condición** que está probando es false.</span><span class="sxs-lookup"><span data-stu-id="f79d2-124">The **condition** you're testing is false.</span></span> <span data-ttu-id="f79d2-125">No tiene ningún código para ejecutar porque solo ha escrito una de las bifurcaciones posibles para una instrucción `if`: la bifurcación true.</span><span class="sxs-lookup"><span data-stu-id="f79d2-125">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="f79d2-126">Cuando explore C# o cualquier otro lenguaje de programación, cometerá errores al escribir código.</span><span class="sxs-lookup"><span data-stu-id="f79d2-126">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="f79d2-127">El compilador buscará dichos errores y los notificará.</span><span class="sxs-lookup"><span data-stu-id="f79d2-127">The compiler will find and report the errors.</span></span> <span data-ttu-id="f79d2-128">Fíjese en la salida de error y en el código que generó el error.</span><span class="sxs-lookup"><span data-stu-id="f79d2-128">Look closely at the error output and the code that generated the error.</span></span> <span data-ttu-id="f79d2-129">El error del compilador normalmente puede ayudarle a encontrar el problema.</span><span class="sxs-lookup"><span data-stu-id="f79d2-129">The compiler error can usually help you find the problem.</span></span>

<span data-ttu-id="f79d2-130">En este primer ejemplo se muestran la potencia de `if` y los tipos booleanos.</span><span class="sxs-lookup"><span data-stu-id="f79d2-130">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="f79d2-131">Un *booleano* es una variable que puede tener uno de estos dos valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-131">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="f79d2-132">C# define un tipo especial `bool` para las variables booleanas.</span><span class="sxs-lookup"><span data-stu-id="f79d2-132">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="f79d2-133">La instrucción `if` comprueba el valor de `bool`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-133">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="f79d2-134">Cuando el valor es `true`, se ejecuta la instrucción que sigue a `if`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-134">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="f79d2-135">De lo contrario, se omite.</span><span class="sxs-lookup"><span data-stu-id="f79d2-135">Otherwise, it's skipped.</span></span>

<span data-ttu-id="f79d2-136">Este proceso de comprobación de condiciones y ejecución de instrucciones en función de esas condiciones es muy eficaz.</span><span class="sxs-lookup"><span data-stu-id="f79d2-136">This process of checking conditions and executing statements based on those conditions is powerful.</span></span>

## <a name="make-if-and-else-work-together"></a><span data-ttu-id="f79d2-137">Operaciones conjuntas con if y else</span><span class="sxs-lookup"><span data-stu-id="f79d2-137">Make if and else work together</span></span>

<span data-ttu-id="f79d2-138">Para ejecutar un código distinto en las bifurcaciones true y false, cree una bifurcación `else` para que se ejecute cuando la condición sea false.</span><span class="sxs-lookup"><span data-stu-id="f79d2-138">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="f79d2-139">Pruebe esto.</span><span class="sxs-lookup"><span data-stu-id="f79d2-139">Try this.</span></span> <span data-ttu-id="f79d2-140">Agregue las dos últimas líneas del código siguiente a su método `Main` (ya debe tener los cuatro primeros):</span><span class="sxs-lookup"><span data-stu-id="f79d2-140">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="f79d2-141">La instrucción que sigue a la palabra clave `else` se ejecuta solo si la condición de prueba es `false`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-141">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="f79d2-142">La combinación de `if` y `else` con condiciones booleanas ofrece toda la eficacia necesaria para administrar una condición `true` y `false` simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="f79d2-142">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f79d2-143">La sangría debajo de las instrucciones `if` y `else` se utiliza para los lectores humanos.</span><span class="sxs-lookup"><span data-stu-id="f79d2-143">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="f79d2-144">El lenguaje C# no considera significativos los espacios en blanco ni las sangrías.</span><span class="sxs-lookup"><span data-stu-id="f79d2-144">The C# language doesn't treat indentation or white space as significant.</span></span>
> <span data-ttu-id="f79d2-145">La instrucción que sigue a la palabra clave `if` o `else` se ejecutará en función de la condición.</span><span class="sxs-lookup"><span data-stu-id="f79d2-145">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="f79d2-146">Todos los ejemplos de este tutorial siguen una práctica común para aplicar sangría a las líneas en función del flujo de control de las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f79d2-146">All the samples in this tutorial follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="f79d2-147">Dado que la sangría no es significativa, debe usar `{` y `}` para indicar si desea que más de una instrucción forme parte del bloque que se ejecuta de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="f79d2-147">Because indentation isn't significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="f79d2-148">Los programadores de C# suelen usar esas llaves en todas las cláusulas `if` y `else`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-148">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="f79d2-149">El siguiente ejemplo es igual que el que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="f79d2-149">The following example is the same as the one you created.</span></span> <span data-ttu-id="f79d2-150">Modifique el código anterior para que coincida con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f79d2-150">Modify your code above to match the following code:</span></span>

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
> <span data-ttu-id="f79d2-151">En el resto de este tutorial, todos los ejemplos de código incluyen las llaves, según las prácticas aceptadas.</span><span class="sxs-lookup"><span data-stu-id="f79d2-151">Through the rest of this tutorial, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="f79d2-152">Puede probar condiciones más complicadas.</span><span class="sxs-lookup"><span data-stu-id="f79d2-152">You can test more complicated conditions.</span></span> <span data-ttu-id="f79d2-153">Agregue el código siguiente a su método `Main` después del código que ha escrito hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="f79d2-153">Add the following code in your `Main` method after the code you've written so far:</span></span>

```csharp
int c = 4;
if ((a + b + c > 10) && (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not equal to the second");
}
```

<span data-ttu-id="f79d2-154">El símbolo `==` prueba la *igualdad*.</span><span class="sxs-lookup"><span data-stu-id="f79d2-154">The `==` symbol tests for *equality*.</span></span> <span data-ttu-id="f79d2-155">Usar `==` permite distinguir la prueba de igualdad de la asignación, que verá en `a = 5`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-155">Using `==` distinguishes the test for equality from assignment, which you saw in `a = 5`.</span></span>

<span data-ttu-id="f79d2-156">`&&` representa "y".</span><span class="sxs-lookup"><span data-stu-id="f79d2-156">The `&&` represents "and".</span></span> <span data-ttu-id="f79d2-157">Significa que ambas condiciones deben cumplirse para ejecutar la instrucción en la bifurcación true.</span><span class="sxs-lookup"><span data-stu-id="f79d2-157">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="f79d2-158">En estos ejemplos también se muestra que puede tener varias instrucciones en cada bifurcación condicional, siempre que las encierre entre `{` y `}`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-158">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="f79d2-159">También puede usar `||` para representar "o".</span><span class="sxs-lookup"><span data-stu-id="f79d2-159">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="f79d2-160">Agregue el código siguiente antes del que ha escrito hasta ahora:</span><span class="sxs-lookup"><span data-stu-id="f79d2-160">Add the following code after what you've written so far:</span></span>

```csharp
if ((a + b + c > 10) || (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not equal to the second");
}
```

<span data-ttu-id="f79d2-161">Modifique los valores de `a`, `b` y `c` y cambie entre `&&` y `||` para explorar.</span><span class="sxs-lookup"><span data-stu-id="f79d2-161">Modify the values of `a`, `b`, and `c` and switch between `&&` and `||` to explore.</span></span> <span data-ttu-id="f79d2-162">Obtendrá más conocimientos sobre el funcionamiento de los operadores `&&` y `||`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-162">You'll gain more understanding of how the `&&` and `||` operators work.</span></span>

<span data-ttu-id="f79d2-163">Ha terminado el primer paso.</span><span class="sxs-lookup"><span data-stu-id="f79d2-163">You've finished the first step.</span></span> <span data-ttu-id="f79d2-164">Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="f79d2-164">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="f79d2-165">Con este paso, resulta más fácil empezar con un nuevo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f79d2-165">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="f79d2-166">Cambie el nombre del método `Main` por `ExploreIf` y escriba un método `Main` nuevo que llame a `ExploreIf`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-166">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="f79d2-167">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f79d2-167">When you've finished, your code should look like this:</span></span>

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

<span data-ttu-id="f79d2-168">Convierta en comentario la llamada a `ExploreIf()`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-168">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="f79d2-169">De este modo la salida estará menos saturada a medida que trabaje en esta sección:</span><span class="sxs-lookup"><span data-stu-id="f79d2-169">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="f79d2-170">El `//` inicia un **comentario** en C#.</span><span class="sxs-lookup"><span data-stu-id="f79d2-170">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="f79d2-171">Los comentarios son cualquier texto que desea mantener en el código fuente pero que no se ejecuta como código.</span><span class="sxs-lookup"><span data-stu-id="f79d2-171">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="f79d2-172">El compilador no genera ningún código ejecutable a partir de comentarios.</span><span class="sxs-lookup"><span data-stu-id="f79d2-172">The compiler doesn't generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="f79d2-173">Uso de bucles para repetir las operaciones</span><span class="sxs-lookup"><span data-stu-id="f79d2-173">Use loops to repeat operations</span></span>

<span data-ttu-id="f79d2-174">En esta sección se usan **bucles** para repetir las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f79d2-174">In this section, you use **loops** to repeat statements.</span></span> <span data-ttu-id="f79d2-175">Pruebe este código en su método `Main`:</span><span class="sxs-lookup"><span data-stu-id="f79d2-175">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="f79d2-176">La instrucción `while` comprueba una condición y ejecuta la instrucción o el bloque de instrucciones que aparece después de `while`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-176">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="f79d2-177">La comprobación de la condición y la ejecución de dichas instrucciones se repetirán hasta que la condición sea false.</span><span class="sxs-lookup"><span data-stu-id="f79d2-177">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="f79d2-178">En este ejemplo aparece otro operador nuevo.</span><span class="sxs-lookup"><span data-stu-id="f79d2-178">There's one other new operator in this example.</span></span> <span data-ttu-id="f79d2-179">El código `++` que aparece después de la variable `counter` es el operador de **incremento**.</span><span class="sxs-lookup"><span data-stu-id="f79d2-179">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="f79d2-180">Suma un valor de uno al valor de `counter` y almacena dicho valor en la variable de `counter`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-180">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f79d2-181">Asegúrese de que la condición del bucle `while` cambia a false mientras ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="f79d2-181">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="f79d2-182">En caso contrario, se crea un **bucle infinito** donde nunca finaliza el programa.</span><span class="sxs-lookup"><span data-stu-id="f79d2-182">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="f79d2-183">Esto no está demostrado en este ejemplo, ya que tendrá que forzar al programa a cerrar mediante **CTRL-C** u otros medios.</span><span class="sxs-lookup"><span data-stu-id="f79d2-183">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="f79d2-184">El bucle `while` prueba la condición antes de ejecutar el código que sigue a `while`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-184">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="f79d2-185">El bucle `do` ... `while` primero ejecuta el código y después comprueba la condición.</span><span class="sxs-lookup"><span data-stu-id="f79d2-185">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="f79d2-186">El bucle *do while* se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f79d2-186">The *do while* loop is shown in the following code:</span></span>

```csharp
int counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="f79d2-187">Este bucle `do` y el bucle `while` anterior generan el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="f79d2-187">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="f79d2-188">Operaciones con el bucle for</span><span class="sxs-lookup"><span data-stu-id="f79d2-188">Work with the for loop</span></span>

<span data-ttu-id="f79d2-189">El bucle **for** se utiliza con frecuencia en C#.</span><span class="sxs-lookup"><span data-stu-id="f79d2-189">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="f79d2-190">Pruebe este código en su método Main():</span><span class="sxs-lookup"><span data-stu-id="f79d2-190">Try this code in your Main() method:</span></span>

```csharp
for (int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
}
```

<span data-ttu-id="f79d2-191">El código anterior funciona de la misma forma que los bucles `while` y `do` que ya ha usado.</span><span class="sxs-lookup"><span data-stu-id="f79d2-191">The previous code does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="f79d2-192">La instrucción `for` consta de tres partes que controlan su funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="f79d2-192">The `for` statement has three parts that control how it works.</span></span>

<span data-ttu-id="f79d2-193">La primera parte es el **inicializador de for**: `int index = 0;` declara que `index` es la variable de bucle y establece su valor inicial en `0`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-193">The first part is the **for initializer**: `int index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="f79d2-194">La parte central es la **condición de for**: `index < 10` declara que este bucle `for` debe continuar ejecutándose mientras que el valor del contador sea menor que diez.</span><span class="sxs-lookup"><span data-stu-id="f79d2-194">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="f79d2-195">La última parte es el **iterador de for**: `index++` especifica cómo modificar la variable de bucle después de ejecutar el bloque que sigue a la instrucción `for`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-195">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="f79d2-196">En este caso, especifica que `index` debe incrementarse en uno cada vez que el bloque se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f79d2-196">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="f79d2-197">Experimente usted mismo.</span><span class="sxs-lookup"><span data-stu-id="f79d2-197">Experiment yourself.</span></span> <span data-ttu-id="f79d2-198">Pruebe cada una de las siguientes variaciones:</span><span class="sxs-lookup"><span data-stu-id="f79d2-198">Try each of the following variations:</span></span>

- <span data-ttu-id="f79d2-199">Cambie el inicializador para que se inicie en un valor distinto.</span><span class="sxs-lookup"><span data-stu-id="f79d2-199">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="f79d2-200">Cambie la condición para que se detenga en un valor diferente.</span><span class="sxs-lookup"><span data-stu-id="f79d2-200">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="f79d2-201">Cuando haya terminado, escriba algo de código para practicar con lo que ha aprendido.</span><span class="sxs-lookup"><span data-stu-id="f79d2-201">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

<span data-ttu-id="f79d2-202">Hay otra instrucción de bucle que no se trata en este tutorial: la instrucción `foreach`.</span><span class="sxs-lookup"><span data-stu-id="f79d2-202">There's one other looping statement that isn't covered in this tutorial: the `foreach` statement.</span></span> <span data-ttu-id="f79d2-203">La instrucción `foreach` repite su instrucción con cada elemento de una secuencia de elementos.</span><span class="sxs-lookup"><span data-stu-id="f79d2-203">The `foreach` statement repeats its statement for every item in a sequence of items.</span></span> <span data-ttu-id="f79d2-204">Se usa más a menudo con *colecciones*, por lo que se trata en el siguiente tutorial.</span><span class="sxs-lookup"><span data-stu-id="f79d2-204">It's most often used with *collections*, so it's covered in the next tutorial.</span></span>

## <a name="created-nested-loops"></a><span data-ttu-id="f79d2-205">Bucles anidados creados</span><span class="sxs-lookup"><span data-stu-id="f79d2-205">Created nested loops</span></span>

<span data-ttu-id="f79d2-206">Se puede anidar un bucle `while`, `do` o `for` dentro de otro para crear una matriz mediante la combinación de cada elemento del bucle externo con cada elemento del bucle interno.</span><span class="sxs-lookup"><span data-stu-id="f79d2-206">A `while`, `do`, or `for` loop can be nested inside another loop to create a matrix using the combination of each item in the outer loop with each item in the inner loop.</span></span> <span data-ttu-id="f79d2-207">Vamos a crear un conjunto de pares alfanuméricos para representar filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="f79d2-207">Let's do that to build a set of alphanumeric pairs to represent rows and columns.</span></span>

<span data-ttu-id="f79d2-208">Un bucle `for` puede generar las filas:</span><span class="sxs-lookup"><span data-stu-id="f79d2-208">One `for` loop can generate the rows:</span></span>

```csharp
for (int row = 1; row < 11; row++)
{
    Console.WriteLine($"The row is {row}");
}
```

<span data-ttu-id="f79d2-209">Otro bucle puede generar las columnas:</span><span class="sxs-lookup"><span data-stu-id="f79d2-209">Another loop can generate the columns:</span></span>

```csharp
for (char column = 'a'; column < 'k'; column++)
{
    Console.WriteLine($"The column is {column}");
}
```

<span data-ttu-id="f79d2-210">Puede anidar un bucle dentro de otro para formar pares:</span><span class="sxs-lookup"><span data-stu-id="f79d2-210">You can nest one loop inside the other to form pairs:</span></span>

```csharp
for (int row = 1; row < 11; row++)
{
    for (char column = 'a'; column < 'k'; column++)
    {
        Console.WriteLine($"The cell is ({row}, {column})");
    }
}
```

<span data-ttu-id="f79d2-211">Puede ver que el bucle externo se incrementa una vez con cada ejecución completa del bucle interno.</span><span class="sxs-lookup"><span data-stu-id="f79d2-211">You can see that the outer loop increments once for each full run of the inner loop.</span></span> <span data-ttu-id="f79d2-212">Invierta el anidamiento de filas y columnas, y vea los cambios por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f79d2-212">Reverse the row and column nesting, and see the changes for yourself.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="f79d2-213">Combinación de ramas y bucles</span><span class="sxs-lookup"><span data-stu-id="f79d2-213">Combine branches and loops</span></span>

<span data-ttu-id="f79d2-214">Ahora que ya ha obtenido la información sobre el bucle `if` y las construcciones de bucles con el lenguaje C#, trate de escribir código de C# para obtener la suma de todos los enteros de uno a veinte que se puedan dividir entre tres.</span><span class="sxs-lookup"><span data-stu-id="f79d2-214">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="f79d2-215">Tenga en cuenta las siguientes sugerencias:</span><span class="sxs-lookup"><span data-stu-id="f79d2-215">Here are a few hints:</span></span>

- <span data-ttu-id="f79d2-216">El operador `%` proporciona el resto de una operación de división.</span><span class="sxs-lookup"><span data-stu-id="f79d2-216">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="f79d2-217">La instrucción `if` genera la condición para saber si un número debe formar parte de la suma.</span><span class="sxs-lookup"><span data-stu-id="f79d2-217">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="f79d2-218">El bucle `for` puede facilitar la repetición de una serie de pasos para todos los números comprendidos entre el uno y el veinte.</span><span class="sxs-lookup"><span data-stu-id="f79d2-218">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="f79d2-219">Pruébelo usted mismo.</span><span class="sxs-lookup"><span data-stu-id="f79d2-219">Try it yourself.</span></span> <span data-ttu-id="f79d2-220">Después, revise cómo lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="f79d2-220">Then check how you did.</span></span> <span data-ttu-id="f79d2-221">Debe obtener 63 como respuesta.</span><span class="sxs-lookup"><span data-stu-id="f79d2-221">You should get 63 for an answer.</span></span> <span data-ttu-id="f79d2-222">Puede ver una respuesta posible mediante la [visualización del código completado en GitHub](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54).</span><span class="sxs-lookup"><span data-stu-id="f79d2-222">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="f79d2-223">Ha completado el tutorial "Bifurcaciones y bucles".</span><span class="sxs-lookup"><span data-stu-id="f79d2-223">You've completed the "branches and loops" tutorial.</span></span>

<span data-ttu-id="f79d2-224">Puede continuar con el tutorial [Matrices y colecciones](arrays-and-collections.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f79d2-224">You can continue with the [Arrays and collections](arrays-and-collections.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="f79d2-225">Puede aprender más sobre estos conceptos en los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f79d2-225">You can learn more about these concepts in these articles:</span></span>

- [<span data-ttu-id="f79d2-226">Instrucciones If y else</span><span class="sxs-lookup"><span data-stu-id="f79d2-226">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="f79d2-227">Instrucción while</span><span class="sxs-lookup"><span data-stu-id="f79d2-227">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="f79d2-228">Instrucción do</span><span class="sxs-lookup"><span data-stu-id="f79d2-228">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="f79d2-229">Instrucción for</span><span class="sxs-lookup"><span data-stu-id="f79d2-229">For statement</span></span>](../../language-reference/keywords/for.md)
