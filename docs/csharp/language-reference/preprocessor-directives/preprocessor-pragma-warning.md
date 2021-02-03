---
description: '#pragma warning: Referencia de C#'
title: '#pragma warning: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 16582a74bd34f2c0d89950280f1d5fde25435eea
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99215997"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="511f0-103">#pragma warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="511f0-103">#pragma warning (C# Reference)</span></span>

<span data-ttu-id="511f0-104">`#pragma warning` puede habilitar o deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="511f0-104">`#pragma warning` can enable or disable certain warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="511f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="511f0-105">Syntax</span></span>

```csharp
#pragma warning disable warning-list
#pragma warning restore warning-list
```

## <a name="parameters"></a><span data-ttu-id="511f0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="511f0-106">Parameters</span></span>

 <span data-ttu-id="511f0-107">`warning-list` Una lista separada por comas de números de advertencia.</span><span class="sxs-lookup"><span data-stu-id="511f0-107">`warning-list` A comma-separated list of warning numbers.</span></span> <span data-ttu-id="511f0-108">El prefijo "CS" es opcional.</span><span class="sxs-lookup"><span data-stu-id="511f0-108">The "CS" prefix is optional.</span></span>

 <span data-ttu-id="511f0-109">Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` habilita todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="511f0-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>

> [!NOTE]
> <span data-ttu-id="511f0-110">Para buscar los números de advertencia en Visual Studio, compile el proyecto y después busque los números de advertencia en la ventana **Salida**.</span><span class="sxs-lookup"><span data-stu-id="511f0-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>

## <a name="example"></a><span data-ttu-id="511f0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="511f0-111">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="511f0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="511f0-112">See also</span></span>

- [<span data-ttu-id="511f0-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="511f0-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="511f0-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="511f0-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="511f0-115">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="511f0-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="511f0-116">Errores del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="511f0-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
- [<span data-ttu-id="511f0-117">Procedimiento para suprimir advertencias de análisis de código</span><span class="sxs-lookup"><span data-stu-id="511f0-117">How to suppress code analysis warnings</span></span>](../../../fundamentals/code-analysis/suppress-warnings.md)
