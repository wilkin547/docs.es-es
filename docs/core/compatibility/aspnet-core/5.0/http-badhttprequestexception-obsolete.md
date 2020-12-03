---
title: 'Cambio importante: HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760160"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a>HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` se han marcado como obsoletos y se han cambiado para que deriven de `Microsoft.AspNetCore.Http.BadHttpRequestException`. Los servidores de Kestrel e IIS siguen produciendo los tipos de excepción antiguos para garantizar la compatibilidad con versiones anteriores. Los tipos obsoletos se quitarán en una versión futura.

Para obtener información, vea [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 4)

## <a name="old-behavior"></a>Comportamiento anterior

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derivaban de <xref:System.IO.IOException?displayProperty=nameWithType>.

## <a name="new-behavior"></a>Comportamiento nuevo

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` están obsoletos. Los tipos también derivan de `Microsoft.AspNetCore.Http.BadHttpRequestException`, que deriva de `System.IO.IOException`.

## <a name="reason-for-change"></a>Motivo del cambio

El cambio se ha realizado para:

* Consolidar los tipos duplicados.
* Unificar el comportamiento en las implementaciones de servidor.

Ahora, una aplicación puede detectar la excepción base `Microsoft.AspNetCore.Http.BadHttpRequestException` cuando se usa Kestrel o IIS.

## <a name="recommended-action"></a>Acción recomendada

Reemplace los usos de `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` y `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` por `Microsoft.AspNetCore.Http.BadHttpRequestException`.

## <a name="affected-apis"></a>API afectadas

- [Microsoft.AspNetCore.Server.IIS.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
