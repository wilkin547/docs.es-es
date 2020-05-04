---
title: 'for (instrucción): Referencia de C#'
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: cb83fa015eea19b156faebb5bed18cc1f0970cc1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738804"
---
# <a name="for-c-reference"></a><span data-ttu-id="9dbeb-102">for (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9dbeb-102">for (C# reference)</span></span>

<span data-ttu-id="9dbeb-103">La instrucción `for` ejecuta una instrucción o un bloque de instrucciones mientras una expresión booleana especificada se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-103">The `for` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="9dbeb-104">En cualquier punto del bloque de instrucciones `for`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="9dbeb-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="9dbeb-105">También se puede salir de un bucle `for` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="9dbeb-105">You can also exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="structure-of-the-for-statement"></a><span data-ttu-id="9dbeb-106">Estructura de la instrucción `for`</span><span class="sxs-lookup"><span data-stu-id="9dbeb-106">Structure of the `for` statement</span></span>

<span data-ttu-id="9dbeb-107">La instrucción `for` define las secciones *inicializador*, *condición* e *iterador*:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>

```csharp
for (initializer; condition; iterator)
    body
```

<span data-ttu-id="9dbeb-108">Las tres secciones son opcionales.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-108">All three sections are optional.</span></span> <span data-ttu-id="9dbeb-109">El cuerpo del bucle es una instrucción o un bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="9dbeb-110">En el siguiente ejemplo se muestra la instrucción `for` con todas las secciones definidas:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="9dbeb-111">La sección *inicializador*</span><span class="sxs-lookup"><span data-stu-id="9dbeb-111">The *initializer* section</span></span>

<span data-ttu-id="9dbeb-112">Las instrucciones de la sección *inicializador* se ejecutan solo una vez, antes de entrar en el bucle.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="9dbeb-113">La sección *inicializador* es cualquiera de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="9dbeb-114">La declaración e inicialización de una variable de bucle local, a la que no se puede tener acceso desde fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="9dbeb-115">Ninguna, una o varias expresiones de instrucción de la siguiente lista, separadas por comas:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="9dbeb-116">instrucción [assignment](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9dbeb-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="9dbeb-117">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="9dbeb-117">invocation of a method</span></span>

  - <span data-ttu-id="9dbeb-118">expresión de [incremento](../operators/arithmetic-operators.md#increment-operator-) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="9dbeb-118">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

  - <span data-ttu-id="9dbeb-119">expresión de [decremento](../operators/arithmetic-operators.md#decrement-operator---) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="9dbeb-119">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

  - <span data-ttu-id="9dbeb-120">creación de un objeto mediante el operador [new](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9dbeb-120">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

  - <span data-ttu-id="9dbeb-121">expresión [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="9dbeb-121">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="9dbeb-122">La sección *inicializador* del ejemplo anterior declara e inicializa la variable de bucle local `i`:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="9dbeb-123">La sección *condición*</span><span class="sxs-lookup"><span data-stu-id="9dbeb-123">The *condition* section</span></span>

<span data-ttu-id="9dbeb-124">La sección *condición*, si está presente, debe ser una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="9dbeb-125">Dicha expresión se evalúa antes de cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="9dbeb-126">Si la sección *condición* no está presente o la expresión booleana se evalúa como `true`, se ejecutará la siguiente iteración del bucle; en caso contrario, se sale del bucle.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="9dbeb-127">La sección *condición* del ejemplo anterior determina si el bucle finaliza en función del valor de la variable de bucle local:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="9dbeb-128">La sección *iterador*</span><span class="sxs-lookup"><span data-stu-id="9dbeb-128">The *iterator* section</span></span>

<span data-ttu-id="9dbeb-129">La sección *iterador* define lo que sucede después de cada iteración del cuerpo del bucle.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="9dbeb-130">La sección *iterador* contiene ninguna o más de las siguientes expresiones de instrucción, separadas por comas:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>

- <span data-ttu-id="9dbeb-131">instrucción [assignment](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9dbeb-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="9dbeb-132">invocación de un método</span><span class="sxs-lookup"><span data-stu-id="9dbeb-132">invocation of a method</span></span>

- <span data-ttu-id="9dbeb-133">expresión de [incremento](../operators/arithmetic-operators.md#increment-operator-) de prefijo o sufijo, como `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="9dbeb-133">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

- <span data-ttu-id="9dbeb-134">expresión de [decremento](../operators/arithmetic-operators.md#decrement-operator---) de prefijo o sufijo, como `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="9dbeb-134">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

- <span data-ttu-id="9dbeb-135">creación de un objeto mediante el operador [new](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9dbeb-135">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

- <span data-ttu-id="9dbeb-136">expresión [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="9dbeb-136">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="9dbeb-137">La sección *iterador* del ejemplo anterior incrementa la variable de bucle local:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="9dbeb-138">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9dbeb-138">Examples</span></span>

<span data-ttu-id="9dbeb-139">En el ejemplo siguiente se muestran varios usos menos comunes de las secciones de la instrucción `for`: asignar un valor a una variable de bucle externa en la sección *inicializador*, invocar un método en las secciones *inicializador* e *iterador*, y cambiar los valores de dos variables en la sección *iterador*.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="9dbeb-140">Haga clic en **Ejecutar** para ejecutar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="9dbeb-141">Después, puede modificar el código y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-141">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]

<span data-ttu-id="9dbeb-142">En el ejemplo siguiente se define el bucle `for` infinito:</span><span class="sxs-lookup"><span data-stu-id="9dbeb-142">The following example defines the infinite `for` loop:</span></span>

[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="9dbeb-143">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9dbeb-143">C# language specification</span></span>

<span data-ttu-id="9dbeb-144">Para más información, vea la sección [La declaración for](~/_csharplang/spec/statements.md#the-for-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="9dbeb-144">For more information, see [The for statement](~/_csharplang/spec/statements.md#the-for-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="9dbeb-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dbeb-145">See also</span></span>

- [<span data-ttu-id="9dbeb-146">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9dbeb-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9dbeb-147">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9dbeb-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9dbeb-148">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="9dbeb-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9dbeb-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="9dbeb-149">foreach, in</span></span>](foreach-in.md)
