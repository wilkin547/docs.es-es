---
title: Checked y Unchecked (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
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
ms.openlocfilehash: 744f59dbf7ee8370010ff76d4e9dde20490de403
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="bd5e5-102">Checked y Unchecked (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bd5e5-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="bd5e5-103">Las instrucciones de C# se pueden ejecutar en un contexto comprobado o no comprobado.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="bd5e5-104">En un contexto no comprobado, el desbordamiento aritmético produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="bd5e5-105">En un contexto no comprobado, el desbordamiento aritmético se pasa por alto y el resultado se trunca.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="bd5e5-106">[checked](../../../csharp/language-reference/keywords/checked.md) Especifica un contexto comprobado.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="bd5e5-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Especifica un contexto no comprobado.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="bd5e5-108">Si no se especifican `checked` ni `unchecked`, el contexto predeterminado depende de factores externos, como las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="bd5e5-109">Las siguientes operaciones se ven afectadas por la comprobación del desbordamiento:</span><span class="sxs-lookup"><span data-stu-id="bd5e5-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="bd5e5-110">Expresiones que usan los siguientes operadores predefinidos en tipos integrales:</span><span class="sxs-lookup"><span data-stu-id="bd5e5-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="bd5e5-111">`++` `--` - (unario)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="bd5e5-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="bd5e5-112">Conversiones numéricas explícitas entre tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="bd5e5-113">La opción del compilador [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) permite especificar un contexto comprobado o no comprobado para todas las declaraciones aritméticas que no están explícitamente en el ámbito de una palabra clave `checked` o `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="bd5e5-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5e5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd5e5-114">See Also</span></span>  
 <span data-ttu-id="bd5e5-115">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd5e5-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bd5e5-116">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd5e5-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bd5e5-117">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd5e5-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="bd5e5-118">Palabras clave de instrucciones</span><span class="sxs-lookup"><span data-stu-id="bd5e5-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)

