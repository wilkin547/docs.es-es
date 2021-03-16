---
title: 'Cambio importante: Cambio de nombres de parámetro en tipos derivados de Stream'
description: Obtenga información sobre el cambio importante de .NET 6.0 en las bibliotecas .NET básicas, en las que se han cambiado algunos nombres de parámetro en métodos de tipos derivados de Stream.
ms.date: 03/04/2021
ms.openlocfilehash: c685fae6a7ed20ea47815d5f89a4e066c75e1178
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260015"
---
# <a name="some-parameters-in-stream-derived-types-are-renamed"></a><span data-ttu-id="f5d82-103">Se ha cambiado el nombre de algunos parámetros en tipos derivados de Stream.</span><span class="sxs-lookup"><span data-stu-id="f5d82-103">Some parameters in Stream-derived types are renamed</span></span>

<span data-ttu-id="f5d82-104">En .NET 6, se ha cambiado el nombre de algunos parámetros de los métodos de los tipos derivados de <xref:System.IO.Stream?displayProperty=fullName> para que coincidan con la clase base.</span><span class="sxs-lookup"><span data-stu-id="f5d82-104">In .NET 6, some parameters of methods on types derived from <xref:System.IO.Stream?displayProperty=fullName> have been renamed to match the base class.</span></span>

## <a name="change-description"></a><span data-ttu-id="f5d82-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f5d82-105">Change description</span></span>

<span data-ttu-id="f5d82-106">En versiones anteriores de .NET, varios tipos derivados de <xref:System.IO.Stream> invalidan los métodos, pero utilizan nombres de parámetro diferentes a los que usa el tipo base.</span><span class="sxs-lookup"><span data-stu-id="f5d82-106">In previous .NET versions, several types derived from <xref:System.IO.Stream> override methods but use different parameter names than those used by the base type.</span></span> <span data-ttu-id="f5d82-107">Por ejemplo, el parámetro de matriz de bytes de <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> se denomina `array`, mientras que el argumento correspondiente en el método de la clase base se denomina `buffer`.</span><span class="sxs-lookup"><span data-stu-id="f5d82-107">For example, the byte array parameter of <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> is named `array` while the corresponding argument in the base class method is named `buffer`.</span></span>

<span data-ttu-id="f5d82-108">En .NET 6, todos los tipos que derivan de <xref:System.IO.Stream?displayProperty=fullName> para los que los nombres de parámetro no coincidían se han ajustado conforme al tipo base mediante el uso de los mismos nombres de parámetro que el tipo base.</span><span class="sxs-lookup"><span data-stu-id="f5d82-108">In .NET 6, all types that derive from <xref:System.IO.Stream?displayProperty=fullName> that had mismatched parameter names have been brought into conformance with the base type by using the same parameter names as the base type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f5d82-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f5d82-109">Version introduced</span></span>

<span data-ttu-id="f5d82-110">6.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="f5d82-110">6.0 Preview 1</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f5d82-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="f5d82-111">Reason for change</span></span>

<span data-ttu-id="f5d82-112">Hay varias razones para el cambio:</span><span class="sxs-lookup"><span data-stu-id="f5d82-112">There are several reasons for the change:</span></span>

- <span data-ttu-id="f5d82-113">Si se pasaba un argumento no válido y se producía una excepción, esa excepción podía contener el nombre del parámetro base o el nombre del parámetro derivado, dependiendo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f5d82-113">If an invalid argument was passed and an exception was thrown, that exception might have contained the base parameter's name or the derived parameter's name, depending on the implementation.</span></span> <span data-ttu-id="f5d82-114">Dado que puede que el autor de llamada haya estado usando un tipo de referencia como base o como tipo derivado, no es posible que el nombre del argumento en la excepción sea siempre correcto.</span><span class="sxs-lookup"><span data-stu-id="f5d82-114">Since the caller may have been using a reference typed as the base or as the derived type, it's impossible for the argument name in the exception to always be correct.</span></span>
- <span data-ttu-id="f5d82-115">Tener distintos nombres de parámetro dificulta la validación coherente del comportamiento en todas las implementaciones de <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="f5d82-115">Having different parameter names makes it harder to consistently validate behavior across all <xref:System.IO.Stream> implementations.</span></span>
- <span data-ttu-id="f5d82-116">.NET 6 agrega un método público en <xref:System.IO.Stream> para validar los argumentos y los métodos deben tener un nombre de parámetro coherente para usar.</span><span class="sxs-lookup"><span data-stu-id="f5d82-116">.NET 6 adds a public method on <xref:System.IO.Stream> for validating arguments, and that methods needs to have a consistent parameter name to use.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f5d82-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f5d82-117">Recommended action</span></span>

<span data-ttu-id="f5d82-118">El efecto de este cambio importante es mínimo:</span><span class="sxs-lookup"><span data-stu-id="f5d82-118">The effect of this breaking change is minimal:</span></span>

- <span data-ttu-id="f5d82-119">Para los archivos binarios existentes, su impacto se limita al código que usa la reflexión para examinar los nombres de parámetro en los tipos derivados afectados.</span><span class="sxs-lookup"><span data-stu-id="f5d82-119">For existing binaries, its impact is limited to code that uses reflection to examine the names of parameters on the affected derived types.</span></span>
- <span data-ttu-id="f5d82-120">En el código fuente, su impacto se limita al código que usa parámetros con nombre para invocar métodos en el tipo de flujo derivado usando una variable de tipo como ese tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="f5d82-120">For source code, its impact is limited to code that uses named parameters to invoke methods on the derived stream type using a variable typed as that derived type.</span></span>

<span data-ttu-id="f5d82-121">En ambos casos, la acción recomendada es usar el nombre de parámetro base de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="f5d82-121">In both cases, the recommended action is to consistently use the base parameter name.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f5d82-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f5d82-122">Affected APIs</span></span>

- <xref:System.IO.BufferedStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.BufferedStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.FileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.FileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.FileStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.FileStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.IO.Compression.DeflateStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.DeflateStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.DeflateStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.DeflateStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.GZipStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.GZipStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.GZipStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.GZipStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.GZipStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.GZipStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.BufferedStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.BufferedStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.FileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.FileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.FileStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.FileStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.Net.Sockets.NetworkStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.Net.Sockets.NetworkStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.Net.Sockets.NetworkStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`

-->
