---
title: when (Palabra clave contextual, Referencia de C#)
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 2b041ca3a821f45dd63ce3f6bee7a920eb495651
ms.sourcegitcommit: 32f0d6f4c01ddc6ca78767c3a30e3305f8cd032c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "87427000"
---
# <a name="when-c-reference"></a><span data-ttu-id="d5dc9-102">when (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d5dc9-102">when (C# Reference)</span></span>

<span data-ttu-id="d5dc9-103">Puede usar la palabra clave contextual `when` para especificar una condición de filtro en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="d5dc9-103">You can use the `when` contextual keyword to specify a filter condition in the following contexts:</span></span>

- <span data-ttu-id="d5dc9-104">En la instrucción `catch` de un bloque [try/catch](try-catch.md) o [try/catch/finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="d5dc9-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="d5dc9-105">En la etiqueta `case` de una instrucción [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="d5dc9-105">In the `case` label of a [switch](switch.md) statement.</span></span>
- <span data-ttu-id="d5dc9-106">En la expresión [`switch`](../operators/switch-expression.md).</span><span class="sxs-lookup"><span data-stu-id="d5dc9-106">In the [`switch` expression](../operators/switch-expression.md).</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="d5dc9-107">`when` en una instrucción `catch`</span><span class="sxs-lookup"><span data-stu-id="d5dc9-107">`when` in a `catch` statement</span></span>

<span data-ttu-id="d5dc9-108">A partir de C# 6, puede usarse `when` en una instrucción `catch` para especificar una condición que debe cumplirse para que el controlador de una excepción específica se ejecute.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-108">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="d5dc9-109">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="d5dc9-109">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="d5dc9-110">donde *expr* es una expresión que se evalúa como un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-110">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="d5dc9-111">Si devuelve `true`, el controlador de excepciones se ejecuta; si devuelve `false`, no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-111">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="d5dc9-112">En el ejemplo siguiente se usa la palabra clave `when` para ejecutar condicionalmente controladores para una <xref:System.Net.Http.HttpRequestException> según el texto del mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-112">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="d5dc9-113">`when` en una instrucción `switch`</span><span class="sxs-lookup"><span data-stu-id="d5dc9-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="d5dc9-114">A partir de C# 7.0, las etiquetas `case` ya no tienen que ser mutuamente exclusivas y el orden con el que las etiquetas `case` aparecen en una instrucción `switch` puede determinar el bloque switch que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-114">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="d5dc9-115">Puede usarse la palabra clave `when` para especificar una condición de filtro que haga que su etiqueta case asociada se cumpla únicamente si también se cumple la condición de filtro.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="d5dc9-116">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="d5dc9-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="d5dc9-117">donde *expr* es un patrón de constante o un patrón de tipo que se compara con la expresión match y *when-condition* es cualquier expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="d5dc9-118">En el ejemplo siguiente se usa la palabra clave `when` para probar objetos `Shape` que tienen un área de cero, así como para probar una serie de objetos `Shape` que tienen un área mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="d5dc9-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="d5dc9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5dc9-119">See also</span></span>

- [<span data-ttu-id="d5dc9-120">switch (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d5dc9-120">switch statement</span></span>](switch.md)
- [<span data-ttu-id="d5dc9-121">try/catch (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d5dc9-121">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="d5dc9-122">try/catch/finally (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d5dc9-122">try/catch/finally statement</span></span>](try-catch-finally.md)
