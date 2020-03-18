---
ms.openlocfilehash: 5ad9c494fd02059e05cc744aad3b06cfc9399995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451903"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>El valor predeterminado de HttpRequestMessage.Version ha cambiado a 1.1

El valor predeterminado de la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> ha cambiado de 2.0 a 1.1.

#### <a name="version-introduced"></a>Versión introducida

3.0

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

#### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
