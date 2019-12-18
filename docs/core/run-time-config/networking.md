---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998838"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="a80e4-103">Opciones de configuración del entorno de ejecución para las redes</span><span class="sxs-lookup"><span data-stu-id="a80e4-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="a80e4-104">Protocolo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a80e4-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="a80e4-105">Configura si está habilitada la compatibilidad con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="a80e4-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="a80e4-106">Predeterminado: deshabilitado (`false`).</span><span class="sxs-lookup"><span data-stu-id="a80e4-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="a80e4-107">Introducido en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a80e4-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="a80e4-108">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="a80e4-108">Setting name</span></span> | <span data-ttu-id="a80e4-109">Valores</span><span class="sxs-lookup"><span data-stu-id="a80e4-109">Values</span></span> |
| - | - |
| <span data-ttu-id="a80e4-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a80e4-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="a80e4-111">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a80e4-111">`false` - disabled</span></span><br/><span data-ttu-id="a80e4-112">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="a80e4-112">`true` - enabled</span></span> |
| <span data-ttu-id="a80e4-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="a80e4-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="a80e4-114">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a80e4-114">`0` - disabled</span></span><br/><span data-ttu-id="a80e4-115">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="a80e4-115">`1` - enabled</span></span> |

## <a name="sockets-http-handler"></a><span data-ttu-id="a80e4-116">Controlador HTTP de sockets</span><span class="sxs-lookup"><span data-stu-id="a80e4-116">Sockets HTTP handler</span></span>

- <span data-ttu-id="a80e4-117">Configura si las API de redes de alto nivel, como <xref:System.Net.Http.HttpClient>, usan <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o la implementación de <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> basada en [libcurl](https://curl.haxx.se/libcurl/).</span><span class="sxs-lookup"><span data-stu-id="a80e4-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="a80e4-118">Predeterminado: usar <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span><span class="sxs-lookup"><span data-stu-id="a80e4-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="a80e4-119">Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a80e4-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="a80e4-120">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="a80e4-120">Setting name</span></span> | <span data-ttu-id="a80e4-121">Valores</span><span class="sxs-lookup"><span data-stu-id="a80e4-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a80e4-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a80e4-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="a80e4-123">`true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="a80e4-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a80e4-124">`false`: habilita el uso de <xref:System.Net.Http.HttpClientHandler>.</span><span class="sxs-lookup"><span data-stu-id="a80e4-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="a80e4-125">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="a80e4-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="a80e4-126">`1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="a80e4-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a80e4-127">`0`: habilita el uso de <xref:System.Net.Http.HttpClientHandler>.</span><span class="sxs-lookup"><span data-stu-id="a80e4-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
