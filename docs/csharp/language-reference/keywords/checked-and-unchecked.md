---
title: Checked y Unchecked (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="8ac60-102">Checked y Unchecked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8ac60-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="8ac60-103">Las instrucciones de C# se pueden ejecutar en un contexto comprobado o no comprobado.</span><span class="sxs-lookup"><span data-stu-id="8ac60-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="8ac60-104">En un contexto no comprobado, el desbordamiento aritmético produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="8ac60-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="8ac60-105">En un contexto no comprobado, el desbordamiento aritmético se pasa por alto y el resultado se trunca.</span><span class="sxs-lookup"><span data-stu-id="8ac60-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="8ac60-106">[checked](../../../csharp/language-reference/keywords/checked.md) Especifica un contexto comprobado.</span><span class="sxs-lookup"><span data-stu-id="8ac60-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="8ac60-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Especifica un contexto no comprobado.</span><span class="sxs-lookup"><span data-stu-id="8ac60-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="8ac60-108">Si no se especifican `checked` ni `unchecked`, el contexto predeterminado depende de factores externos, como las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="8ac60-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="8ac60-109">Las siguientes operaciones se ven afectadas por la comprobación del desbordamiento:</span><span class="sxs-lookup"><span data-stu-id="8ac60-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="8ac60-110">Expresiones que usan los siguientes operadores predefinidos en tipos integrales:</span><span class="sxs-lookup"><span data-stu-id="8ac60-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="8ac60-111">`++` `--` - (unario)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="8ac60-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="8ac60-112">Conversiones numéricas explícitas entre tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="8ac60-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="8ac60-113">La opción del compilador [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) permite especificar un contexto comprobado o no comprobado para todas las declaraciones aritméticas que no están explícitamente en el ámbito de una palabra clave `checked` o `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="8ac60-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac60-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ac60-114">See Also</span></span>  
 [<span data-ttu-id="8ac60-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8ac60-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8ac60-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8ac60-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8ac60-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="8ac60-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8ac60-118">Palabras clave de instrucciones</span><span class="sxs-lookup"><span data-stu-id="8ac60-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)
