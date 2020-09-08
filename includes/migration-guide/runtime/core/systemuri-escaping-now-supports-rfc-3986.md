---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496981"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="aea8b-101">La aplicación de secuencias de escape de System.Uri ahora es compatible con RFC 3986</span><span class="sxs-lookup"><span data-stu-id="aea8b-101">System.Uri escaping now supports RFC 3986</span></span>

#### <a name="details"></a><span data-ttu-id="aea8b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="aea8b-102">Details</span></span>

<span data-ttu-id="aea8b-103">La aplicación de secuencias de escape a los URI se ha modificado en .NET Framework 4.5 para que sea compatible con [RFC 3986](https://tools.ietf.org/html/rfc3986).</span><span class="sxs-lookup"><span data-stu-id="aea8b-103">URI escaping has changed in .NET Framework 4.5 to support [RFC 3986](https://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="aea8b-104">Cambios concretos:</span><span class="sxs-lookup"><span data-stu-id="aea8b-104">Specific changes include:</span></span><ul><li><span data-ttu-id="aea8b-105">El método <xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> incluye los caracteres reservados entre caracteres de escape de con arreglo a RFC 3986.</span><span class="sxs-lookup"><span data-stu-id="aea8b-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="aea8b-106">El método <xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> no incluye entre caracteres de escape los caracteres reservados.</span><span class="sxs-lookup"><span data-stu-id="aea8b-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> does not escape reserved characters.</span></span></li><li><span data-ttu-id="aea8b-107">El método <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> no inicia una excepción si encuentra una secuencia de escape no válida.</span><span class="sxs-lookup"><span data-stu-id="aea8b-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="aea8b-108">Los caracteres de escape no reservados no se incluyen en una secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="aea8b-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="aea8b-109">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="aea8b-109">Suggestion</span></span>

<ul><li><span data-ttu-id="aea8b-110">Actualice las aplicaciones para que no se basen en el inicio de <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> en caso de tratarse de secuencias de escape no válidas.</span><span class="sxs-lookup"><span data-stu-id="aea8b-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="aea8b-111">Ahora, este tipo de secuencias deben detectarse directamente.</span><span class="sxs-lookup"><span data-stu-id="aea8b-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="aea8b-112">De igual modo, cabe esperar que los URI y las cadenas de datos con secuencias de escape y sin ellas varíen entre .NET Framework 4.0 y .NET Framework 4.5, y no se deben comparar directamente entre versiones de .NET.</span><span class="sxs-lookup"><span data-stu-id="aea8b-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET Framework 4.0 and .NET Framework 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="aea8b-113">En lugar de ello, deben analizarse y normalizarse en una única versión de .NET antes de efectuar cualquier comparación.</span><span class="sxs-lookup"><span data-stu-id="aea8b-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>

| <span data-ttu-id="aea8b-114">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="aea8b-114">Name</span></span>    | <span data-ttu-id="aea8b-115">Valor</span><span class="sxs-lookup"><span data-stu-id="aea8b-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="aea8b-116">Ámbito</span><span class="sxs-lookup"><span data-stu-id="aea8b-116">Scope</span></span>   |<span data-ttu-id="aea8b-117">Secundaria</span><span class="sxs-lookup"><span data-stu-id="aea8b-117">Minor</span></span>|
|<span data-ttu-id="aea8b-118">Versión</span><span class="sxs-lookup"><span data-stu-id="aea8b-118">Version</span></span>|<span data-ttu-id="aea8b-119">4.5</span><span class="sxs-lookup"><span data-stu-id="aea8b-119">4.5</span></span>|
|<span data-ttu-id="aea8b-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="aea8b-120">Type</span></span>|<span data-ttu-id="aea8b-121">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="aea8b-121">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="aea8b-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="aea8b-122">Affected APIs</span></span>

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
