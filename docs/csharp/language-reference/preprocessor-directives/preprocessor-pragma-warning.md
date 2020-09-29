---
description: '#pragma warning: Referencia de C#'
title: '#pragma warning: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5b67d384e37a5e509ce8ebcc5ddeb16a4437ea2b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168535"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="d6622-103">#pragma warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d6622-103">#pragma warning (C# Reference)</span></span>

<span data-ttu-id="d6622-104">`#pragma warning` puede habilitar o deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="d6622-104">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6622-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6622-105">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6622-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6622-106">Parameters</span></span>  

 `warning-list`  
 <span data-ttu-id="d6622-107">Una lista separada por comas de números de advertencia.</span><span class="sxs-lookup"><span data-stu-id="d6622-107">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="d6622-108">El prefijo "CS" es opcional.</span><span class="sxs-lookup"><span data-stu-id="d6622-108">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="d6622-109">Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` habilita todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="d6622-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6622-110">Para buscar los números de advertencia en Visual Studio, compile el proyecto y después busque los números de advertencia en la ventana **Salida**.</span><span class="sxs-lookup"><span data-stu-id="d6622-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6622-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6622-111">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d6622-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6622-112">See also</span></span>

- [<span data-ttu-id="d6622-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d6622-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d6622-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d6622-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d6622-115">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="d6622-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="d6622-116">Errores del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="d6622-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
