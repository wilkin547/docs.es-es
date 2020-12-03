---
title: 'Cambio importante: IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760098"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a>IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite

Un defecto del middleware de UrlRewrite de IIS impedía que la cadena de consulta se conservase en reglas de reescritura. Ese defecto se ha corregido para mantener la coherencia con el comportamiento del módulo UrlRewrite de IIS.

Para obtener información, vea el tema [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).

## <a name="version-introduced"></a>Versión introducida

ASP.NET Core 5.0 Preview 7

## <a name="old-behavior"></a>Comportamiento anterior

Observe la siguiente regla de reescritura:

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

La regla anterior no anexa la cadena de consulta. Un URI como `/about?id=1` redirige a `/contact` en lugar de a `/contact?id=1`. El valor predeterminado del atributo `appendQueryString` también es `true`.

## <a name="new-behavior"></a>Comportamiento nuevo

La cadena de consulta se mantiene. El URI del ejemplo de [Comportamiento anterior](#old-behavior) sería `/contact?id=1`.

## <a name="reason-for-change"></a>Motivo del cambio

El comportamiento anterior no coincidía con el comportamiento del módulo UrlRewrite de IIS. Para admitir la migración entre el middleware y el módulo, el objetivo es mantener comportamientos coherentes.

## <a name="recommended-action"></a>Acción recomendada

Si se prefiere el comportamiento de eliminación de la cadena de consulta, el elemento `action` debe establecerse en `appendQueryString="false"`.

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
