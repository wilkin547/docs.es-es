---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394272"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Almacenamiento en caché: se ha quitado la propiedad CompactOnMemoryPressure

En la versión ASP.NET Core 3.0 se han quitado las [API MemoryCacheOptions](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18) obsoletas.

#### <a name="change-description"></a>Descripción del cambio

Este cambio es una continuación de [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221). Para obtener información, vea [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

La propiedad `MemoryCacheOptions.CompactOnMemoryPressure` estaba disponible.

#### <a name="new-behavior"></a>Comportamiento nuevo

Se ha quitado la propiedad `MemoryCacheOptions.CompactOnMemoryPressure`.

#### <a name="reason-for-change"></a>Motivo del cambio

La compactación automática de la caché provocaba problemas. Para evitar un comportamiento inesperado, solo se debe compactar la caché cuando sea necesario.

#### <a name="recommended-action"></a>Acción recomendada

Para compactar la caché, realice la conversión a un tipo heredado `MemoryCache` y llame a `Compact` cuando sea necesario.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
