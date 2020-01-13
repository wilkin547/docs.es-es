---
title: when (Palabra clave contextual, Referencia de C#)
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 6a61c42ba2d01e84ffae376bf95c99877437be85
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712837"
---
# <a name="when-c-reference"></a><span data-ttu-id="d6315-102">when (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d6315-102">when (C# Reference)</span></span>

<span data-ttu-id="d6315-103">Puede usar la palabra clave contextual `when` para especificar una condición de filtro en dos contextos:</span><span class="sxs-lookup"><span data-stu-id="d6315-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="d6315-104">En la instrucción `catch` de un bloque [try/catch](try-catch.md) o [try/catch/finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="d6315-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="d6315-105">En la etiqueta `case` de una instrucción [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="d6315-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="d6315-106">`when` en una instrucción `catch`</span><span class="sxs-lookup"><span data-stu-id="d6315-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="d6315-107">A partir de C# 6, puede usarse `when` en una instrucción `catch` para especificar una condición que debe cumplirse para que el controlador de una excepción específica se ejecute.</span><span class="sxs-lookup"><span data-stu-id="d6315-107">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="d6315-108">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="d6315-108">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="d6315-109">donde *expr* es una expresión que se evalúa como un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="d6315-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="d6315-110">Si devuelve `true`, el controlador de excepciones se ejecuta; si devuelve `false`, no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d6315-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="d6315-111">En el ejemplo siguiente se usa la palabra clave `when` para ejecutar condicionalmente controladores para una <xref:System.Net.Http.HttpRequestException> según el texto del mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="d6315-111">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="d6315-112">`when` en una instrucción `switch`</span><span class="sxs-lookup"><span data-stu-id="d6315-112">`when` in a `switch` statement</span></span>

<span data-ttu-id="d6315-113">A partir de C# 7.0, las etiquetas `case` ya no tienen que ser mutuamente exclusivas y el orden con el que las etiquetas `case` aparecen en una instrucción `switch` puede determinar el bloque switch que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d6315-113">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="d6315-114">Puede usarse la palabra clave `when` para especificar una condición de filtro que haga que su etiqueta case asociada se cumpla únicamente si también se cumple la condición de filtro.</span><span class="sxs-lookup"><span data-stu-id="d6315-114">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="d6315-115">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="d6315-115">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="d6315-116">donde *expr* es un patrón de constante o un patrón de tipo que se compara con la expresión match y *when-condition* es cualquier expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="d6315-116">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="d6315-117">En el ejemplo siguiente se usa la palabra clave `when` para probar objetos `Shape` que tienen un área de cero, así como para probar una serie de objetos `Shape` que tienen un área mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="d6315-117">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="d6315-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6315-118">See also</span></span>

- [<span data-ttu-id="d6315-119">switch (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6315-119">switch statement</span></span>](switch.md)
- [<span data-ttu-id="d6315-120">try/catch (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6315-120">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="d6315-121">try/catch/finally (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6315-121">try/catch/finally statement</span></span>](try-catch-finally.md)
