---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6b5e03b127f95911b712b66c0be8a4f5a2929fc2
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761946"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="7d09f-103">Opciones de configuración del entorno de ejecución para las redes</span><span class="sxs-lookup"><span data-stu-id="7d09f-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="7d09f-104">Protocolo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="7d09f-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="7d09f-105">Configura si está habilitada la compatibilidad con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="7d09f-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="7d09f-106">Si se omite esta configuración, la compatibilidad con el protocolo HTTP/2 está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7d09f-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="7d09f-107">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="7d09f-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="7d09f-108">Introducido en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="7d09f-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="7d09f-109">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="7d09f-109">Setting name</span></span> | <span data-ttu-id="7d09f-110">Valores</span><span class="sxs-lookup"><span data-stu-id="7d09f-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7d09f-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7d09f-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="7d09f-112">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="7d09f-112">`false` - disabled</span></span><br/><span data-ttu-id="7d09f-113">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="7d09f-113">`true` - enabled</span></span> |
| <span data-ttu-id="7d09f-114">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="7d09f-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="7d09f-115">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="7d09f-115">`0` - disabled</span></span><br/><span data-ttu-id="7d09f-116">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="7d09f-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="7d09f-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="7d09f-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="7d09f-118">Configura si <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> usa <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o pilas de protocolo HTTP anteriores (<xref:System.Net.Http.WinHttpHandler> en Windows y `CurlHandler`, una clase interna implementada sobre [libcurl](https://curl.haxx.se/libcurl/), en Linux).</span><span class="sxs-lookup"><span data-stu-id="7d09f-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="7d09f-119">Es posible que esté usando las API para redes de alto nivel en lugar de crear directamente instancias de la clase <xref:System.Net.Http.HttpClientHandler>.</span><span class="sxs-lookup"><span data-stu-id="7d09f-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="7d09f-120">Este valor también afecta a la pila del protocolo HTTP que usan las API para redes de alto nivel, como <xref:System.Net.Http.HttpClient> y [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span><span class="sxs-lookup"><span data-stu-id="7d09f-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="7d09f-121">Si se omite este valor, <xref:System.Net.Http.HttpClientHandler> utiliza <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="7d09f-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="7d09f-122">Esto es equivalente a establecer el valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="7d09f-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="7d09f-123">Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d09f-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="7d09f-124">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="7d09f-124">Setting name</span></span> | <span data-ttu-id="7d09f-125">Valores</span><span class="sxs-lookup"><span data-stu-id="7d09f-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7d09f-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7d09f-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="7d09f-127">`true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="7d09f-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="7d09f-128">`false`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux</span><span class="sxs-lookup"><span data-stu-id="7d09f-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="7d09f-129">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="7d09f-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="7d09f-130">`1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="7d09f-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="7d09f-131">`0`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux</span><span class="sxs-lookup"><span data-stu-id="7d09f-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="7d09f-132">A partir de .NET 5, la configuración `System.Net.Http.UseSocketsHttpHandler` ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="7d09f-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
