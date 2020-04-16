---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989108"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="b1e14-103">Opciones de configuración del entorno de ejecución para las redes</span><span class="sxs-lookup"><span data-stu-id="b1e14-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="b1e14-104">Protocolo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="b1e14-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="b1e14-105">Configura si está habilitada la compatibilidad con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="b1e14-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="b1e14-106">Predeterminado: deshabilitado (`false`).</span><span class="sxs-lookup"><span data-stu-id="b1e14-106">Default: Disabled (`false`).</span></span>

- <span data-ttu-id="b1e14-107">Introducido en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b1e14-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="b1e14-108">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="b1e14-108">Setting name</span></span> | <span data-ttu-id="b1e14-109">Valores</span><span class="sxs-lookup"><span data-stu-id="b1e14-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b1e14-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b1e14-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="b1e14-111">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1e14-111">`false` - disabled</span></span><br/><span data-ttu-id="b1e14-112">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="b1e14-112">`true` - enabled</span></span> |
| <span data-ttu-id="b1e14-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="b1e14-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="b1e14-114">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1e14-114">`0` - disabled</span></span><br/><span data-ttu-id="b1e14-115">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="b1e14-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="b1e14-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="b1e14-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="b1e14-117">Configura si <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> usa <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o pilas de protocolo HTTP anteriores (<xref:System.Net.Http.WinHttpHandler> en Windows y `CurlHandler`, una clase interna implementada sobre [libcurl](https://curl.haxx.se/libcurl/), en Linux).</span><span class="sxs-lookup"><span data-stu-id="b1e14-117">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b1e14-118">Es posible que esté usando las API para redes de alto nivel en lugar de crear directamente instancias de la clase <xref:System.Net.Http.HttpClientHandler>.</span><span class="sxs-lookup"><span data-stu-id="b1e14-118">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="b1e14-119">Este valor también afecta a la pila del protocolo HTTP que usan las API para redes de alto nivel, como <xref:System.Net.Http.HttpClient> y [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span><span class="sxs-lookup"><span data-stu-id="b1e14-119">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="b1e14-120">Predeterminado: usar <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span><span class="sxs-lookup"><span data-stu-id="b1e14-120">Default: Use <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span></span>

- <span data-ttu-id="b1e14-121">Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1e14-121">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="b1e14-122">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="b1e14-122">Setting name</span></span> | <span data-ttu-id="b1e14-123">Valores</span><span class="sxs-lookup"><span data-stu-id="b1e14-123">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b1e14-124">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b1e14-124">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="b1e14-125">`true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="b1e14-125">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="b1e14-126">`false`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux</span><span class="sxs-lookup"><span data-stu-id="b1e14-126">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="b1e14-127">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="b1e14-127">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="b1e14-128">`1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="b1e14-128">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="b1e14-129">`0`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux</span><span class="sxs-lookup"><span data-stu-id="b1e14-129">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="b1e14-130">A partir de .NET 5, la configuración `System.Net.Http.UseSocketsHttpHandler` ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b1e14-130">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
