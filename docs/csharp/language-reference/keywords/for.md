---
title: for (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d65c198b0fd763bddae4832290af038b8992eb48
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="for-c-reference"></a><span data-ttu-id="17d49-102">for (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="17d49-102">for (C# Reference)</span></span>
<span data-ttu-id="17d49-103">Mediante el uso de un bucle `for`, se puede ejecutar una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="17d49-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="17d49-104">Este tipo de bucle es útil para recorrer en iteración matrices y para otras aplicaciones en las que se sabe de antemano cuántas veces se quiere recorrer en iteración el bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17d49-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17d49-105">Example</span></span>  
 <span data-ttu-id="17d49-106">En el ejemplo siguiente, el valor de `i` se escribe en la consola y se incrementa en 1 durante cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop.</span></span>  
  
 <span data-ttu-id="17d49-107">[!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="17d49-107">[!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]</span></span>  
  
 <span data-ttu-id="17d49-108">La instrucción `for` del ejemplo anterior realiza las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="17d49-108">The `for` statement in the previous example performs the following actions.</span></span>  
  
1.  <span data-ttu-id="17d49-109">Primero, se establece el valor inicial de la variable `i`.</span><span class="sxs-lookup"><span data-stu-id="17d49-109">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="17d49-110">Este paso solo se produce una vez, independientemente de cuántas veces se repita el bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-110">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="17d49-111">Esta inicialización se puede considerar que tiene lugar fuera del proceso de bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-111">You can think of this initialization as happening outside the looping process.</span></span>  
  
2.  <span data-ttu-id="17d49-112">Para evaluar la condición (`i <= 5`), el valor de `i` se compara con 5.</span><span class="sxs-lookup"><span data-stu-id="17d49-112">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>  
  
    -   <span data-ttu-id="17d49-113">Si `i` es menor o igual a 5, la condición se evalúa como `true` y se producen las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="17d49-113">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="17d49-114">La instrucción `Console.WriteLine` en el cuerpo del bucle muestra el valor de `i`.</span><span class="sxs-lookup"><span data-stu-id="17d49-114">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="17d49-115">El valor de `i` se incrementa en 1.</span><span class="sxs-lookup"><span data-stu-id="17d49-115">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="17d49-116">El bucle vuelve al principio del paso 2 para evaluar la condición de nuevo.</span><span class="sxs-lookup"><span data-stu-id="17d49-116">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="17d49-117">Si `i` es mayor que 5, la condición se evalúa como `false`, y se sale del bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-117">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
 <span data-ttu-id="17d49-118">Tenga en cuenta que, si el valor inicial de `i` es mayor que 5, el cuerpo del bucle no se ejecuta ni siquiera una vez.</span><span class="sxs-lookup"><span data-stu-id="17d49-118">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>  
  
 <span data-ttu-id="17d49-119">Cada instrucción `for` define secciones de inicializador, condición e iterador.</span><span class="sxs-lookup"><span data-stu-id="17d49-119">Every `for` statement defines initializer, condition, and iterator sections.</span></span> <span data-ttu-id="17d49-120">Normalmente estas secciones determinan cuántas veces se repite el bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-120">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 <span data-ttu-id="17d49-121">Las secciones tienen los objetivos siguientes.</span><span class="sxs-lookup"><span data-stu-id="17d49-121">The sections serve the following purposes.</span></span>  
  
-   <span data-ttu-id="17d49-122">La sección de inicializador establece las condiciones iniciales.</span><span class="sxs-lookup"><span data-stu-id="17d49-122">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="17d49-123">Las instrucciones de esta sección se ejecutan solo una vez, antes de entrar en el bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-123">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="17d49-124">La sección solo puede contener una de las dos opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="17d49-124">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="17d49-125">La declaración e inicialización de una variable de bucle local, como se muestra en el primer ejemplo (`int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="17d49-125">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="17d49-126">La variable es local para el bucle y no es accesible desde fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-126">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="17d49-127">Ninguna o más expresiones de instrucción de la siguiente lista, separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="17d49-127">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="17d49-128">instrucción [assignment](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="17d49-128">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="17d49-129">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="17d49-129">invocation of a method</span></span>  
  
        -   <span data-ttu-id="17d49-130">expresión de [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="17d49-130">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="17d49-131">expresión de [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="17d49-131">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="17d49-132">creación de un objeto mediante [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="17d49-132">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="17d49-133">expresión [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="17d49-133">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="17d49-134">La sección de condición contiene una expresión booleana que se evalúa para determinar si el bucle debe salir o volverse a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="17d49-134">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="17d49-135">La sección de iterador define lo que sucede después de cada iteración del cuerpo del bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-135">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="17d49-136">La sección de iterador contiene ninguna o más de las siguientes expresiones de instrucción, separadas por comas:</span><span class="sxs-lookup"><span data-stu-id="17d49-136">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="17d49-137">instrucción [assignment](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="17d49-137">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="17d49-138">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="17d49-138">invocation of a method</span></span>  
  
    -   <span data-ttu-id="17d49-139">expresión de [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="17d49-139">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="17d49-140">expresión de [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="17d49-140">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="17d49-141">creación de un objeto mediante [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="17d49-141">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="17d49-142">expresión [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="17d49-142">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="17d49-143">El cuerpo del bucle consta de una instrucción, una instrucción vacía o un bloque de instrucciones, que se crean incluyendo cero o más instrucciones entre llaves.</span><span class="sxs-lookup"><span data-stu-id="17d49-143">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="17d49-144">Se puede salir de un bucle `for` mediante la palabra clave [break](../../../csharp/language-reference/keywords/break.md), o bien se puede ir a la siguiente iteración mediante la palabra clave [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="17d49-144">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="17d49-145">También se puede salir de un bucle mediante una instrucción [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="17d49-145">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
 <span data-ttu-id="17d49-146">En el primer ejemplo de este tema se muestra el tipo de bucle `for` más común, que realiza las siguientes opciones para las secciones.</span><span class="sxs-lookup"><span data-stu-id="17d49-146">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections.</span></span>  
  
-   <span data-ttu-id="17d49-147">El inicializador declara e inicializa una variable de bucle local, `i`, que mantiene un recuento de las iteraciones del bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-147">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="17d49-148">La condición comprueba el valor de la variable de bucle con un valor final conocido, 5.</span><span class="sxs-lookup"><span data-stu-id="17d49-148">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="17d49-149">La sección de iterador usa una instrucción de incremento postfijo, `i++`, para realizar un recuento de cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="17d49-149">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>  
  
 <span data-ttu-id="17d49-150">En el ejemplo siguiente se muestran varias opciones menos comunes: asignar un valor a una variable de bucle externa en la sección de inicializador, invocar el método `Console.WriteLine` en las secciones de inicializador y de iterador, y cambiar los valores de dos variables en la sección de iterador.</span><span class="sxs-lookup"><span data-stu-id="17d49-150">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section,  invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>  
  
 <span data-ttu-id="17d49-151">[!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="17d49-151">[!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]</span></span>  
  
 <span data-ttu-id="17d49-152">Todas las expresiones que definen una instrucción `for` son opcionales.</span><span class="sxs-lookup"><span data-stu-id="17d49-152">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="17d49-153">Por ejemplo, la siguiente instrucción crea un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="17d49-153">For example, the following statement creates an infinite loop.</span></span>  
  
 <span data-ttu-id="17d49-154">[!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="17d49-154">[!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="17d49-155">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="17d49-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="17d49-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="17d49-156">See Also</span></span>  
 <span data-ttu-id="17d49-157">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="17d49-157">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="17d49-158">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="17d49-158">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="17d49-159">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="17d49-159">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="17d49-160">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="17d49-160">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 <span data-ttu-id="17d49-161">[for (Instrucción) (C++)](/cpp/cpp/for-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="17d49-161">[for Statement (C++)](/cpp/cpp/for-statement-cpp) </span></span>  
 [<span data-ttu-id="17d49-162">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="17d49-162">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

