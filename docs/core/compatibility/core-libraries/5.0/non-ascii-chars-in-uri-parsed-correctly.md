---
title: 'Cambio importante: Rutas de acceso de URI con caracteres que no son ASCII se analizan correctamente en UNIX'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII ahora se analizan correctamente en plataformas Unix.
ms.date: 11/01/2020
ms.openlocfilehash: 94de4e0eb94a11153d873871d4003422a4286a0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760112"
---
# <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a>Rutas de acceso de URI con caracteres que no son ASCII se analizan correctamente en UNIX

Se ha corregido un error de la clase <xref:System.Uri?displayProperty=fullName>, de modo que las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII ahora se analizan correctamente en plataformas UNIX.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII se analizan incorrectamente en plataformas UNIX y los segmentos de la ruta de acceso están duplicados. (Las rutas de acceso absolutas son las que empiezan por "/"). El problema de análisis se ha solucionado para .NET 5.0. Si pasa de una versión anterior de .NET a .NET 5.0 u otra posterior, obtendrá valores diferentes generados por <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType> y otros miembros de <xref:System.Uri>.

Tenga en cuenta el resultado de este código cuando se ejecute en UNIX.

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

Resultado en la versión anterior de .NET:

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

Resultado en .NET 5.0 u otra versión posterior:

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Si tiene código que espera segmentos de ruta de acceso duplicados y los tiene en cuenta, puede quitar ese código.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Uri?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
