---
description: 'throw: Referencia de C#'
title: 'throw: Referencia de C#'
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
ms.openlocfilehash: 4cad4810b89f976f92ce576917feb2398acce636
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142042"
---
# <a name="throw-c-reference"></a><span data-ttu-id="44a73-103">throw (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="44a73-103">throw (C# Reference)</span></span>

<span data-ttu-id="44a73-104">Indica la aparición de una excepción durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="44a73-104">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44a73-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44a73-105">Remarks</span></span>

<span data-ttu-id="44a73-106">La sintaxis de `throw` es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="44a73-106">The syntax of `throw` is:</span></span>

```csharp
throw [e];
```

<span data-ttu-id="44a73-107">donde `e` es una instancia de una clase derivada de <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="44a73-107">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44a73-108">En el ejemplo siguiente se usa la instrucción `throw` para producir una excepción <xref:System.IndexOutOfRangeException> si el argumento pasado a un método denominado `GetNumber` no se corresponde con un índice válido de una matriz interna.</span><span class="sxs-lookup"><span data-stu-id="44a73-108">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

<span data-ttu-id="44a73-109">Después, los autores de llamadas a método usan un bloque `try-catch` o `try-catch-finally` para controlar la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="44a73-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="44a73-110">En el ejemplo siguiente se controla la excepción producida por el método `GetNumber`.</span><span class="sxs-lookup"><span data-stu-id="44a73-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a><span data-ttu-id="44a73-111">Inicio repetido de una excepción</span><span class="sxs-lookup"><span data-stu-id="44a73-111">Re-throwing an exception</span></span>

<span data-ttu-id="44a73-112">`throw` también se puede usar en un bloque `catch` para volver a iniciar una excepción controlada en un bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="44a73-112">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="44a73-113">En este caso, `throw` no toma un operando de excepción.</span><span class="sxs-lookup"><span data-stu-id="44a73-113">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="44a73-114">Resulta más útil cuando un método pasa un argumento de un autor de llamada a otro método de biblioteca y el método de biblioteca produce una excepción que se debe pasar al autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="44a73-114">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="44a73-115">Por ejemplo, en el ejemplo siguiente se vuelve a iniciar una excepción <xref:System.NullReferenceException> que se produce al intentar recuperar el primer carácter de una cadena sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="44a73-115">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span>

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> <span data-ttu-id="44a73-116">También puede usar la sintaxis `throw e` en un bloque `catch` para crear instancias de una nueva excepción que se pase al autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="44a73-116">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="44a73-117">En este caso, no se conserva el seguimiento de la pila de la excepción original, que está disponible en la propiedad <xref:System.Exception.StackTrace>.</span><span class="sxs-lookup"><span data-stu-id="44a73-117">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>

## <a name="the-throw-expression"></a><span data-ttu-id="44a73-118">La expresión `throw`</span><span class="sxs-lookup"><span data-stu-id="44a73-118">The `throw` expression</span></span>

<span data-ttu-id="44a73-119">A partir de C# 7.0, se puede usar `throw` como una expresión y como una instrucción.</span><span class="sxs-lookup"><span data-stu-id="44a73-119">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="44a73-120">Esto permite iniciar una excepción en contextos que antes no se admitían.</span><span class="sxs-lookup"><span data-stu-id="44a73-120">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="44a73-121">Entre ellas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="44a73-121">These include:</span></span>

- <span data-ttu-id="44a73-122">[El operador condicional](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="44a73-122">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="44a73-123">En el ejemplo siguiente se usa una expresión `throw` para iniciar una excepción <xref:System.ArgumentException> si se pasa a un método una matriz de cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="44a73-123">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="44a73-124">Antes de C# 7.0, esta lógica tenía que aparecer en una instrucción `if`/`else`.</span><span class="sxs-lookup"><span data-stu-id="44a73-124">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- <span data-ttu-id="44a73-125">[El operador de uso combinado de NULL](../operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="44a73-125">[the null-coalescing operator](../operators/null-coalescing-operator.md).</span></span> <span data-ttu-id="44a73-126">En el ejemplo siguiente, se usa una expresión `throw` con un operador de uso combinado de NULL para producir una excepción si la cadena asignada a una propiedad `Name` es `null`.</span><span class="sxs-lookup"><span data-stu-id="44a73-126">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- <span data-ttu-id="44a73-127">Un método o [lambda](../operators/lambda-expressions.md) con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="44a73-127">an expression-bodied [lambda](../operators/lambda-expressions.md) or method.</span></span> <span data-ttu-id="44a73-128">En el ejemplo siguiente se muestra un método con forma de expresión que produce una excepción <xref:System.InvalidCastException> porque no se admite una conversión a un valor <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="44a73-128">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="44a73-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="44a73-129">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="44a73-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="44a73-130">See also</span></span>

- [<span data-ttu-id="44a73-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="44a73-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="44a73-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="44a73-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="44a73-133">try-catch</span><span class="sxs-lookup"><span data-stu-id="44a73-133">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="44a73-134">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="44a73-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="44a73-135">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="44a73-135">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
