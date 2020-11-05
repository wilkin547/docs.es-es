---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bda608e83bb1b093d7d9b860de9607f6734720aa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188307"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="a7423-103">Opciones de configuración del entorno de ejecución para las redes</span><span class="sxs-lookup"><span data-stu-id="a7423-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="a7423-104">Protocolo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a7423-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="a7423-105">Configura si está habilitada la compatibilidad con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="a7423-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="a7423-106">Introducido en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a7423-106">Introduced in .NET Core 3.0.</span></span>

- <span data-ttu-id="a7423-107">Solo para .NET Core 3.0: Si se omite esta configuración, la compatibilidad con el protocolo HTTP/2 está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a7423-107">.NET Core 3.0 only: If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="a7423-108">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="a7423-108">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="a7423-109">.NET Core 3.1, y .NET 5 y versiones posteriores: si se omite esta configuración, se habilita la compatibilidad con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="a7423-109">.NET Core 3.1 and .NET 5+: If you omit this setting, support for the HTTP/2 protocol is enabled.</span></span> <span data-ttu-id="a7423-110">Esto es equivalente a establecer el valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="a7423-110">This is equivalent to setting the value to `true`.</span></span>

| | <span data-ttu-id="a7423-111">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="a7423-111">Setting name</span></span> | <span data-ttu-id="a7423-112">Valores</span><span class="sxs-lookup"><span data-stu-id="a7423-112">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a7423-113">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a7423-113">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="a7423-114">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-114">`false` - disabled</span></span><br/><span data-ttu-id="a7423-115">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-115">`true` - enabled</span></span> |
| <span data-ttu-id="a7423-116">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="a7423-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="a7423-117">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-117">`0` - disabled</span></span><br/><span data-ttu-id="a7423-118">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-118">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="a7423-119">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="a7423-119">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="a7423-120">Configura si <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> usa <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o pilas de protocolo HTTP anteriores (<xref:System.Net.Http.WinHttpHandler> en Windows y `CurlHandler`, una clase interna implementada sobre [libcurl](https://curl.haxx.se/libcurl/), en Linux).</span><span class="sxs-lookup"><span data-stu-id="a7423-120">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a7423-121">Es posible que esté usando las API para redes de alto nivel en lugar de crear directamente instancias de la clase <xref:System.Net.Http.HttpClientHandler>.</span><span class="sxs-lookup"><span data-stu-id="a7423-121">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="a7423-122">Este valor también afecta a la pila del protocolo HTTP que usan las API para redes de alto nivel, como <xref:System.Net.Http.HttpClient> y [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span><span class="sxs-lookup"><span data-stu-id="a7423-122">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="a7423-123">Si se omite este valor, <xref:System.Net.Http.HttpClientHandler> utiliza <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="a7423-123">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="a7423-124">Esto es equivalente a establecer el valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="a7423-124">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="a7423-125">Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a7423-125">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="a7423-126">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="a7423-126">Setting name</span></span> | <span data-ttu-id="a7423-127">Valores</span><span class="sxs-lookup"><span data-stu-id="a7423-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a7423-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a7423-128">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="a7423-129">`true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="a7423-129">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a7423-130">`false`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux</span><span class="sxs-lookup"><span data-stu-id="a7423-130">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="a7423-131">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="a7423-131">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="a7423-132">`1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="a7423-132">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a7423-133">`0`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux</span><span class="sxs-lookup"><span data-stu-id="a7423-133">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="a7423-134">A partir de .NET 5, la configuración `System.Net.Http.UseSocketsHttpHandler` ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="a7423-134">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>

## <a name="latin1-headers-net-core-31-only"></a><span data-ttu-id="a7423-135">Encabezados Latin1 (solo .NET Core 3.1)</span><span class="sxs-lookup"><span data-stu-id="a7423-135">Latin1 headers (.NET Core 3.1 only)</span></span>

- <span data-ttu-id="a7423-136">Este modificador permite relajar la validación de encabezados HTTP y habilita <xref:System.Net.Http.SocketsHttpHandler> para enviar caracteres codificados mediante ISO-8859-1 (Latin-1) en los encabezados.</span><span class="sxs-lookup"><span data-stu-id="a7423-136">This switch allows relaxing the HTTP header validation, enabling <xref:System.Net.Http.SocketsHttpHandler> to send ISO-8859-1 (Latin-1) encoded characters in headers.</span></span>

- <span data-ttu-id="a7423-137">Si se omite esta configuración, un intento de enviar un carácter que no sea ASCII iniciará una excepción <xref:System.Net.Http.HttpRequestException>.</span><span class="sxs-lookup"><span data-stu-id="a7423-137">If you omit this setting, an attempt to send a non-ASCII character will result in <xref:System.Net.Http.HttpRequestException>.</span></span> <span data-ttu-id="a7423-138">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="a7423-138">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="a7423-139">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="a7423-139">Setting name</span></span> | <span data-ttu-id="a7423-140">Valores</span><span class="sxs-lookup"><span data-stu-id="a7423-140">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a7423-141">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a7423-141">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | <span data-ttu-id="a7423-142">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-142">`false` - disabled</span></span><br/><span data-ttu-id="a7423-143">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-143">`true` - enabled</span></span> |
| <span data-ttu-id="a7423-144">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="a7423-144">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | <span data-ttu-id="a7423-145">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-145">`0` - disabled</span></span><br/><span data-ttu-id="a7423-146">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="a7423-146">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="a7423-147">Esta opción solo está disponible en .NET Core 3.1 desde la versión 3.1.9, y no en versiones anteriores o posteriores.</span><span class="sxs-lookup"><span data-stu-id="a7423-147">This option is only available in .NET Core 3.1 since version 3.1.9, and not in previous or later versions.</span></span> <span data-ttu-id="a7423-148">En .NET 5 se recomienda usar <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span><span class="sxs-lookup"><span data-stu-id="a7423-148">In .NET 5 we recommend using <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span></span>
