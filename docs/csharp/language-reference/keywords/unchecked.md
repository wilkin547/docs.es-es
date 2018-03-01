---
title: unchecked (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c05e7cb742d8e8f5a7804656a5ec13548d0498b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="f5528-102">unchecked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f5528-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="f5528-103">La palabra clave `unchecked` se usa para suprimir la comprobación de desbordamiento en las operaciones y conversiones aritméticas de tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="f5528-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="f5528-104">En un contexto unchecked, si una expresión genera un valor que está fuera del intervalo del tipo de destino, no se marca el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="f5528-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="f5528-105">Por ejemplo, dado que el cálculo del siguiente ejemplo se realiza en un bloque o una expresión `unchecked`, el hecho de que el resultado sea demasiado grande para un entero se omite y se asigna a `int1` el valor -2 147 483 639.</span><span class="sxs-lookup"><span data-stu-id="f5528-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 <span data-ttu-id="f5528-106">Si se quita el entorno `unchecked`, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="f5528-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="f5528-107">El desbordamiento se puede detectar en tiempo de compilación porque todos los términos de la expresión son constantes.</span><span class="sxs-lookup"><span data-stu-id="f5528-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="f5528-108">Las expresiones que contienen términos no constantes son unchecked de forma predeterminada en tiempo de compilación y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f5528-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="f5528-109">Vea [checked](../../../csharp/language-reference/keywords/checked.md) para obtener información sobre cómo habilitar un entorno checked.</span><span class="sxs-lookup"><span data-stu-id="f5528-109">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="f5528-110">Puesto que la comprobación de desbordamiento lleva tiempo, el uso del código unchecked en situaciones donde no hay riesgo de desbordamiento puede mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f5528-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="f5528-111">Pero si el desbordamiento es una posibilidad, se debe usar un entorno checked.</span><span class="sxs-lookup"><span data-stu-id="f5528-111">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5528-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5528-112">Example</span></span>  
 <span data-ttu-id="f5528-113">En este ejemplo se muestra cómo usar la palabra clave `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="f5528-113">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f5528-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f5528-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5528-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5528-115">See Also</span></span>  
 [<span data-ttu-id="f5528-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f5528-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f5528-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f5528-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f5528-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f5528-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f5528-119">Checked y Unchecked</span><span class="sxs-lookup"><span data-stu-id="f5528-119">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="f5528-120">checked</span><span class="sxs-lookup"><span data-stu-id="f5528-120">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)
