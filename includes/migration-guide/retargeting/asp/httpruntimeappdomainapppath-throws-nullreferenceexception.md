---
ms.openlocfilehash: d6c658f306dd4792e3cb5dbdc9471043ca95a071
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859182"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath inicia una excepción NullReferenceException

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6.2, el entorno de ejecución inicia una excepción <code>T:System.NullReferenceException</code> al recuperar un valor <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> que incluye caracteres NULL. En .NET Framework 4.6.1 y versiones anteriores, el entorno de ejecución inicia una excepción <code>T:System.ArgumentNullException</code>.|
|Sugerencia|Puede hacer lo siguiente para responder a este cambio:<ul><li>Controle <code>T:System.NullReferenceException</code> si la aplicación se ejecuta en .NET Framework 4.6.2.</li><li>Actualice a .NET Framework 4.7, que restaura el comportamiento anterior e inicia una excepción <code>T:System.ArgumentNullException</code>.</li></ul>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|

