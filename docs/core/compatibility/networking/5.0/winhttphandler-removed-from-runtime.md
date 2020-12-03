---
title: 'Cambio importante: WinHttpHandler quitado del entorno de ejecución de .NET'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde WinHttpHandler se ha quitado del entorno de ejecución de .NET.
ms.date: 10/18/2020
ms.openlocfilehash: f8b9910ade8d459133791a23704d624a91cc5dff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760141"
---
# <a name="winhttphandler-removed-from-net-runtime"></a>WinHttpHandler quitado del entorno de ejecución de .NET

La clase `WinHttpHandler` se ha quitado del ensamblado *System.Net.Http.dll*. Ahora solo está disponible como un [paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) fuera de banda (OOB).

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la clase <xref:System.Net.Http.WinHttpHandler> está disponible como parte de las bibliotecas básicas de .NET. A partir de .NET 5.0, la clase solo está disponible como un <xref:System.Net.Http.WinHttpHandler>[paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) instalado por separado.

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
