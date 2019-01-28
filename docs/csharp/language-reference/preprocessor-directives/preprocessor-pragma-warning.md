---
title: '#pragma warning: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 7c664ee7d6e0e083eba958e6ee36a63009e13956
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606613"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="aa8e2-102">#pragma warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="aa8e2-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="aa8e2-103">`#pragma warning` puede habilitar o deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="aa8e2-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa8e2-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa8e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa8e2-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="aa8e2-106">Una lista separada por comas de números de advertencia.</span><span class="sxs-lookup"><span data-stu-id="aa8e2-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="aa8e2-107">El prefijo "CS" es opcional.</span><span class="sxs-lookup"><span data-stu-id="aa8e2-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="aa8e2-108">Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` habilita todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="aa8e2-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa8e2-109">Para buscar los números de advertencia en Visual Studio, compile el proyecto y después busque los números de advertencia en la ventana **Salida**.</span><span class="sxs-lookup"><span data-stu-id="aa8e2-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa8e2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa8e2-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa8e2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa8e2-111">See also</span></span>

- [<span data-ttu-id="aa8e2-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="aa8e2-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="aa8e2-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="aa8e2-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="aa8e2-114">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="aa8e2-114">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
- [<span data-ttu-id="aa8e2-115">Errores del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="aa8e2-115">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
