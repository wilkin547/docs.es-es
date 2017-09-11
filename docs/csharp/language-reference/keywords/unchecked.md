---
title: unchecked (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
dev_langs:
- CSharp
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
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
ms.openlocfilehash: 5878a2412e6c85da85b1a3b8c2a8255b51e67137
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="unchecked-c-reference"></a><span data-ttu-id="f2c3b-102">unchecked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f2c3b-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="f2c3b-103">La palabra clave `unchecked` se usa para suprimir la comprobación de desbordamiento en las operaciones y conversiones aritméticas de tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="f2c3b-104">En un contexto unchecked, si una expresión genera un valor que está fuera del intervalo del tipo de destino, no se marca el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="f2c3b-105">Por ejemplo, dado que el cálculo del siguiente ejemplo se realiza en un bloque o una expresión `unchecked`, el hecho de que el resultado sea demasiado grande para un entero se omite y se asigna a `int1` el valor -2 147 483 639.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 <span data-ttu-id="f2c3b-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2c3b-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span></span>  
  
 <span data-ttu-id="f2c3b-107">Si se quita el entorno `unchecked`, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-107">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="f2c3b-108">El desbordamiento se puede detectar en tiempo de compilación porque todos los términos de la expresión son constantes.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-108">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="f2c3b-109">Las expresiones que contienen términos no constantes son unchecked de forma predeterminada en tiempo de compilación y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-109">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="f2c3b-110">Vea [checked](../../../csharp/language-reference/keywords/checked.md) para obtener información sobre cómo habilitar un entorno checked.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-110">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="f2c3b-111">Puesto que la comprobación de desbordamiento lleva tiempo, el uso del código unchecked en situaciones donde no hay riesgo de desbordamiento puede mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-111">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="f2c3b-112">Pero si el desbordamiento es una posibilidad, se debe usar un entorno checked.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-112">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2c3b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2c3b-113">Example</span></span>  
 <span data-ttu-id="f2c3b-114">En este ejemplo se muestra cómo usar la palabra clave `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="f2c3b-114">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 <span data-ttu-id="f2c3b-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2c3b-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f2c3b-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f2c3b-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2c3b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2c3b-117">See Also</span></span>  
 <span data-ttu-id="f2c3b-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2c3b-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f2c3b-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2c3b-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f2c3b-120">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2c3b-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f2c3b-121">[Checked y Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="f2c3b-121">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="f2c3b-122">checked</span><span class="sxs-lookup"><span data-stu-id="f2c3b-122">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)

