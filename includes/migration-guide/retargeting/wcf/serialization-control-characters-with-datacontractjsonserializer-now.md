---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614788"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a>La serialización de los caracteres de control con DataContractJsonSerializer ahora es compatible con ECMAScript V6 y V8

#### <a name="details"></a>Detalles

En .NET Framework 4.6.2 y versiones anteriores, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> no serializaba algunos caracteres de control especiales, como \b, \f y \t, de una forma que fuera compatible con los estándares ECMAScript V6 y V8. A partir de .NET Framework 4.7, la serialización de estos caracteres de control es compatible con ECMAScript V6 y V8.

#### <a name="suggestion"></a>Sugerencia

Esta característica está habilitada de forma predeterminada para las aplicaciones destinadas a .NET Framework 4.7. Si no desea este compartimiento, puede rechazar esta característica agregando la siguiente línea a la sección `<runtime>` del archivo app.config o web.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
