---
title: for (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: 2c099411499c6ca8396c55955bdc634e48caf621
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306532"
---
# <a name="for-c-reference"></a><span data-ttu-id="5736b-102">for (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5736b-102">for (C# reference)</span></span>

<span data-ttu-id="5736b-103">Mediante el uso de un bucle `for`, se puede ejecutar una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`.loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to</span><span class="sxs-lookup"><span data-stu-id="5736b-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="5736b-104">Este tipo de bucle es útil para recorrer en iteración matrices y para otras aplicaciones en las que se sabe de antemano cuántas veces se quiere recorrer en iteración el bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>
  
## <a name="example"></a><span data-ttu-id="5736b-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5736b-105">Example</span></span>

<span data-ttu-id="5736b-106">En el ejemplo siguiente, el valor de `i` se escribe en la consola y se incrementa en 1 durante cada iteración del bucle:</span><span class="sxs-lookup"><span data-stu-id="5736b-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop:</span></span>
  
[!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]
  
<span data-ttu-id="5736b-107">La [instrucción for](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) del ejemplo anterior realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5736b-107">The [for statement](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) in the previous example performs the following actions:</span></span>
  
1.  <span data-ttu-id="5736b-108">Primero, se establece el valor inicial de la variable `i`.</span><span class="sxs-lookup"><span data-stu-id="5736b-108">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="5736b-109">Este paso solo se produce una vez, independientemente de cuántas veces se repita el bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-109">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="5736b-110">Esta inicialización se puede considerar que tiene lugar fuera del proceso de bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-110">You can think of this initialization as happening outside the looping process.</span></span>
  
2.  <span data-ttu-id="5736b-111">Para evaluar la condición (`i <= 5`), el valor de `i` se compara con 5.</span><span class="sxs-lookup"><span data-stu-id="5736b-111">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>
  
    -   <span data-ttu-id="5736b-112">Si `i` es menor o igual a 5, la condición se evalúa como `true` y se producen las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="5736b-112">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="5736b-113">La instrucción `Console.WriteLine` en el cuerpo del bucle muestra el valor de `i`.</span><span class="sxs-lookup"><span data-stu-id="5736b-113">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="5736b-114">El valor de `i` se incrementa en 1.</span><span class="sxs-lookup"><span data-stu-id="5736b-114">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="5736b-115">El bucle vuelve al principio del paso 2 para evaluar la condición de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5736b-115">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="5736b-116">Si `i` es mayor que 5, la condición se evalúa como `false`, y se sale del bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-116">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
<span data-ttu-id="5736b-117">Tenga en cuenta que, si el valor inicial de `i` es mayor que 5, el cuerpo del bucle no se ejecuta ni siquiera una vez.</span><span class="sxs-lookup"><span data-stu-id="5736b-117">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>

## <a name="sections-of-a-for-statement"></a><span data-ttu-id="5736b-118">Secciones de una instrucción for</span><span class="sxs-lookup"><span data-stu-id="5736b-118">Sections of a for statement</span></span>
  
<span data-ttu-id="5736b-119">Cada [instrucción for](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) define secciones de *inicializador*, *condición* e *iterador*.</span><span class="sxs-lookup"><span data-stu-id="5736b-119">Every [for statement](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) defines *initializer*, *condition*, and *iterator* sections.</span></span> <span data-ttu-id="5736b-120">Normalmente estas secciones determinan cuántas veces se repite el bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-120">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
<span data-ttu-id="5736b-121">Las secciones tienen los objetivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5736b-121">The sections serve the following purposes:</span></span>
  
-   <span data-ttu-id="5736b-122">La sección de inicializador establece las condiciones iniciales.</span><span class="sxs-lookup"><span data-stu-id="5736b-122">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="5736b-123">Las instrucciones de esta sección se ejecutan solo una vez, antes de entrar en el bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-123">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="5736b-124">La sección solo puede contener una de las dos opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="5736b-124">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="5736b-125">La declaración e inicialización de una variable de bucle local, como se muestra en el primer ejemplo (`int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="5736b-125">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="5736b-126">La variable es local para el bucle y no es accesible desde fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-126">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="5736b-127">Ninguna o más expresiones de instrucción de la siguiente lista, separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="5736b-127">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="5736b-128">instrucción [assignment](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="5736b-128">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="5736b-129">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="5736b-129">invocation of a method</span></span>  
  
        -   <span data-ttu-id="5736b-130">expresión de [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="5736b-130">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="5736b-131">expresión de [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="5736b-131">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="5736b-132">creación de un objeto mediante [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="5736b-132">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="5736b-133">expresión [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="5736b-133">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="5736b-134">La sección de condición contiene una expresión booleana que se evalúa para determinar si el bucle debe salir o volverse a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="5736b-134">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="5736b-135">La sección de iterador define lo que sucede después de cada iteración del cuerpo del bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-135">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="5736b-136">La sección de iterador contiene ninguna o más de las siguientes expresiones de instrucción, separadas por comas:</span><span class="sxs-lookup"><span data-stu-id="5736b-136">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="5736b-137">instrucción [assignment](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="5736b-137">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="5736b-138">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="5736b-138">invocation of a method</span></span>  
  
    -   <span data-ttu-id="5736b-139">expresión de [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="5736b-139">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="5736b-140">expresión de [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="5736b-140">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="5736b-141">creación de un objeto mediante [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="5736b-141">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="5736b-142">expresión [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="5736b-142">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="5736b-143">El cuerpo del bucle consta de una instrucción, una instrucción vacía o un bloque de instrucciones, que se crean incluyendo cero o más instrucciones entre llaves.</span><span class="sxs-lookup"><span data-stu-id="5736b-143">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="5736b-144">Se puede salir de un bucle `for` mediante la palabra clave [break](../../../csharp/language-reference/keywords/break.md), o bien se puede ir a la siguiente iteración mediante la palabra clave [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="5736b-144">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="5736b-145">También se puede salir de un bucle mediante una instrucción [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="5736b-145">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
<span data-ttu-id="5736b-146">En el primer ejemplo de este tema se muestra el tipo de bucle `for` más común, que realiza las siguientes opciones para las secciones:</span><span class="sxs-lookup"><span data-stu-id="5736b-146">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections:</span></span>
  
-   <span data-ttu-id="5736b-147">El inicializador declara e inicializa una variable de bucle local, `i`, que mantiene un recuento de las iteraciones del bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-147">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="5736b-148">La condición comprueba el valor de la variable de bucle con un valor final conocido, 5.</span><span class="sxs-lookup"><span data-stu-id="5736b-148">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="5736b-149">La sección de iterador usa una instrucción de incremento postfijo, `i++`, para realizar un recuento de cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="5736b-149">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>

## <a name="more-examples"></a><span data-ttu-id="5736b-150">Más ejemplos</span><span class="sxs-lookup"><span data-stu-id="5736b-150">More examples</span></span>
  
<span data-ttu-id="5736b-151">En el ejemplo siguiente se muestran varias opciones menos comunes: asignar un valor a una variable de bucle externa en la sección de inicializador, invocar el método `Console.WriteLine` en las secciones de inicializador y de iterador, y cambiar los valores de dos variables en la sección de iterador.</span><span class="sxs-lookup"><span data-stu-id="5736b-151">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section, invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>
  
[!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
<span data-ttu-id="5736b-152">Todas las expresiones que definen una instrucción `for` son opcionales.</span><span class="sxs-lookup"><span data-stu-id="5736b-152">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="5736b-153">Por ejemplo, la siguiente instrucción crea un bucle infinito:</span><span class="sxs-lookup"><span data-stu-id="5736b-153">For example, the following statement creates an infinite loop:</span></span>
  
[!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5736b-154">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5736b-154">C# language specification</span></span>  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
  
## <a name="see-also"></a><span data-ttu-id="5736b-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="5736b-155">See also</span></span>

[<span data-ttu-id="5736b-156">La instrucción for (especificación del lenguaje C#)</span><span class="sxs-lookup"><span data-stu-id="5736b-156">The for statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement)  
[<span data-ttu-id="5736b-157">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5736b-157">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="5736b-158">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5736b-158">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="5736b-159">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5736b-159">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="5736b-160">foreach, in</span><span class="sxs-lookup"><span data-stu-id="5736b-160">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
[<span data-ttu-id="5736b-161">for (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="5736b-161">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
[<span data-ttu-id="5736b-162">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="5736b-162">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
