---
title: checked (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
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
ms.openlocfilehash: abe34772c0f07b0a43f7299088bf5ea9a1d2aa78
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-reference"></a><span data-ttu-id="563c7-102">checked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="563c7-102">checked (C# Reference)</span></span>
<span data-ttu-id="563c7-103">La palabra clave `checked` se usa con el fin de habilitar explícitamente la comprobación de desbordamiento para operaciones aritméticas y conversiones de tipo integral.</span><span class="sxs-lookup"><span data-stu-id="563c7-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="563c7-104">De manera predeterminada, una expresión que solo contiene valores constantes provoca un error del compilador si la expresión genera un valor fuera del intervalo del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="563c7-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="563c7-105">Si la expresión contiene uno o varios valores no constantes, el compilador no detecta el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="563c7-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="563c7-106">En el siguiente ejemplo, la evaluación de la expresión asignada a `i2` no genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="563c7-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 <span data-ttu-id="563c7-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="563c7-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span></span>  
  
 <span data-ttu-id="563c7-108">De manera predeterminada, estas expresiones no constantes no se someten a la comprobación de desbordamiento en tiempo de ejecución y no generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="563c7-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="563c7-109">En el ejemplo anterior, se muestra -2 147 483 639 como la suma de dos enteros positivos.</span><span class="sxs-lookup"><span data-stu-id="563c7-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="563c7-110">La comprobación de desbordamiento se puede habilitar mediante opciones del compilador, la configuración del entorno o la palabra clave `checked`.</span><span class="sxs-lookup"><span data-stu-id="563c7-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="563c7-111">En los ejemplos siguientes, se muestra cómo usar una expresión `checked` o un bloque `checked` para detectar el desbordamiento generado por la suma anterior en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="563c7-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="563c7-112">En ambos ejemplos se genera una excepción de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="563c7-112">Both examples raise an overflow exception.</span></span>  
  
 <span data-ttu-id="563c7-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="563c7-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span></span>  
  
 <span data-ttu-id="563c7-114">Se puede usar la palabra clave [unchecked](../../../csharp/language-reference/keywords/unchecked.md) para evitar la comprobación de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="563c7-114">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="563c7-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="563c7-115">Example</span></span>  
 <span data-ttu-id="563c7-116">En este ejemplo, se muestra cómo usar `checked` para habilitar la comprobación de desbordamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="563c7-116">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 <span data-ttu-id="563c7-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="563c7-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="563c7-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="563c7-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="563c7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="563c7-119">See Also</span></span>  
 <span data-ttu-id="563c7-120">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="563c7-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="563c7-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="563c7-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="563c7-122">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="563c7-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="563c7-123">[Checked y Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="563c7-123">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="563c7-124">unchecked</span><span class="sxs-lookup"><span data-stu-id="563c7-124">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)

