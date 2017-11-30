---
title: bool (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords: bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1d52955d64a6c8063e4ea93ceb096459c1c5e984
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="bool-c-reference"></a><span data-ttu-id="4da23-102">bool (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4da23-102">bool (C# Reference)</span></span>
<span data-ttu-id="4da23-103">La palabra clave `bool` es un alias de <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4da23-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4da23-104">Se usa para declarar variables que almacenan los valores booleanos [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="4da23-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4da23-105">Si necesita una variable booleana que también pueda tener un valor de `null`, use `bool?`.</span><span class="sxs-lookup"><span data-stu-id="4da23-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="4da23-106">Para más información, consulte [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL).</span><span class="sxs-lookup"><span data-stu-id="4da23-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="literals"></a><span data-ttu-id="4da23-107">Literales</span><span class="sxs-lookup"><span data-stu-id="4da23-107">Literals</span></span>  
 <span data-ttu-id="4da23-108">Se puede asignar un valor booleano a una variable `bool`.</span><span class="sxs-lookup"><span data-stu-id="4da23-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="4da23-109">También se puede asignar una expresión que se evalúe como `bool` a una variable `bool`.</span><span class="sxs-lookup"><span data-stu-id="4da23-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 <span data-ttu-id="4da23-110">El valor predeterminado de una variable `bool` es `false`.</span><span class="sxs-lookup"><span data-stu-id="4da23-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="4da23-111">El valor predeterminado de una variable `bool?` es `null`.</span><span class="sxs-lookup"><span data-stu-id="4da23-111">The default value of a `bool?` variable is `null`.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="4da23-112">Conversiones</span><span class="sxs-lookup"><span data-stu-id="4da23-112">Conversions</span></span>  
 <span data-ttu-id="4da23-113">En C++, un valor de tipo `bool` se puede convertir en un valor de tipo `int`, es decir, `false` equivale a cero y `true` equivale a valores distintos de cero.</span><span class="sxs-lookup"><span data-stu-id="4da23-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="4da23-114">En C#, no hay ninguna conversión entre el tipo `bool` y otros tipos.</span><span class="sxs-lookup"><span data-stu-id="4da23-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="4da23-115">Por ejemplo, la siguiente instrucción `if` no es válida en C#:</span><span class="sxs-lookup"><span data-stu-id="4da23-115">For example, the following `if` statement is invalid in C#:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 <span data-ttu-id="4da23-116">Para probar una variable del tipo `int`, tendrá que compararla explícitamente con un valor, como cero, del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4da23-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="4da23-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4da23-117">Example</span></span>  
 <span data-ttu-id="4da23-118">En este ejemplo, se escribe un carácter desde el teclado y el programa comprueba si el carácter de entrada es una letra.</span><span class="sxs-lookup"><span data-stu-id="4da23-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="4da23-119">Si es una letra, comprueba si está en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4da23-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="4da23-120">Estas comprobaciones se realizan con <xref:System.Char.IsLetter%2A> y <xref:System.Char.IsLower%2A>; ambos devuelven el tipo `bool`:</span><span class="sxs-lookup"><span data-stu-id="4da23-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="4da23-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4da23-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4da23-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da23-122">See Also</span></span>  
 [<span data-ttu-id="4da23-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4da23-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4da23-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4da23-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4da23-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="4da23-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4da23-126">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="4da23-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="4da23-127">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="4da23-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="4da23-128">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="4da23-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="4da23-129">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="4da23-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
