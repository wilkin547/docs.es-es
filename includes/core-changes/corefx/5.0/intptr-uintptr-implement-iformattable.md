---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024709"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="8a4e8-101">IntPtr y UIntPtr implementan IFormattable</span><span class="sxs-lookup"><span data-stu-id="8a4e8-101">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="8a4e8-102"><xref:System.IntPtr> y <xref:System.UIntPtr> ahora implementan <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-102"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="8a4e8-103">Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-103">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8a4e8-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="8a4e8-104">Change description</span></span>

<span data-ttu-id="8a4e8-105">En versiones anteriores de .NET, <xref:System.IntPtr> y <xref:System.UIntPtr> no implementan <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-105">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="8a4e8-106">Las funciones que comprueban <xref:System.IFormattable> pueden revertir simplemente a llamar a <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> o <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, lo que significa que no se respetan los especificadores de formato ni las referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-106">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="8a4e8-107">En .NET 5.0 y versiones posteriores, <xref:System.IntPtr> y <xref:System.UIntPtr> implementan <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-107">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="8a4e8-108">Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-108">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="8a4e8-109">Este cambio afecta a escenarios como cadenas interpoladas y <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, entre otros.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-109">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8a4e8-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="8a4e8-110">Reason for change</span></span>

<span data-ttu-id="8a4e8-111"><xref:System.IntPtr> y <xref:System.UIntPtr> ahora tienen compatibilidad de lenguaje en C# mediante las palabras clave `nint` y `nuint`.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-111"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="8a4e8-112">Los tipos de respaldo se han actualizado para proporcionar paridad cercana (siempre que sea posible) con funcionalidad expuesta por otros tipos primitivos, como <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-112">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8a4e8-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="8a4e8-113">Version introduced</span></span>

<span data-ttu-id="8a4e8-114">5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="8a4e8-114">5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8a4e8-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="8a4e8-115">Recommended action</span></span>

<span data-ttu-id="8a4e8-116">Si no quiere que se use un especificador de formato o una referencia cultural personalizada al mostrar valores de estos tipos, puede llamar a las sobrecargas <xref:System.IntPtr.ToString?displayProperty=nameWithType> y <xref:System.UIntPtr.ToString?displayProperty=nameWithType> de `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-116">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

#### <a name="category"></a><span data-ttu-id="8a4e8-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="8a4e8-117">Category</span></span>

<span data-ttu-id="8a4e8-118">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="8a4e8-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8a4e8-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8a4e8-119">Affected APIs</span></span>

<span data-ttu-id="8a4e8-120">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="8a4e8-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
