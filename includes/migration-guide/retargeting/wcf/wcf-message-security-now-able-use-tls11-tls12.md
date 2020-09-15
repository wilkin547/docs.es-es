---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614802"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>La seguridad de los mensajes de WCF ahora puede usar TLS1.1 y TLS1.2

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7, los clientes pueden configurar TLS1.1 o TLS1.2 en la seguridad de los mensajes de WCF además de SSL3.0 y TLS1.0 a través de ajustes de configuración de la aplicación.

#### <a name="suggestion"></a>Sugerencia

En .NET Framework 4.7, la compatibilidad con TLS1.1 y TLS1.2 en la seguridad de los mensajes de WCF está deshabilitada de forma predeterminada. Se puede habilitar si se agrega la línea siguiente a la sección `<runtime>` del archivo app.config o web.config:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7         |
| Tipo    | Redestinación |
