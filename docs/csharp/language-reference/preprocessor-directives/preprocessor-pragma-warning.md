---
title: '#pragma warning (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5330b448dc2b328992b2d29699557d20df56dee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="15971-102">#pragma warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="15971-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="15971-103">`#pragma warning` puede habilitar o deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="15971-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15971-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15971-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15971-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15971-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="15971-106">Una lista separada por comas de números de advertencia.</span><span class="sxs-lookup"><span data-stu-id="15971-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="15971-107">El prefijo "CS" es opcional.</span><span class="sxs-lookup"><span data-stu-id="15971-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="15971-108">Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` habilita todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="15971-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15971-109">Para buscar los números de advertencia en Visual Studio, compile el proyecto y después busque los números de advertencia en la ventana **Salida**.</span><span class="sxs-lookup"><span data-stu-id="15971-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15971-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15971-110">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="15971-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="15971-111">See Also</span></span>  
 [<span data-ttu-id="15971-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="15971-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="15971-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="15971-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="15971-114">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="15971-114">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="15971-115">Errores del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="15971-115">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
