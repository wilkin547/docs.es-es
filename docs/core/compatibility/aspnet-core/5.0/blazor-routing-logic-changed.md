---
title: 'Cambio importante: Blazor: Cambios en la lógica de enrutamiento en aplicaciones Blazor'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Cambios en la lógica de enrutamiento en aplicaciones Blazor'
author: scottaddie
ms.author: scaddie
ms.date: 12/14/2020
ms.openlocfilehash: 4ab8289565c88b17eb204a11724bb12a09b033c2
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513512"
---
# <a name="blazor-route-precedence-logic-changed-in-blazor-apps"></a>Blazor: Lógica de precedencia de ruta cambiada en aplicaciones Blazor

Un error en la implementación de enrutamiento de Blazor afectaba al modo en que se determinaba la prioridad de las rutas. Este error afectaba a las rutas de captura general o a las rutas con parámetros opcionales dentro de la aplicación Blazor.

## <a name="version-introduced"></a>Versión introducida

5.0.1

## <a name="old-behavior"></a>Comportamiento anterior

Con el comportamiento erróneo, se tenían en cuenta primero las rutas con menor prioridad y se hacían coincidir antes que las rutas con mayor prioridad. Por ejemplo, la ruta `{*slug}` se hacía coincidir antes que la ruta `/customer/{id}`.

## <a name="new-behavior"></a>Comportamiento nuevo

El comportamiento actual coincide más estrechamente con el comportamiento de enrutamiento definido en las aplicaciones de ASP.NET Core. El marco determina primero la prioridad de la ruta para cada segmento. La longitud de la ruta solo se usa como segundo criterio para priorizar en caso de igualdad.

## <a name="reason-for-change"></a>Motivo del cambio

El comportamiento original se considera un error en la implementación. Como objetivo, el sistema de enrutamiento de las aplicaciones Blazor debe comportarse del mismo modo que el sistema de enrutamiento del resto de ASP.NET Core.

## <a name="recommended-action"></a>Acción recomendada

Si actualiza desde versiones anteriores de Blazor a 5.x, use el atributo `PreferExactMatches` en el componente `Router`. Este atributo se puede usar para escoger el comportamiento correcto. Por ejemplo:

```razor
<Router AppAssembly="@typeof(Program).Assembly" PreferExactMatches="true">
```

Cuando `PreferExactMatches` se establece en `true`, la coincidencia de rutas prefiere las coincidencias exactas a los caracteres comodín.

## <a name="affected-apis"></a>API afectadas

None

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
