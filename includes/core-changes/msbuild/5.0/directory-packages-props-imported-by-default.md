---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538829"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a>Los archivos Directory.Packages.props se importan de forma predeterminada

Los archivos *.props* de NuGet importan de forma automática un archivo denominado *Directory.Packages.props* si se encuentra en la carpeta del proyecto o en cualquiera de sus antecesores.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, podía tener un archivo con el nombre *Directory.Packages.props* en el archivo del proyecto y el archivo *.props* de NuGet no lo importaría de forma automática en tiempo de compilación.

A partir de .NET 5.0, este tipo de archivo *se importa* automáticamente si existe en la carpeta del proyecto o en cualquiera de sus antecesores. Si tiene un archivo con este nombre en la carpeta del proyecto, esta importación automática podría cambiar el comportamiento de la compilación. Por ejemplo, el archivo no se importaba y ahora se importará, o bien el orden del momento de la importación se podría cambiar si lo importa de forma específica.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio se ha realizado para admitir el [control de versiones de paquetes centrales](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) para NuGet.

#### <a name="recommended-action"></a>Acción recomendada

Cambie el nombre del archivo *Directory.Packages.props* existente si no se debe importar de forma automática.

#### <a name="category"></a>Categoría

MSBuild

#### <a name="affected-apis"></a>API afectadas

N/D

<!--

#### Affected APIs

Not detectable via API analysis.

-->
