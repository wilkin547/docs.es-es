---
title: for (Referencia de C#)
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: beac7727c8ce83d8ea20f0fc578f80ceef3053e7
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208096"
---
# <a name="for-c-reference"></a><span data-ttu-id="0756f-102">for (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0756f-102">for (C# reference)</span></span>

<span data-ttu-id="0756f-103">La instrucción `for` ejecuta una instrucción o un bloque de instrucciones mientras una expresión booleana especificada se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="0756f-103">The `for` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="0756f-104">En cualquier punto del bloque de instrucciones `for`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="0756f-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="0756f-105">También se puede salir de un bucle `for` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="0756f-105">You also can exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>
  
## <a name="structure-of-the-for-statement"></a><span data-ttu-id="0756f-106">Estructura de la instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="0756f-106">Structure of the `for` statement</span></span>

<span data-ttu-id="0756f-107">La instrucción `for` define las secciones *inicializador*, *condición* e *iterador*:</span><span class="sxs-lookup"><span data-stu-id="0756f-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>
  
```csharp
for (initializer; condition; iterator)  
    body  
```

<span data-ttu-id="0756f-108">Las tres secciones son opcionales.</span><span class="sxs-lookup"><span data-stu-id="0756f-108">All three sections are optional.</span></span> <span data-ttu-id="0756f-109">El cuerpo del bucle es una instrucción o un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="0756f-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="0756f-110">En el siguiente ejemplo se muestra la instrucción `for` con todas las secciones definidas:</span><span class="sxs-lookup"><span data-stu-id="0756f-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="0756f-111">La sección *inicializador*</span><span class="sxs-lookup"><span data-stu-id="0756f-111">The *initializer* section</span></span>

<span data-ttu-id="0756f-112">Las instrucciones de la sección *inicializador* se ejecutan solo una vez, antes de entrar en el bucle.</span><span class="sxs-lookup"><span data-stu-id="0756f-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="0756f-113">La sección *inicializador* es cualquiera de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="0756f-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="0756f-114">La declaración e inicialización de una variable de bucle local, a la que no se puede tener acceso desde fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="0756f-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="0756f-115">Ninguna, una o varias expresiones de instrucción de la siguiente lista, separadas por comas:</span><span class="sxs-lookup"><span data-stu-id="0756f-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="0756f-116">instrucción [assignment](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="0756f-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="0756f-117">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="0756f-117">invocation of a method</span></span>  

  - <span data-ttu-id="0756f-118">expresión de [incremento](../operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="0756f-118">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  

  - <span data-ttu-id="0756f-119">expresión de [decremento](../operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="0756f-119">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  

  - <span data-ttu-id="0756f-120">creación de un objeto mediante la palabra clave [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="0756f-120">creation of an object by using [new](new-operator.md) keyword</span></span>

  - <span data-ttu-id="0756f-121">expresión [await](await.md)</span><span class="sxs-lookup"><span data-stu-id="0756f-121">[await](await.md) expression</span></span>

<span data-ttu-id="0756f-122">La sección *inicializador* del ejemplo anterior declara e inicializa la variable de bucle local `i`:</span><span class="sxs-lookup"><span data-stu-id="0756f-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="0756f-123">La sección *condición*</span><span class="sxs-lookup"><span data-stu-id="0756f-123">The *condition* section</span></span>

<span data-ttu-id="0756f-124">La sección *condición*, si está presente, debe ser una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="0756f-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="0756f-125">Dicha expresión se evalúa antes de cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="0756f-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="0756f-126">Si la sección *condición* no está presente o la expresión booleana se evalúa como `true`, se ejecutará la siguiente iteración del bucle; en caso contrario, se sale del bucle.</span><span class="sxs-lookup"><span data-stu-id="0756f-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="0756f-127">La sección *condición* del ejemplo anterior determina si el bucle finaliza en función del valor de la variable de bucle local:</span><span class="sxs-lookup"><span data-stu-id="0756f-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="0756f-128">La sección *iterador*</span><span class="sxs-lookup"><span data-stu-id="0756f-128">The *iterator* section</span></span>

<span data-ttu-id="0756f-129">La sección *iterador* define lo que sucede después de cada iteración del cuerpo del bucle.</span><span class="sxs-lookup"><span data-stu-id="0756f-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="0756f-130">La sección *iterador* contiene ninguna o más de las siguientes expresiones de instrucción, separadas por comas:</span><span class="sxs-lookup"><span data-stu-id="0756f-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>  

- <span data-ttu-id="0756f-131">instrucción [assignment](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="0756f-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="0756f-132">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="0756f-132">invocation of a method</span></span>  

- <span data-ttu-id="0756f-133">expresión de [incremento](../operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="0756f-133">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  

- <span data-ttu-id="0756f-134">expresión de [decremento](../operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="0756f-134">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  

- <span data-ttu-id="0756f-135">creación de un objeto mediante la palabra clave [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="0756f-135">creation of an object by using [new](new-operator.md) keyword</span></span>

- <span data-ttu-id="0756f-136">expresión [await](await.md)</span><span class="sxs-lookup"><span data-stu-id="0756f-136">[await](await.md) expression</span></span>

<span data-ttu-id="0756f-137">La sección *iterador* del ejemplo anterior incrementa la variable de bucle local:</span><span class="sxs-lookup"><span data-stu-id="0756f-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="0756f-138">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0756f-138">Examples</span></span>

<span data-ttu-id="0756f-139">En el ejemplo siguiente se muestran varios usos menos comunes de las secciones de la instrucción `for`: asignar un valor a una variable de bucle externa en la sección *inicializador*, invocar un método en las secciones *inicializador* e *iterador*, y cambiar los valores de dos variables en la sección *iterador*.</span><span class="sxs-lookup"><span data-stu-id="0756f-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="0756f-140">Haga clic en **Ejecutar** para ejecutar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0756f-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="0756f-141">Después, puede modificar el código y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0756f-141">After that you can modify the code and run it again.</span></span>
  
[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]
  
<span data-ttu-id="0756f-142">En el ejemplo siguiente se define el bucle `for` infinito:</span><span class="sxs-lookup"><span data-stu-id="0756f-142">The following example defines the infinite `for` loop:</span></span>
  
[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]
  
## <a name="c-language-specification"></a><span data-ttu-id="0756f-143">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0756f-143">C# language specification</span></span>  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
  
## <a name="see-also"></a><span data-ttu-id="0756f-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="0756f-144">See also</span></span>

[<span data-ttu-id="0756f-145">La instrucción for (especificación del lenguaje C#)</span><span class="sxs-lookup"><span data-stu-id="0756f-145">The for statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement)  
[<span data-ttu-id="0756f-146">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0756f-146">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="0756f-147">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0756f-147">C# Programming Guide</span></span>](../../programming-guide/index.md)  
[<span data-ttu-id="0756f-148">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="0756f-148">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="0756f-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="0756f-149">foreach, in</span></span>](foreach-in.md)  
[<span data-ttu-id="0756f-150">for (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="0756f-150">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
[<span data-ttu-id="0756f-151">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="0756f-151">Iteration Statements</span></span>](iteration-statements.md)
