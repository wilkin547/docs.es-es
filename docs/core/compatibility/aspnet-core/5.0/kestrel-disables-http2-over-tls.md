---
title: 'Cambio importante: Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: befd393795f3e1859d391bca513dd9856101d295
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760220"
---
# <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a><span data-ttu-id="54487-103">Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles</span><span class="sxs-lookup"><span data-stu-id="54487-103">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>

<span data-ttu-id="54487-104">Para habilitar HTTP/2 sobre TLS (Seguridad de la capa de transporte) en Windows, deben cumplirse dos requisitos:</span><span class="sxs-lookup"><span data-stu-id="54487-104">To enable HTTP/2 over Transport Layer Security (TLS) on Windows, two requirements need to be met:</span></span>

- <span data-ttu-id="54487-105">Compatibilidad con ALPN (Negociación de protocolo de capa de aplicación), disponible a partir de Windows 8.1 y Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="54487-105">Application-Layer Protocol Negotiation (ALPN) support, which is available starting with Windows 8.1 and Windows Server 2012 R2.</span></span>
- <span data-ttu-id="54487-106">Un conjunto de cifrados compatible con HTTP/2, disponible a partir de Windows 10 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="54487-106">A set of ciphers compatible with HTTP/2, which is available starting with Windows 10 and Windows Server 2016.</span></span>

<span data-ttu-id="54487-107">De este modo, el comportamiento de Kestrel cuando se configura HTTP/2 sobre TLS ha cambiado a:</span><span class="sxs-lookup"><span data-stu-id="54487-107">As such, Kestrel's behavior when HTTP/2 over TLS is configured has changed to:</span></span>

- <span data-ttu-id="54487-108">Cambio a la versión anterior `Http1` y registro de un mensaje en el nivel `Information` cuando [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) está establecido en `Http1AndHttp2`.</span><span class="sxs-lookup"><span data-stu-id="54487-108">Downgrade to `Http1` and log a message at the `Information` level when [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) is set to `Http1AndHttp2`.</span></span> <span data-ttu-id="54487-109">`Http1AndHttp2` es el valor predeterminado en `ListenOptions.HttpProtocols`.</span><span class="sxs-lookup"><span data-stu-id="54487-109">`Http1AndHttp2` is the default value for `ListenOptions.HttpProtocols`.</span></span>
- <span data-ttu-id="54487-110">Inicio de `NotSupportedException` cuando `ListenOptions.HttpProtocols` está establecido en `Http2`.</span><span class="sxs-lookup"><span data-stu-id="54487-110">Throw a `NotSupportedException` when `ListenOptions.HttpProtocols` is set to `Http2`.</span></span>

<span data-ttu-id="54487-111">Para obtener información, vea el tema [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).</span><span class="sxs-lookup"><span data-stu-id="54487-111">For discussion, see issue [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="54487-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="54487-112">Version introduced</span></span>

<span data-ttu-id="54487-113">ASP.NET Core 5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="54487-113">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="54487-114">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="54487-114">Old behavior</span></span>

<span data-ttu-id="54487-115">En la tabla siguiente se describe el comportamiento cuando se configura HTTP/2 sobre TLS.</span><span class="sxs-lookup"><span data-stu-id="54487-115">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="54487-116">Protocolos</span><span class="sxs-lookup"><span data-stu-id="54487-116">Protocols</span></span> | <span data-ttu-id="54487-117">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="54487-117">Windows 7,</span></span><br /><span data-ttu-id="54487-118">Windows Server 2008 R2,</span><span class="sxs-lookup"><span data-stu-id="54487-118">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="54487-119">o versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="54487-119">or earlier</span></span> | <span data-ttu-id="54487-120">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="54487-120">Windows 8,</span></span><br /><span data-ttu-id="54487-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="54487-121">Windows Server 2012</span></span> | <span data-ttu-id="54487-122">Windows 8.1,</span><span class="sxs-lookup"><span data-stu-id="54487-122">Windows 8.1,</span></span><br /><span data-ttu-id="54487-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="54487-123">Windows Server 2012 R2</span></span> | <span data-ttu-id="54487-124">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="54487-124">Windows 10,</span></span><br /><span data-ttu-id="54487-125">Windows Server 2016,</span><span class="sxs-lookup"><span data-stu-id="54487-125">Windows Server 2016,</span></span><br /><span data-ttu-id="54487-126">o versiones más recientes</span><span class="sxs-lookup"><span data-stu-id="54487-126">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="54487-127">Inicio de `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="54487-127">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="54487-128">Error durante el protocolo de enlace TLS</span><span class="sxs-lookup"><span data-stu-id="54487-128">Error during TLS handshake</span></span>     | <span data-ttu-id="54487-129">Error durante el protocolo de enlace TLS &ast;</span><span class="sxs-lookup"><span data-stu-id="54487-129">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="54487-130">Sin errores</span><span class="sxs-lookup"><span data-stu-id="54487-130">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="54487-131">Cambio a la versión anterior `Http1`</span><span class="sxs-lookup"><span data-stu-id="54487-131">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="54487-132">Cambio a la versión anterior `Http1`</span><span class="sxs-lookup"><span data-stu-id="54487-132">Downgrade to `Http1`</span></span>     | <span data-ttu-id="54487-133">Error durante el protocolo de enlace TLS &ast;</span><span class="sxs-lookup"><span data-stu-id="54487-133">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="54487-134">Sin errores</span><span class="sxs-lookup"><span data-stu-id="54487-134">No error</span></span> |

<span data-ttu-id="54487-135">&ast; Configure los conjuntos de cifrado compatibles para habilitar estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="54487-135">&ast; Configure compatible cipher suites to enable these scenarios.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="54487-136">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="54487-136">New behavior</span></span>

<span data-ttu-id="54487-137">En la tabla siguiente se describe el comportamiento cuando se configura HTTP/2 sobre TLS.</span><span class="sxs-lookup"><span data-stu-id="54487-137">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="54487-138">Protocolos</span><span class="sxs-lookup"><span data-stu-id="54487-138">Protocols</span></span> | <span data-ttu-id="54487-139">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="54487-139">Windows 7,</span></span><br /><span data-ttu-id="54487-140">Windows Server 2008 R2,</span><span class="sxs-lookup"><span data-stu-id="54487-140">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="54487-141">o versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="54487-141">or earlier</span></span> | <span data-ttu-id="54487-142">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="54487-142">Windows 8,</span></span><br /><span data-ttu-id="54487-143">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="54487-143">Windows Server 2012</span></span> | <span data-ttu-id="54487-144">Windows 8.1,</span><span class="sxs-lookup"><span data-stu-id="54487-144">Windows 8.1,</span></span><br /><span data-ttu-id="54487-145">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="54487-145">Windows Server 2012 R2</span></span> | <span data-ttu-id="54487-146">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="54487-146">Windows 10,</span></span><br /><span data-ttu-id="54487-147">Windows Server 2016,</span><span class="sxs-lookup"><span data-stu-id="54487-147">Windows Server 2016,</span></span><br /><span data-ttu-id="54487-148">o versiones más recientes</span><span class="sxs-lookup"><span data-stu-id="54487-148">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="54487-149">Inicio de `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="54487-149">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="54487-150">Inicio de `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="54487-150">Throw `NotSupportedException`</span></span>     | <span data-ttu-id="54487-151">Inicio de `NotSupportedException` &ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="54487-151">Throw `NotSupportedException` &ast;&ast;</span></span>     | <span data-ttu-id="54487-152">Sin errores</span><span class="sxs-lookup"><span data-stu-id="54487-152">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="54487-153">Cambio a la versión anterior `Http1`</span><span class="sxs-lookup"><span data-stu-id="54487-153">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="54487-154">Cambio a la versión anterior `Http1`</span><span class="sxs-lookup"><span data-stu-id="54487-154">Downgrade to `Http1`</span></span>     | <span data-ttu-id="54487-155">Cambio a la versión anterior `Http1` &ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="54487-155">Downgrade to `Http1` &ast;&ast;</span></span>     | <span data-ttu-id="54487-156">Sin errores</span><span class="sxs-lookup"><span data-stu-id="54487-156">No error</span></span> |

<span data-ttu-id="54487-157">&ast;&ast; Configure los conjuntos de cifrado compatibles y establezca el cambio de contexto de la aplicación `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` en `true` para habilitar estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="54487-157">&ast;&ast; Configure compatible cipher suites and set the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` to `true` to enable these scenarios.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="54487-158">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="54487-158">Reason for change</span></span>

<span data-ttu-id="54487-159">Con este cambio, se garantiza que los errores de compatibilidad de HTTP/2 sobre TLS en versiones anteriores de Windows se detectan con la mayor claridad y rapidez posible.</span><span class="sxs-lookup"><span data-stu-id="54487-159">This change ensures compatibility errors for HTTP/2 over TLS on older Windows versions are surfaced as early and as clearly as possible.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="54487-160">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="54487-160">Recommended action</span></span>

<span data-ttu-id="54487-161">Asegúrese de que HTTP/2 sobre TLS esté deshabilitado en versiones de Windows incompatibles.</span><span class="sxs-lookup"><span data-stu-id="54487-161">Ensure HTTP/2 over TLS is disabled on incompatible Windows versions.</span></span> <span data-ttu-id="54487-162">Windows 8.1 y Windows Server 2012 R2 son incompatibles, puesto que carecen de los cifrados necesarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54487-162">Windows 8.1 and Windows Server 2012 R2 are incompatible since they lack the necessary ciphers by default.</span></span> <span data-ttu-id="54487-163">No obstante, es posible modificar los valores de configuración del equipo para que se usen cifrados compatibles con HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="54487-163">However, it's possible to update the Computer Configuration settings to use HTTP/2 compatible ciphers.</span></span> <span data-ttu-id="54487-164">Para obtener más información, vea [Conjuntos de cifrado TLS en Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span><span class="sxs-lookup"><span data-stu-id="54487-164">For more information, see [TLS cipher suites in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span></span> <span data-ttu-id="54487-165">Una vez configurado, se debe establecer el cambio de contexto de la aplicación `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` para habilitar HTTP/2 sobre TLS en Kestrel.</span><span class="sxs-lookup"><span data-stu-id="54487-165">Once configured, HTTP/2 over TLS on Kestrel must be enabled by setting the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`.</span></span> <span data-ttu-id="54487-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="54487-166">For example:</span></span>

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

<span data-ttu-id="54487-167">La compatibilidad subyacente no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="54487-167">No underlying support has changed.</span></span> <span data-ttu-id="54487-168">Por ejemplo, HTTP/2 sobre TLS nunca ha funcionado en Windows 8 ni Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="54487-168">For example, HTTP/2 over TLS has never worked on Windows 8 or Windows Server 2012.</span></span> <span data-ttu-id="54487-169">Este cambio modifica el modo en el que se presentan los errores en estos escenarios no admitidos.</span><span class="sxs-lookup"><span data-stu-id="54487-169">This change modifies how errors in these unsupported scenarios are presented.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="54487-170">API afectadas</span><span class="sxs-lookup"><span data-stu-id="54487-170">Affected APIs</span></span>

<span data-ttu-id="54487-171">None</span><span class="sxs-lookup"><span data-stu-id="54487-171">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
