---
title: '#pragma warning (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 89ff8151d55ac58a1b114f7727297704ce26b9a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481935"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="19d03-102">#pragma warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="19d03-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="19d03-103">`#pragma warning` puede habilitar o deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="19d03-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19d03-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19d03-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19d03-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19d03-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="19d03-106">Una lista separada por comas de números de advertencia.</span><span class="sxs-lookup"><span data-stu-id="19d03-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="19d03-107">El prefijo "CS" es opcional.</span><span class="sxs-lookup"><span data-stu-id="19d03-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="19d03-108">Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` habilita todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="19d03-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19d03-109">Para buscar los números de advertencia en Visual Studio, compile el proyecto y después busque los números de advertencia en la ventana **Salida**.</span><span class="sxs-lookup"><span data-stu-id="19d03-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19d03-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19d03-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="19d03-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="19d03-111">See Also</span></span>

- [<span data-ttu-id="19d03-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="19d03-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="19d03-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="19d03-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="19d03-114">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="19d03-114">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="19d03-115">Errores del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="19d03-115">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
