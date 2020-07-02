---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617550"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath inicia una excepción NullReferenceException

#### <a name="details"></a>Detalles

En .NET Framework 4.6.2, el entorno de ejecución inicia una excepción `T:System.NullReferenceException` al recuperar un valor `P:System.Web.HttpRuntime.AppDomainAppPath` que incluye caracteres NULL. En .NET Framework 4.6.1 y versiones anteriores, el entorno de ejecución inicia una excepción `T:System.ArgumentNullException`.

#### <a name="suggestion"></a>Sugerencia

Puede hacer lo siguiente para responder a este cambio:

- Controle `T:System.NullReferenceException` si la aplicación se ejecuta en .NET Framework 4.6.2.
- Actualice a .NET Framework 4.7, que restaura el comportamiento anterior e inicia una excepción `T:System.ArgumentNullException`.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
