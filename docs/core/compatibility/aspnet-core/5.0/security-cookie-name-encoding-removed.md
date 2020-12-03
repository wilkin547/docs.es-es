---
title: 'Cambio importante: Seguridad: Se ha quitado la codificación de nombre de cookie'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Seguridad: Se ha quitado la codificación de nombre de cookie'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 3cd40d2b04d0cdf0863e3a3fb6d790c2b35692bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760270"
---
# <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="06e22-103">Seguridad: Se ha quitado la codificación de nombre de cookie</span><span class="sxs-lookup"><span data-stu-id="06e22-103">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="06e22-104">El [estándar de cookies de HTTP](https://tools.ietf.org/html/rfc6265#section-4.1.1) solo permite caracteres específicos en nombres y valores de cookies.</span><span class="sxs-lookup"><span data-stu-id="06e22-104">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="06e22-105">Para admitir caracteres no permitidos, ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="06e22-105">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="06e22-106">Codifica cuando se crea una cookie de respuesta.</span><span class="sxs-lookup"><span data-stu-id="06e22-106">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="06e22-107">Descodifica cuando se crea una cookie de solicitud.</span><span class="sxs-lookup"><span data-stu-id="06e22-107">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="06e22-108">En ASP.NET Core 5.0, este comportamiento de codificación ha cambiado en respuesta a un problema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="06e22-108">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="06e22-109">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span><span class="sxs-lookup"><span data-stu-id="06e22-109">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="06e22-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="06e22-110">Version introduced</span></span>

<span data-ttu-id="06e22-111">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="06e22-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="06e22-112">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="06e22-112">Old behavior</span></span>

<span data-ttu-id="06e22-113">Se codifican los nombres de las cookies de respuesta.</span><span class="sxs-lookup"><span data-stu-id="06e22-113">Response cookie names are encoded.</span></span> <span data-ttu-id="06e22-114">Se descodifican los nombres de las cookies de solicitud.</span><span class="sxs-lookup"><span data-stu-id="06e22-114">Request cookie names are decoded.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="06e22-115">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="06e22-115">New behavior</span></span>

<span data-ttu-id="06e22-116">Se ha quitado la codificación y descodificación de los nombres de cookies.</span><span class="sxs-lookup"><span data-stu-id="06e22-116">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="06e22-117">En el caso de las [versiones compatibles](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) de ASP.NET Core anteriores, el equipo planea mitigar el problema de descodificación en contexto.</span><span class="sxs-lookup"><span data-stu-id="06e22-117">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="06e22-118">Además, al llamar a <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> con un nombre de cookie no válido se inicia una excepción de tipo <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="06e22-118">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="06e22-119">La codificación y la descodificación de valores de cookies permanecen sin cambios.</span><span class="sxs-lookup"><span data-stu-id="06e22-119">Encoding and decoding of cookie values remains unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="06e22-120">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="06e22-120">Reason for change</span></span>

<span data-ttu-id="06e22-121">Se ha detectado un problema en [varios marcos web](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span><span class="sxs-lookup"><span data-stu-id="06e22-121">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="06e22-122">La codificación y la descodificación podrían permitir que un atacante omita una característica de seguridad llamada [prefijos de cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) mediante la suplantación de prefijos reservados como `__Host-` con valores codificados como `__%48ost-`.</span><span class="sxs-lookup"><span data-stu-id="06e22-122">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="06e22-123">El ataque requiere que una vulnerabilidad de seguridad inserte las cookies suplantadas, como una vulnerabilidad de scripts entre sitios (XSS), en el sitio web.</span><span class="sxs-lookup"><span data-stu-id="06e22-123">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="06e22-124">Estos prefijos no se usan de forma predeterminada en ASP.NET Core ni en las bibliotecas o plantillas de `Microsoft.Owin`.</span><span class="sxs-lookup"><span data-stu-id="06e22-124">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="06e22-125">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="06e22-125">Recommended action</span></span>

<span data-ttu-id="06e22-126">Si va a mover proyectos a ASP.NET Core 5.0 o una versión posterior, asegúrese de que los nombres de las cookies cumplen los [requisitos de especificación de tokens](https://tools.ietf.org/html/rfc2616#section-2.2): Los caracteres ASCII excluyen los controles y separadores `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span><span class="sxs-lookup"><span data-stu-id="06e22-126">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="06e22-127">El uso de caracteres que no son ASCII en los nombres de cookies u otros encabezados HTTP puede producir una excepción del servidor o que el cliente pueda realizar una acción inadecuada de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="06e22-127">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="06e22-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="06e22-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
