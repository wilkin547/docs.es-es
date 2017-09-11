---
title: throw (Referencia de C#)
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: 955f6d87614e0b452ace162e79e34aec9decad54
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="throw-c-reference"></a><span data-ttu-id="740da-102">throw (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="740da-102">throw (C# Reference)</span></span>
<span data-ttu-id="740da-103">Indica la aparición de una excepción durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="740da-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="740da-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="740da-104">Remarks</span></span>

<span data-ttu-id="740da-105">La sintaxis de `throw` es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="740da-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="740da-106">donde `e` es una instancia de una clase derivada de <xref:System.Exception?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="740da-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=fullName>.</span></span> <span data-ttu-id="740da-107">En el ejemplo siguiente se usa la instrucción `throw` para producir una excepción @System.IndexOutOfRangeException si el argumento pasado a un método denominado `GetNumber` no se corresponde con un índice válido de una matriz interna.</span><span class="sxs-lookup"><span data-stu-id="740da-107">The following example uses the `throw` statement to throw an @System.IndexOutOfRangeException if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

<span data-ttu-id="740da-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="740da-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span></span>  

<span data-ttu-id="740da-109">Después, los autores de llamadas a método usan un bloque `try-catch` o `try-catch-finally` para controlar la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="740da-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="740da-110">En el ejemplo siguiente se controla la excepción producida por el método `GetNumber`.</span><span class="sxs-lookup"><span data-stu-id="740da-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

<span data-ttu-id="740da-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="740da-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span></span>  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="740da-112">Volver a iniciar una excepción</span><span class="sxs-lookup"><span data-stu-id="740da-112">Re-throwing an exception</span></span>

<span data-ttu-id="740da-113">`throw` también se puede usar en un bloque `catch` para volver a iniciar una excepción controlada en un bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="740da-113">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="740da-114">En este caso, `throw` no toma un operando de excepción.</span><span class="sxs-lookup"><span data-stu-id="740da-114">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="740da-115">Resulta más útil cuando un método pasa un argumento de un autor de llamada a otro método de biblioteca y el método de biblioteca produce una excepción que se debe pasar al autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="740da-115">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="740da-116">Por ejemplo, en el ejemplo siguiente se vuelve a iniciar una excepción @System.NullReferenceException que se produce al intentar recuperar el primer carácter de una cadena sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="740da-116">For example, the following example re-throws an @System.NullReferenceException that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

<span data-ttu-id="740da-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="740da-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="740da-118">También puede usar la sintaxis `throw e` en un bloque `catch` para crear instancias de una nueva excepción que se pase al autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="740da-118">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="740da-119">En este caso, no se conserva el seguimiento de la pila de la excepción original, que está disponible en la propiedad @System.Exception.Stacktrace.</span><span class="sxs-lookup"><span data-stu-id="740da-119">In this case, the stack trace of the original exception, which is available from the @System.Exception.Stacktrace property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="740da-120">La expresión `throw`</span><span class="sxs-lookup"><span data-stu-id="740da-120">The `throw` expression</span></span>

<span data-ttu-id="740da-121">A partir de C# 7, se puede usar `throw` como una expresión y como una instrucción.</span><span class="sxs-lookup"><span data-stu-id="740da-121">Starting with C# 7, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="740da-122">Esto permite iniciar una excepción en contextos que antes no se admitían.</span><span class="sxs-lookup"><span data-stu-id="740da-122">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="740da-123">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="740da-123">These include:</span></span>

- <span data-ttu-id="740da-124">[El operador condicional](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="740da-124">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="740da-125">En el ejemplo siguiente se usa una expresión `throw` para iniciar una excepción @System.ArgumentException si se pasa a un método una matriz de cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="740da-125">The following example uses a `throw` expression to throw an @System.ArgumentException if a method is passed an empty string array.</span></span> <span data-ttu-id="740da-126">Antes de C# 7, esta lógica tendría que aparecer en una instrucción `if`/`else`.</span><span class="sxs-lookup"><span data-stu-id="740da-126">Before C# 7, this logic would need to appear in an `if`/`else` statement.</span></span>

   <span data-ttu-id="740da-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="740da-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span></span>  
  
- <span data-ttu-id="740da-128">[El operador de uso combinado de NULL](../operators/null-conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="740da-128">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="740da-129">En el ejemplo siguiente, se usa una expresión `throw` con un operador de uso combinado de NULL para producir una excepción si la cadena asignada a una propiedad `Name` es `null`.</span><span class="sxs-lookup"><span data-stu-id="740da-129">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   <span data-ttu-id="740da-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="740da-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span></span>  
 
- <span data-ttu-id="740da-131">Un método o [lambda](../../lambda-expressions.md) con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="740da-131">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="740da-132">En el ejemplo siguiente se muestra un método con forma de expresión que produce una excepción @System.InvalidCastException porque no se admite una conversión a un valor @System.DateTime.</span><span class="sxs-lookup"><span data-stu-id="740da-132">The following example illustrates an expression-bodied method that throws an @System.InvalidCastException because a conversion to a @System.DateTime value is not supported.</span></span>
 
   <span data-ttu-id="740da-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="740da-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span></span>  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="740da-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="740da-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="740da-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="740da-135">See Also</span></span>  
 <span data-ttu-id="740da-136">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="740da-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="740da-137">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="740da-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="740da-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="740da-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="740da-139">[Instrucciones try, catch y throw en C++](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="740da-139">[The try, catch, and throw Statements in C++](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="740da-140">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="740da-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="740da-141">[Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="740da-141">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 [<span data-ttu-id="740da-142">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="740da-142">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

