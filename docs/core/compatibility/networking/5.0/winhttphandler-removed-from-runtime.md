---
title: 'Cambio importante: WinHttpHandler quitado del entorno de ejecución de .NET'
description: Obtenga información sobre el cambio importante en .NET 5, donde WinHttpHandler se ha quitado del entorno de ejecución de .NET.
ms.date: 10/18/2020
ms.openlocfilehash: 95abcfb4d7670be035bd640dbb85458406c1b0e0
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256418"
---
# <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="81a90-103">WinHttpHandler quitado del entorno de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="81a90-103">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="81a90-104">La clase `WinHttpHandler` se ha quitado del ensamblado *System.Net.Http.dll*.</span><span class="sxs-lookup"><span data-stu-id="81a90-104">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="81a90-105">Ahora solo está disponible como un [paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="81a90-105">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="81a90-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="81a90-106">Version introduced</span></span>

<span data-ttu-id="81a90-107">5.0</span><span class="sxs-lookup"><span data-stu-id="81a90-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="81a90-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="81a90-108">Change description</span></span>

<span data-ttu-id="81a90-109">En versiones anteriores de .NET, la clase <xref:System.Net.Http.WinHttpHandler> está disponible como parte de las bibliotecas básicas de .NET.</span><span class="sxs-lookup"><span data-stu-id="81a90-109">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="81a90-110">A partir de .NET 5, la clase <xref:System.Net.Http.WinHttpHandler> solo está disponible como un [paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) instalado por separado.</span><span class="sxs-lookup"><span data-stu-id="81a90-110">Starting in .NET 5, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="81a90-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="81a90-111">Recommended action</span></span>

<span data-ttu-id="81a90-112">Instale el [paquete NuGet System.Net.Http.WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="81a90-112">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="81a90-113">O bien, si no necesita características específicas de WinHTTP, use <xref:System.Net.Http.SocketsHttpHandler> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="81a90-113">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="81a90-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="81a90-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
