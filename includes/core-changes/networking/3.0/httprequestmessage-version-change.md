---
ms.openlocfilehash: 9aff20e35469f9e786f0f790fda4ffaa04e76e64
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116425"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>El valor predeterminado de HttpRequestMessage.Version ha cambiado a 1.1

El valor predeterminado de la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> ha cambiado de 2.0 a 1.1.

#### <a name="version-introduced"></a>Versión introducida

.NET Core 3.0

#### <a name="change-description"></a>Descripción del cambio

En las versiones 1.0 a 2.0 de .NET Core, el valor predeterminado de la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> es 1.1. A partir de la versión 2.1 de .NET Core, se ha cambiado a 2.1.

A partir de la versión 3.0 de .NET Core, el número de versión predeterminado devuelto por la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> es, una vez más, 1.1.

#### <a name="recommended-action"></a>Acción recomendada

Actualice el código si depende de que la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> devuelva un valor predeterminado de 2.0.

#### <a name="category"></a>Categoría

Redes

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
