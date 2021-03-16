---
title: 'Cambio importante: Mejora del control de cadenas de búsqueda vacías por parte de LastIndexOf'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde LastIndexOf y las API relacionadas ahora devuelven valores correctos al buscar una subcadena de longitud cero.
ms.date: 11/01/2020
ms.openlocfilehash: 9dc34300d867fe1bb9264494b3f2261bad2c1eea
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257432"
---
# <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a><span data-ttu-id="57248-103">Mejora del control de cadenas de búsqueda vacías por parte de LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="57248-103">LastIndexOf has improved handling of empty search strings</span></span>

<span data-ttu-id="57248-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> y las API relacionadas ahora devuelven valores correctos al buscar una subcadena de longitud cero (o equivalente a longitud cero) dentro de una cadena más grande.</span><span class="sxs-lookup"><span data-stu-id="57248-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs now return correct values when searching for a zero-length (or zero-length equivalent) substring within a larger string.</span></span>

## <a name="change-description"></a><span data-ttu-id="57248-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="57248-105">Change description</span></span>

<span data-ttu-id="57248-106">En .NET Framework y .NET Core 1.0-3.1, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> y las API relacionadas podrían devolver un valor incorrecto cuando el autor de la llamada busca una subcadena de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="57248-106">In .NET Framework and .NET Core 1.0 - 3.1, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs might return an incorrect value when the caller searches for a zero-length substring.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

<span data-ttu-id="57248-107">A partir de .NET 5, estas API devuelven el valor correcto para `LastIndexOf`.</span><span class="sxs-lookup"><span data-stu-id="57248-107">Starting with .NET 5, these APIs return the correct value for `LastIndexOf`.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

<span data-ttu-id="57248-108">En estos ejemplos, `5` es la respuesta correcta porque `"Hello".Substring(5)` y `"Hello".AsSpan().Slice(5)` generan una cadena vacía, que es trivialmente igual que la subcadena vacía que se busca.</span><span class="sxs-lookup"><span data-stu-id="57248-108">In these examples, `5` is the correct answer because `"Hello".Substring(5)` and `"Hello".AsSpan().Slice(5)` both produce an empty string, which is trivially equal to the empty substring that is sought.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="57248-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="57248-109">Reason for change</span></span>

<span data-ttu-id="57248-110">Este cambio formaba parte de un esfuerzo general de corrección de errores relacionados con el control de cadenas para .NET 5.</span><span class="sxs-lookup"><span data-stu-id="57248-110">This change was part of an overall bug fixing effort around string handling for .NET 5.</span></span> <span data-ttu-id="57248-111">También ayuda a unificar el comportamiento entre las plataformas Windows y las que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="57248-111">It also helps unify our behavior between Windows and non-Windows platforms.</span></span> <span data-ttu-id="57248-112">Para obtener más información, vea [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) y [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).</span><span class="sxs-lookup"><span data-stu-id="57248-112">For more information, see [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) and [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="57248-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="57248-113">Version introduced</span></span>

<span data-ttu-id="57248-114">5.0</span><span class="sxs-lookup"><span data-stu-id="57248-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="57248-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="57248-115">Recommended action</span></span>

<span data-ttu-id="57248-116">No tiene que realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="57248-116">You don't need to take any action.</span></span> <span data-ttu-id="57248-117">El entorno de ejecución de .NET 5 proporciona los nuevos comportamientos de forma automática.</span><span class="sxs-lookup"><span data-stu-id="57248-117">The .NET 5 runtime provides the new behaviors automatically.</span></span>

<span data-ttu-id="57248-118">No hay ningún modificador de compatibilidad para restaurar el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="57248-118">There is no compatibility switch to restore the old behavior.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="57248-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="57248-119">Affected APIs</span></span>

- <xref:System.String.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.Globalization.CompareInfo.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.MemoryExtensions.LastIndexOf%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.String.LastIndexOf`
- `Overload:System.Globalization.CompareInfo.LastIndexOf`
- `Overload:System.MemoryExtensions.LastIndexOf`

-->
