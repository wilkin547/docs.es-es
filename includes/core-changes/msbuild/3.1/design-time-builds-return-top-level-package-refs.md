---
ms.openlocfilehash: 53840ddd59ae3463bae2930fd0151ab2cd2d65cb
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593335"
---
### <a name="design-time-builds-only-return-top-level-package-references"></a>Las compilaciones en tiempo de diseño solo devuelven referencias de paquete de nivel superior

A partir del SDK de .NET Core 3.1.400, el destino de `RunResolvePackageDependencies` solo devuelve las referencias de paquete de nivel superior.

#### <a name="version-introduced"></a>Versión introducida

SDK 3.1.400 de .NET Core

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores del SDK de .NET Core, el destino `RunResolvePackageDependencies` creó los siguientes elementos de MSBuild que contenían información del archivo de recursos de NuGet:

- `PackageDefinitions`
- `PackageDependencies`
- `TargetDefinitions`
- `FileDefinitions`
- `FileDependencies`

Visual Studio usa estos datos para rellenar el nodo Dependencias en el explorador de soluciones, pero puede ser una gran cantidad de datos y estos no son necesarios a menos que se expanda el nodo Dependencias.

A partir de la versión 3.1.400 del SDK de .NET Core, la mayoría de estos elementos no se generan de forma predeterminada. Solo se devuelven los elementos de tipo `Package`. Si Visual Studio necesita que los elementos rellenen el nodo dependencias, lee la información directamente del archivo de recursos.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio se presentó para mejorar el rendimiento de carga de la solución dentro de Visual Studio. Anteriormente, todas las referencias de paquete se cargaban, lo que implicaba la carga de muchas referencias que la mayoría de los usuarios nunca veían.

#### <a name="recommended-action"></a>Acción recomendada

Si tiene lógica de MSBuild que depende de la creación de estos elementos, establezca la propiedad `EmitLegacyAssetsFileItems` en `true` en el archivo del proyecto. Esta configuración habilita el comportamiento anterior en el que se crean todos los elementos.

#### <a name="category"></a>Categoría

MSBuild

#### <a name="affected-apis"></a>API afectadas

N/D
