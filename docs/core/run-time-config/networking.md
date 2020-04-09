---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: f5ea47f0444a911dc2347a66817cabf585fd8e70
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635425"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="2daf1-103">Opciones de configuración del entorno de ejecución para las redes</span><span class="sxs-lookup"><span data-stu-id="2daf1-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="2daf1-104">Protocolo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="2daf1-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="2daf1-105">Configura si está habilitada la compatibilidad con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="2daf1-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="2daf1-106">Predeterminado: deshabilitado (`false`).</span><span class="sxs-lookup"><span data-stu-id="2daf1-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="2daf1-107">Introducido en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2daf1-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="2daf1-108">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="2daf1-108">Setting name</span></span> | <span data-ttu-id="2daf1-109">Valores</span><span class="sxs-lookup"><span data-stu-id="2daf1-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2daf1-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2daf1-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="2daf1-111">`false`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2daf1-111">`false` - disabled</span></span><br/><span data-ttu-id="2daf1-112">`true`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2daf1-112">`true` - enabled</span></span> |
| <span data-ttu-id="2daf1-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="2daf1-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="2daf1-114">`0`: deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2daf1-114">`0` - disabled</span></span><br/><span data-ttu-id="2daf1-115">`1`: habilitado.</span><span class="sxs-lookup"><span data-stu-id="2daf1-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="2daf1-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="2daf1-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="2daf1-117">Configura si las API de redes de alto nivel, como <xref:System.Net.Http.HttpClient>, usan <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o la implementación de <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> basada en [libcurl](https://curl.haxx.se/libcurl/).</span><span class="sxs-lookup"><span data-stu-id="2daf1-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="2daf1-118">Predeterminado: usar <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span><span class="sxs-lookup"><span data-stu-id="2daf1-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="2daf1-119">Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2daf1-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="2daf1-120">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="2daf1-120">Setting name</span></span> | <span data-ttu-id="2daf1-121">Valores</span><span class="sxs-lookup"><span data-stu-id="2daf1-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="2daf1-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="2daf1-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="2daf1-123">`true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="2daf1-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="2daf1-124">`false`: habilita el uso de <xref:System.Net.Http.HttpClientHandler>.</span><span class="sxs-lookup"><span data-stu-id="2daf1-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="2daf1-125">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="2daf1-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="2daf1-126">`1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="2daf1-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="2daf1-127">`0`: habilita el uso de <xref:System.Net.Http.HttpClientHandler>.</span><span class="sxs-lookup"><span data-stu-id="2daf1-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |

> [!NOTE]
> <span data-ttu-id="2daf1-128">A partir de .NET 5, la configuración `System.Net.Http.UseSocketsHttpHandler` ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2daf1-128">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
