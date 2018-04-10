---
title: checked (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0ae77894cdc94e41dfa281b92ed3304e0dc25731
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="checked-c-reference"></a><span data-ttu-id="9952f-102">checked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9952f-102">checked (C# Reference)</span></span>
<span data-ttu-id="9952f-103">La palabra clave `checked` se usa con el fin de habilitar explícitamente la comprobación de desbordamiento para operaciones aritméticas y conversiones de tipo integral.</span><span class="sxs-lookup"><span data-stu-id="9952f-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="9952f-104">De manera predeterminada, una expresión que solo contiene valores constantes provoca un error del compilador si la expresión genera un valor fuera del intervalo del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="9952f-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="9952f-105">Si la expresión contiene uno o varios valores no constantes, el compilador no detecta el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="9952f-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="9952f-106">En el siguiente ejemplo, la evaluación de la expresión asignada a `i2` no genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="9952f-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 <span data-ttu-id="9952f-107">De manera predeterminada, estas expresiones no constantes no se someten a la comprobación de desbordamiento en tiempo de ejecución y no generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="9952f-107">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="9952f-108">En el ejemplo anterior, se muestra -2 147 483 639 como la suma de dos enteros positivos.</span><span class="sxs-lookup"><span data-stu-id="9952f-108">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="9952f-109">La comprobación de desbordamiento se puede habilitar mediante opciones del compilador, la configuración del entorno o la palabra clave `checked`.</span><span class="sxs-lookup"><span data-stu-id="9952f-109">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="9952f-110">En los ejemplos siguientes, se muestra cómo usar una expresión `checked` o un bloque `checked` para detectar el desbordamiento generado por la suma anterior en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9952f-110">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="9952f-111">En ambos ejemplos se genera una excepción de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="9952f-111">Both examples raise an overflow exception.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 <span data-ttu-id="9952f-112">Se puede usar la palabra clave [unchecked](../../../csharp/language-reference/keywords/unchecked.md) para evitar la comprobación de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="9952f-112">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9952f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9952f-113">Example</span></span>  
 <span data-ttu-id="9952f-114">En este ejemplo, se muestra cómo usar `checked` para habilitar la comprobación de desbordamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9952f-114">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="9952f-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9952f-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9952f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9952f-116">See Also</span></span>  
 [<span data-ttu-id="9952f-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9952f-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9952f-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9952f-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9952f-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="9952f-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9952f-120">Checked y Unchecked</span><span class="sxs-lookup"><span data-stu-id="9952f-120">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="9952f-121">unchecked</span><span class="sxs-lookup"><span data-stu-id="9952f-121">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)
