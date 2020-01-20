---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901682"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Almacenamiento en caché: se ha quitado la propiedad CompactOnMemoryPressure

En la versión ASP.NET Core 3.0 se han quitado las [API MemoryCacheOptions](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18) obsoletas.

#### <a name="change-description"></a>Descripción del cambio

Este cambio es una continuación de [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221). Para obtener información, vea [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).

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
