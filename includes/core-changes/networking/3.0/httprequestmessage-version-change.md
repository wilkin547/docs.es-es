---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567745"
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

-- >

