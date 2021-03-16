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
# <a name="winhttphandler-removed-from-net-runtime"></a>WinHttpHandler quitado del entorno de ejecución de .NET

La clase `WinHttpHandler` se ha quitado del ensamblado *System.Net.Http.dll*. Ahora solo está disponible como un [paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) fuera de banda (OOB).

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la clase <xref:System.Net.Http.WinHttpHandler> está disponible como parte de las bibliotecas básicas de .NET. A partir de .NET 5, la clase <xref:System.Net.Http.WinHttpHandler> solo está disponible como un [paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) instalado por separado.

## <a name="recommended-action"></a>Acción recomendada

Instale el [paquete NuGet System.Net.Http.WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/). O bien, si no necesita características específicas de WinHTTP, use <xref:System.Net.Http.SocketsHttpHandler> en su lugar.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
