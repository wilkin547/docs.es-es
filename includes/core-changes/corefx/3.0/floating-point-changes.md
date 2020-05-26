---
ms.openlocfilehash: 719f336e1b38597674d6ee8f0c5429dd965054b1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721760"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a><span data-ttu-id="047c8-101">Cambios en los comportamientos de formato y análisis de los números de punto flotante</span><span class="sxs-lookup"><span data-stu-id="047c8-101">Floating-point formatting and parsing behavior changed</span></span>

<span data-ttu-id="047c8-102">Los comportamientos de formato y análisis de los números de punto flotante (de los tipos <xref:System.Double> y <xref:System.Single>) ahora son compatibles con IEEE.</span><span class="sxs-lookup"><span data-stu-id="047c8-102">Floating point parsing and formatting behavior (by the <xref:System.Double> and <xref:System.Single> types) are now IEEE-compliant.</span></span>

#### <a name="change-description"></a><span data-ttu-id="047c8-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="047c8-103">Change description</span></span>

<span data-ttu-id="047c8-104">En .NET Core 2.2 y en versiones anteriores, dar formato con <xref:System.Double.ToString%2A?displayProperty=nameWithType> y <xref:System.Single.ToString%2A?displayProperty=nameWithType>, y realizar análisis con <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> y <xref:System.Single.TryParse%2A?displayProperty=nameWithType> no es compatible con IEEE.</span><span class="sxs-lookup"><span data-stu-id="047c8-104">In .NET Core 2.2 and earlier versions, formatting with <xref:System.Double.ToString%2A?displayProperty=nameWithType> and <xref:System.Single.ToString%2A?displayProperty=nameWithType>, and parsing with <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> are not IEEE-compliant.</span></span> <span data-ttu-id="047c8-105">Como resultado, no es posible garantizar que un valor realizará todo el proceso con una cadena de formato estándar o personalizado compatible.</span><span class="sxs-lookup"><span data-stu-id="047c8-105">As a result, it is impossible to guarantee that a value will roundtrip with any supported standard or custom format string.</span></span> <span data-ttu-id="047c8-106">En algunas entradas, se puede producir un error al intentar analizar un valor con formato y, en otras, el valor analizado no es igual que el valor original.</span><span class="sxs-lookup"><span data-stu-id="047c8-106">For some inputs, the attempt to parse a formatted value can fail, and for others, the parsed value doesn't equal the original value.</span></span>

<span data-ttu-id="047c8-107">A partir de .NET Core 3.0, las operaciones de análisis y formato son compatibles con IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="047c8-107">Starting with .NET Core 3.0, parsing and formatting operations are IEEE 754-compliant.</span></span> <span data-ttu-id="047c8-108">Esto garantiza que el comportamiento de los tipos de punto flotante en .NET coincide con el de los lenguajes compatibles con IEEE, como C#.</span><span class="sxs-lookup"><span data-stu-id="047c8-108">This ensures that the behavior of floating-point types in .NET matches that of IEEE-compliant languages such as C#.</span></span> <span data-ttu-id="047c8-109">Para obtener más información, vea la entrada de blog [Mejoras de formato y análisis de punto flotante en .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="047c8-109">For more information, see the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="047c8-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="047c8-110">Version introduced</span></span>

<span data-ttu-id="047c8-111">3.0</span><span class="sxs-lookup"><span data-stu-id="047c8-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="047c8-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="047c8-112">Recommended action</span></span>

<span data-ttu-id="047c8-113">En la sección “Posible impacto en el código existente” de la entrada de blog [Mejoras de formato y análisis de punto flotante en .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/), se sugieren cambios en el código si observa un cambio de comportamiento en comparación con las aplicaciones de .NET Core 2.2. Por lo general, esto implica el uso de una cadena de formato estándar o personalizado diferente para aplicar el comportamiento deseado.</span><span class="sxs-lookup"><span data-stu-id="047c8-113">The "Potential impact to existing code" section of the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post suggests changes to your code if you observe a change of behavior when compared to .NET Core 2.2 applications Generally, this involves using a different standard or custom format string to enforce the desired behavior.</span></span> <span data-ttu-id="047c8-114">Es posible que algunos resultados no tengan una solución alternativa si anteriormente eran incorrectos.</span><span class="sxs-lookup"><span data-stu-id="047c8-114">Some results may not have a workaround if they were previously incorrect.</span></span>

#### <a name="category"></a><span data-ttu-id="047c8-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="047c8-115">Category</span></span>

<span data-ttu-id="047c8-116">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="047c8-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="047c8-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="047c8-117">Affected APIs</span></span>

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
